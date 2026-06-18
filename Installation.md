# 📱 Nabu Dual-Boot/Triple-Boot Installation Guide (Android + Windows / Linux)

This guide will help you set up **Windows** and/or **Linux** alongside Android using a **modded TWRP recovery**.

---

##  Prerequisites

Before you begin, make sure you have the following:

-  **Unlocked Bootloader**
-  At least **50% battery**
-  Backup of all important data
-  Required files:

###  Downloads

-  Modded TWRP  
  👉 [Modded-TWRP.zip](https://github.com/Kumar-Jy/twrp_device_xiaomi_nabu/releases/tag/mod-hybrid)

-  Windows ESD Image  - `[ Skip if Windows not required ]`    
   👉 [Windows-Image](https://arkt-7.github.io/woawin/)  

-  Win Installer ZIP - `[ Skip if Windows not required ]`  
  👉 [Nabu-Win-Installer.zip](https://github.com/Kumar-Jy/Windows-in-NABU-Without-PC/releases/tag/Nabu-WinInstaller)
 
- 🐧 Linux Installer ZIP  
  👉 [Linux_Installer.zip](https://pixeldrain.com/l/q91xunoN)

---

## 📦 1. Partitioning
<details>
  
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
     - Windows (W) :
     - Linux  (L)  :
     *(You can choose either one or both depending on your setup and Press Enter to skip any part)*
  
3. Once done:
   - Reboot to **System** and setup Android
</details>

---

## 🪟 2. Windows Installation  *`[ Skip if Windows not required ]`*  
<details>
1. Download required files:
   - Windows `.esd` image  
   - `WinInstaller.zip`

   > **Make sure both files are placed in the Xiaomi Pad 5 Download folder.**

2. Reboot into **modded TWRP**
   - Go to **Install**
   - Select `WinInstaller.zip`
   - Swipe to flash
   - Wait for installation to finish, then reboot to system
   - Wait for Windows setup to complete
   - Finish initial setup
3. After setup:
   - Reboot back to **Android**

</details>

---

## 🐧 3. Linux Installation
<details>
  
1. Download required files:
   - `Linux-Installer.zip`
2. Install Linux:
   - Reboot into **modded TWRP**
   - Select `Linux-Installer.zip`
   - Swipe to flash
3. Once finished:
   - Reboot to system
4. Boot Menu:
   - Device will boot into **UEFI menu**
   - Use:
     - **Volume Up/Down** → Navigate  
     - **Power Button** → Select OS
5. Choose your desired OS and boot 🎉
</details>

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
