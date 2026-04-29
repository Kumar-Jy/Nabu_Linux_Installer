# Linux Installer Zip for Xiaomi Pad 5 (NABU)
---
### Installation Instruction
- #### 📱 Multi-OS Installation Guide
  - 👉 [Android + Windows + Linux](Installation.md)

---
## Create the release ZIP archive

This repository should be packaged into a single ZIP archive from the repository root folder `Linux_Installer_Zip`.

### Required archive structure

The ZIP must contain the following top-level items as shown in the graph below:

```
installer_ubuntu/
├─ README.md
├─ bin/
├─ DBKP/
├─ efi/
│  └─ android/
│  └─ BOOT/
│  └─ linux/
│     └─ linux.efi
├─ image/
│  └─ linux.img
└─ META-INF/
```

- `bin/`, and `DBKP/` are constant directories. Do not change or expand their internal contents in the archive.
- Put the linux boot.efi into the `efi/linux/` directory.
- Put the new Linux image file at `installer_linux/image/linux.img`.
- Select all folders and pack it as a zip file using 7zip.

### Notes
- The ZIP should preserve the directory layout exactly as shown above.
- Do not include any unrelated files outside the listed root directories.

### Credit & Thanks
| File | Description | Author & Link |
| :--- | :--- | :--- |
| `Linux-Installer` | Linx Installer script | [Kumar-Jy](https://github.com/Kumar-Jy) |
| `image/linux.img` | Ubuntu root filesystem image | [Canonical](https://github.com/canorical) & [TheMojoMan](https://github.com/TheMojoMan) |
| `efi/` | EFI boot files and boot configuration | [Timofey](https://github.com/timoxa0) & [TheMojoMan](https://github.com/TheMojoMan) |
| `DBKP/` | DualBoot kernel patcher and UEFI payload | [rodriguest](https://github.com/rodriguezst), [remtrik](https://github.com/remtrik), [map220v](https://github.com/map220v), [project Aloha](https://github.com/Project-Aloha) |
| `bin/` | Helper binaries for flashing | [7z](https://www.7-zip.org/) |
