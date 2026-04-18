# Workflow Guide: Create Installer Release

This guide explains how to use the automated GitHub Actions workflow to generate and upload the Linux installer ZIP to releases.

## Overview

The workflow automates:
- Downloading Linux image and EFI files from provided links
- Extracting them if they're in compressed format (gzip, bzip2, xz, 7z, zip)
- Copying the image to `/image/` directory
- Copying the EFI file to `/efi/linux/` directory
- Creating a properly structured installer ZIP archive
- Creating a GitHub release with the ZIP file as an asset

## Supported Compression Formats

The workflow automatically detects and extracts:
- **gzip** (.gz, .tar.gz)
- **bzip2** (.bz2, .tar.bz2)
- **xz** (.xz, .tar.xz)
- **7-zip** (.7z)
- **zip** (.zip)
- **Raw files** (no compression)

## How to Run the Workflow

### Option 1: Via GitHub Web UI

1. Go to your repository on GitHub
2. Click on the **Actions** tab
3. Select **Create Installer Release** workflow from the left sidebar
4. Click **Run workflow** button
5. Fill in the required inputs:
   - **img_link**: Full URL/link to your Linux image file (compressed or raw)
   - **efi_link**: Full URL/link to your EFI file (compressed or raw)
   - **release_tag**: Version tag (e.g., `v1.0.0`, `v1.0.1`, etc.)
6. Click **Run workflow**

### Option 2: Using GitHub CLI

```bash
gh workflow run create-installer-release.yml \
  -f img_link="<URL_TO_IMG>" \
  -f efi_link="<URL_TO_EFI>" \
  -f release_tag="v1.0.0"
```

## Input Parameters

### img_link (Required)
- **Description**: Download link for the Linux image file
- **Format**: Full URL with protocol (http://, https://, ftp://, etc.)
- **Examples**:
  - `https://example.com/linux.img.7z`

### efi_link (Required)
- **Description**: Download link for the EFI file
- **Format**: Full URL with protocol
- **Examples**:
  - `https://example.com/efi_files.efi.xz`
  - `https://example.com/efi_files.tar.zip`

### release_tag (Required)
- **Description**: Release version tag
- **Format**: Standard semantic versioning (e.g., `v1.0.0`)
- **Examples**: `v1.0.0`, `v1.0.1`, `v2.0.0-beta`, `v1.1.0-rc1`

## Workflow Steps

The workflow performs these steps in order:

1. **Checkout repository** - Gets the latest code
2. **Download files** - Downloads Linux image and EFI file from provided links
3. **Extract Linux image** - Detects format and extracts if compressed
4. **Extract EFI file** - Detects format and extracts if compressed
5. **Prepare EFI directory** - Prepares the EFI file for use
6. **Copy files** - Copies files to correct directories:
   - Linux image → `image/linux.img`
   - EFI file → `efi/linux/bootaa64.efi`
7. **Verify structure** - Confirms files are in place
8. **Create ZIP** - Creates `installer_linux.zip` with proper structure
9. **Create Release** - Creates GitHub release with release notes
10. **Upload Asset** - Uploads ZIP file to the release
11. **Cleanup** - Removes temporary files

## Output

After successful execution:

- ✅ A new GitHub release with tag `<release_tag>` is created
- ✅ The release contains `installer_linux.zip` as an asset
- ✅ Release notes include:
  - Release date and time
  - Source links for image and EFI files
  - List of updated components
  - Link to installation guide

## ZIP Archive Structure

The created ZIP file contains:

```
installer_ubuntu/
├─ README.md
├─ bin/
├─ DBKP/
├─ efi/
│  ├─ android/
│  ├─ BOOT/
│  └─ linux/
│     └─ linux.efi (updated)
├─ image/
│  └─ linux.img (updated)
└─ META-INF/
```

## Troubleshooting

### Workflow fails with "Download failed"
- Verify the links are correct and accessible
- Check that the links are publicly accessible (no authentication required)
- Try the links manually in a browser to confirm

### "No .img file found in archive"
- The compressed file doesn't contain a `.img` file
- Extract the compressed file manually to check its contents
- Ensure you're providing the correct file link

### "EFI file not found"
- The compressed file doesn't contain a `.efi` file
- Check the actual filename inside the compressed file
- Manual extraction might be needed to verify contents

### ZIP file is too large
- This is expected if the Linux image is large (typically 500MB - 2GB+)
- Ensure you have sufficient GitHub release storage

## Notes

- The workflow preserves the exact directory structure as specified in README.md
- Only `linux.img` and `efi/linux/linux.efi` are updated
- All other files (bin/, DBKP/, META-INF/) remain unchanged
- Each release is independent and doesn't affect previous releases
- Release tags must be unique (attempting to use an existing tag will fail)

## Example Workflow Run

```
Input:
  img_link: https://example.com/ubuntu-22.04-arm64.img.xz
  efi_link: https://example.com/efi_files.efi.xz
  release_tag: v1.0.0

Output:
  Release: Linux Installer v1.0.0
  Asset: installer_ubuntu.zip (containing updated linux.img and bootaa64.efi)
```

## Support

For issues or questions:
1. Check the workflow execution logs in Actions tab
2. Review the step output for detailed error messages
3. Verify input parameters are correct
4. Check that links are accessible and contain expected files
