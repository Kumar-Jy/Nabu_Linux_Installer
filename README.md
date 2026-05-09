# Linux Installer Zip for Xiaomi Pad 5 (NABU)
---
### 📱 Installation Instruction
  - 👉 [Dual Boot/Triple Boot Installation Guide](Installation.md)

---
## Create the release ZIP archive

This repository should be packaged into a single ZIP archive from the repository root folder `Linux_Installer_Zip`.

### Required archive structure

The ZIP must contain the following top-level items as shown in the graph below:

```
Linux_Installer.zip/
├─ README.md
├─ bin/
├─ DBKP/
├─ EFI/
│  └─ android/
│  └─ BOOT/
│  └─ linux/
│     └─ linux.efi
├─ image/
│  └─ rootfs.img
└─ META-INF/
```

- `bin/`, and `DBKP/` are constant directories. Do not change or expand their internal contents in the archive.
- Put the linux boot.efi into the `EFI/linux/` directory.
- Put the Linux rootfs.img into the `installer_linux/image/rootfs.img`.
- Select all folders and pack it as a zip file using 7zip.

### Notes
- The ZIP should preserve the directory layout exactly as shown above.
- Do not include any unrelated files outside the listed root directories.

### Credit & Thanks
| File | Description | Author & Link |
| :--- | :--- | :--- |
| Linux-Installer | Linux Installer script | [Kumar-Jy](https://github.com/Kumar-Jy) |
| RootFS & efi | Linux RootFS image | [Timofey](https://github.com/timoxa0) , [Canonical](https://github.com/canorical) , [TheMojoMan](https://github.com/TheMojoMan) , [jhuang](https://github.com/jhuang6451/nabu_fedora), [PocketBlue](https://github.com/pocketblue) |
| DBKP/ | DualBoot kernel patcher and UEFI payload | [rodriguest](https://github.com/rodriguezst) , [remtrik](https://github.com/remtrik) , [map220v](https://github.com/map220v), [project Aloha](https://github.com/Project-Aloha) |
| And all the other developers who involved directly or indirectly in the development.
 |

## See Also
* [postmarketOS](https://wiki.postmarketos.org/wiki/Xiaomi_Pad_5_%28xiaomi-nabu%29) - pmOS for nabu.
* [pocketblue](https://github.com/pocketblue/pocketblue) - Fedora Silverblue for nabu.
* [nabu-fedora](https://github.com/jhuang6451/nabu_fedora) - fedora for nabu
* [nabu-fedora-builder](https://github.com/nik012003/nabu-fedora-builder) - Another minimum Fedora for nabu (EOL).
* [nabu-alarm](https://github.com/nabu-alarm/) - alarm (Arch Linux ARM) for nabu (EOL).
* [Xiaomi-Nabu](https://github.com/TheMojoMan/Xiaomi-Nabu) - Ubuntu for nabu.