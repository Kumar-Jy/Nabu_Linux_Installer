# 📱 Nabu Dual-Boot/Triple-Boot Installation Guide (Android + Windows / Linux)

This guide will help you set up **Windows** and/or **Linux** alongside Android using a **modded TWRP recovery**.

---

## 📋 Prerequisites

Before you begin, ensure your environment meets the following requirements:

* **Unlocked Bootloader** (Mandatory)
* At least **50% battery** charge
* A host machine (PC or secondary Android device with ADB/Fastboot binaries configured)
* A reliable USB data cable

---

## 💻 ADB & Fastboot Setup

If your host machine isn't configured yet, choose your platform below to set up your flashing environment:
<details> 
<summary>🪟 Method A: Using a Windows PC</summary>

1. Download the official [Google Platform Tools for Windows](https://developer.android.com/tools/releases/platform-tools).
2. Extract the contents of the ZIP folder to an easy-to-reach location (e.g., `C:\platform-tools`).
3. Open **Windows Terminal** or **Command Prompt** and navigate to your folder:
 ```cmd
cd C:\platform-tools
```
4. **Driver Note:** If your phone shows up with a yellow warning triangle in Device Manager while in Fastboot mode, download and install the official
[Google USB Drivers](https://developer.android.com/studio/run/win-usb)

</details>

<details>
<summary>📱 Method B: Using Another Android Phone (OTG)</summary>

You can flash your device using a secondary Android phone via a USB-OTG adapter.

1. Install: **Bugjaeger Mobile ADB - USB OTG** from the Google Play Store.
2. Connect both phones using a USB cable and Plug the OTG adapter into the host phone
3. Launch Bugjaeger - Accept the USB permission prompt
4. Go to Fastboot section- Open the Commands tab (terminal icon) to run ADB/Fastboot commands
</details>


## 📦 1. Partitioning
<details>

  1. Download required files:
   - 👉 [Modded-TWRP.zip](https://github.com/Kumar-Jy/twrp_device_xiaomi_nabu/releases/tag/mod-hybrid)
     
  2. Boot into modded TWRP: 
   ```bash
   fastboot boot modded-twrp.img
   ```
  3. In TWRP:
   - Go to **Advanced → Terminal**
   - Type:
     ```bash
     partition
     ```
   - Enter the required size in GB for:
     - Windows (W) :
     - Linux  (L)  :    
     *(You can choose either one or both depending on your setup and Press Enter to skip any part)*
  
  4. Once done:
   - Reboot to **System** and setup Android
</details>

---

## 🪟 2. Windows Installation  *`[ Skip if Windows not required ]`*  
<details>
1. Download required files:

  👉 [Windows-Image](https://arkt-7.github.io/woawin/)  

  👉 [Nabu-Win-Installer.zip](https://github.com/Kumar-Jy/Windows-in-NABU-Without-PC/releases/tag/Nabu-WinInstaller)

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
   - 👉 [Linux_Installer.zip](https://pixeldrain.com/l/FPTC8sMG)
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
