# 📱 Multi-OS Installation Guide (Android + Windows + Linux)

This guide will help you set up **Windows** and/or **Linux** alongside Android using a **modded TWRP recovery**.

---

## 📋 Prerequisites

Before you begin, make sure you have the following:

- 🔧 **Unlocked Bootloader**
- 🔋 At least **50% battery**
- 💾 Backup of all important data
- 🧰 Required files:

### 📥 Downloads

- 🛠️ Modded TWRP  
  👉 [Modded-TWRP.zip](https://github.com/Kumar-Jy/twrp_device_xiaomi_nabu/releases/download/mod-win/TEST_V4-MODDED-TWRP-WINDOWS-17-04.img) 

- 🪟 Windows ESD Image  
  👉 [Windows-Image](https://arkt-7.github.io/woawin/)  

- 📦 WinInstaller ZIP  
  👉 [Nabu-WinInstaller.zip](https://github.com/Kumar-Jy/Windows-in-NABU-Without-PC/releases/tag/Nabu-WinInstaller) 

- 🐧 Linux Installer ZIP  
  👉 [Nabu-Linux-Installer.zip](https://drive.google.com/file/d/1C0CX-avpkK0a8TSgN6Ji9W3TljwfFo4c/view?usp=sharing)  

- 🔁 SB/NSB Boot Switcher ZIP  
  👉 [SB/NSB-Boot-Switcher.zip](https://github.com/Kumar-Jy/Windows-in-NABU-Without-PC/releases/download/Files/NABU_SB_NSB_boot_switcher_V260119.zip) 

---

## 📦 1. Partitioning

1. Boot into modded TWRP:
   ```bash
   fastboot boot modded-twrp.img
   ```
2. In TWRP:
   - Go to **Advanced → Terminal**
   - Type:
     ```bash
     partition
     ```
   - Enter the required size for:
     - Windows
     - Linux  
     *(You can choose either one or both depending on your setup)*
3. Once done:
   - Reboot to **System**

---

## 🪟 2. Windows Installation

1. Download required files:
   - Windows `.esd` image  
   - `WinInstaller.zip`
2. Reboot into **modded TWRP**
3. Install Windows:
   - Go to **Install**
   - Select `WinInstaller.zip`
   - Swipe to flash
4. Wait for installation to finish, then reboot
5. First boot:
   - Wait for Windows setup to complete
   - Finish initial setup
6. After setup:
   - Reboot back to **Android**

---

## 🐧 3. Linux Installation

1. Download required files:
   - `Linux-Installer.zip`
   - `SB/NSB Boot Switcher.zip`
2. Flash Boot Switcher:
   - Reboot into **modded TWRP**
   - Go to **Install**
   - Select `SB/NSB Boot Switcher.zip`
   - Swipe to flash
   - Reboot when done  
     *(This switches Windows to No Secure Boot, required for triple boot)*
3. Return to Android, then:
   - Reboot again into **modded TWRP**
4. Install Linux:
   - Select `Linux-Installer.zip`
   - Swipe to flash
5. Once finished:
   - Reboot to system
6. Boot Menu:
   - Device will boot into **UEFI menu**
   - Use:
     - **Volume Up/Down** → Navigate  
     - **Power Button** → Select OS
7. Choose your desired OS and boot 🎉

---

## ⚠️ Notes

- Make sure your battery is sufficiently charged before starting
- Backup important data before partitioning
- Incorrect partition sizes may break installation

---

## 🚀 Enjoy Your Multi-Boot Setup!

You can now switch between:
- Android  
- Windows  
- Linux  

Anytime from the UEFI boot menu.