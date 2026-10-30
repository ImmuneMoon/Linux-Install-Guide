# 🐧 Linux Install Guide (Linux Mint, Zorin OS & Ubuntu)

![Linux Mint | Zorin OS | Ubuntu](https://img.shields.io/badge/Linux-Mint%20%7C%20Zorin%20OS%20%7C%20Ubuntu-E95420?logo=linux&logoColor=white)
![Tools: balenaEtcher, Rufus](https://img.shields.io/badge/Tools-balenaEtcher%20%7C%20Rufus-5c2d91)
![Needs an 8 GB or larger USB drive](https://img.shields.io/badge/Needs-8%20GB%2B%20USB%20drive-6f42c1)
[![Last updated](https://img.shields.io/github/last-commit/ImmuneMoon/Linux-Install-Guide?label=updated)](https://github.com/ImmuneMoon/Linux-Install-Guide/commits/main)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey)](LICENSE)

**📄 [Download the PDF](Linux-Install-Guide.pdf)**

## 📖 Overview
The **Linux Install Guide** walks first-time users through moving a PC to Linux, from picking a version to the first updates. It's a good fit for PCs that can't run Windows 11, and it helps keep older hardware out of the bin.

The guide is built around one idea: you can run Linux from a USB drive and test everything before you change anything on your PC. It covers Linux Mint, Zorin OS, and Ubuntu, and it covers replacing Windows or installing alongside it.

## ⚠️ Important Disclaimer
Installing Linux can permanently erase your drive, and installing alongside Windows changes its partitions. Back up anything you can't afford to lose first, and check the drive before you click **Install**. Versions, menu names, and support dates change, so confirm them on each project's site.

## 🚀 How to Use
Download the PDF above, or read on below. Start with **Before You Start** and work through the steps in order. You can stop after **Step 5** without having changed anything on your PC.

This guide works alongside two others:
* [Windows 10 Community Support Guide](https://github.com/ImmuneMoon/Windows-10-Community-Support-Guide) - Your options if you're leaving, or staying on, Windows 10.
* [Windows Install Guide](https://github.com/ImmuneMoon/Windows-Install-Guide) - Making a Windows USB drive, if you'd rather stay on Windows.

---

<!-- guide:start -->

*Versions and support dates were checked in October 2026. They change, so confirm them on each project's site.*

## The Problem
You want to give a PC a new life with Linux, maybe because it can't run Windows 11 or because you're done with Windows. You've never installed Linux, and you don't want to lose your files or end up with a PC that won't start.

## How a Linux Install Actually Works
Linux comes as an ISO file, which you write to a USB flash drive. The useful part comes next: when you start your PC from that drive, Linux runs from the USB without touching your hard drive. This is called a **live session**, and it lets you test everything before you change anything.

So the order is always:

1. Back up your files.
2. Make the USB drive.
3. Try Linux from the USB. Nothing is installed yet.
4. Install it only if you're happy.

If you don't like it, shut down, pull out the USB drive, and your PC is exactly as it was.

## Before You Start
1. **Back up everything you care about** to an external drive or cloud storage. Installing Linux can erase your drive, and even the safer option changes your partitions.
2. **Save your BitLocker recovery key** if your drive is encrypted. Find it at [aka.ms/myrecoverykey](https://aka.ms/myrecoverykey). Windows may ask for it after the changes below.
3. **List the apps you can't live without,** then check whether they run on Linux. This is what usually decides whether Linux will work for you. Many things run in a browser now, and web apps work the same on Linux.
4. **Get a flash drive of at least 8 GB.** It will be erased.
5. **Plug the PC into power** if it's a laptop.

## Step 1: Choose Your Linux
You can't go too far wrong here. If you aren't sure, pick **Linux Mint Cinnamon**. You can try more than one from USB before you decide.

| Linux | Good for | Version | Requirements |
|---|---|---|---|
| **[Linux Mint](https://linuxmint.com/download.php)** | People coming from Windows. Its layout will feel familiar. | 22.3, supported until April 2029 | About 15 GB for the system, with 100 GB or more recommended |
| **[Zorin OS](https://zorin.com/os/download/)** | People who want a polished look, with layouts that resemble Windows. The Core edition is free. | 18.1 | 1 GHz dual-core 64-bit, 2 GB RAM, 15 GB storage |
| **[Ubuntu](https://ubuntu.com/download/desktop)** | People who want the most widely used option, with plenty of guides online. | 26.04.1 LTS, with five years of free updates | 2 GHz dual-core, 6 GB RAM, 25 GB storage |

> **Older PC?** Linux Mint's **Xfce** edition is lighter than Cinnamon, and Zorin OS has a Lite edition.

## Step 2: Download and Check the ISO
1. Download the ISO from the project's own site, using the links in the table above.
2. Check that the download is intact. On Windows, open the Start menu, type `cmd`, and open **Command Prompt**. Run this, using your file's path:
   ```cmd
   certutil -hashfile "C:\Users\You\Downloads\linux.iso" SHA256
   ```
3. Compare the long code it prints with the one the project publishes. Linux Mint lists them in a `sha256sum.txt` file on its download mirrors. If they don't match, download the ISO again.

## Step 3: Make the USB Drive
Both tools below **erase everything on the flash drive**. Linux Mint's own [install guide](https://linuxmint-installation-guide.readthedocs.io/en/latest/burn.html) recommends balenaEtcher, and it's the simpler of the two.

### Using balenaEtcher
1. Download balenaEtcher from [etcher.balena.io](https://etcher.balena.io/) and install it.
2. Plug in your flash drive and open balenaEtcher.
3. Click **Flash from file** and pick your ISO.
4. Click **Select target** and pick your flash drive. Check the name and size, since this is the drive that gets erased.
5. Click **Flash!** and click **Yes** if Windows asks for permission.
6. Wait for it to finish writing and validating, then close it.

> **Windows may say the drive needs to be formatted.** Click **Cancel**. Windows just can't read the new layout, and formatting would wipe what you just wrote.

### Using Rufus
If you already have [Rufus](https://rufus.ie/en/), or balenaEtcher won't run on your PC:

1. Open Rufus and pick your flash drive under **Device**.
2. Click **SELECT** and open your ISO.
3. Leave the other settings alone and click **START**.
4. If Rufus asks how to write the image, choose **ISO Image mode**. If the drive won't boot later, write it again using **DD Image mode**.
5. Click **OK** on the warning that everything on the drive will be destroyed.
6. Wait until the bar at the bottom says **READY**, then click **CLOSE**.

## Step 4: Start From the USB Drive
1. Plug in the USB drive and restart the PC.
2. As the PC starts, press its boot menu key. Common keys are `F12`, `F11`, `F10`, `F8`, `F2`, `F1`, `Esc`, and `Delete`. The right one is usually shown on screen for a moment.
3. Pick your USB drive from the list. If there's no boot menu, open the BIOS and move the USB drive to the top of the boot order.
4. At the Linux menu, press **Enter**. Linux will take a minute or two to load.

Leave Secure Boot on for now. These three normally start with it on. If yours won't, see **If Something Goes Wrong**.

## Step 5: Try It Before You Install
You're now running Linux from the USB drive, so it will be slower than a real install. Use this time to check the things that are hard to fix later:

- [ ] Wi-Fi connects
- [ ] Sound plays
- [ ] The screen looks right, and external monitors work
- [ ] Keyboard, touchpad, and webcam work
- [ ] Your printer works, if you need one
- [ ] The web apps you rely on work

If something doesn't work, try another Linux from **Step 1** before giving up. Hardware support varies between them. Ask for help too (see **Where to Get Help**).

## Step 6: Install It
First, choose how you want to set it up:

| Option | What it does | Choose this if |
|---|---|---|
| **Replace Windows** | Erases the drive and installs only Linux. | You've backed up, and you're sure you won't need Windows. |
| **Install alongside Windows** | Shrinks Windows and adds Linux next to it. You choose which to start each time. | You still need Windows for an app, or you want a way back. |

### If You're Installing Alongside Windows
Do these in Windows first. Install Windows before Linux, because a Windows install replaces the Linux boot menu.

1. **Turn off BitLocker** if it's on, and wait for it to finish. The installer may not offer this option on an encrypted drive.
2. **Turn off Fast Startup.** Go to **Control Panel** > **Power Options** > **Choose what the power buttons do** > **Change settings that are currently unavailable**, uncheck **Turn on fast startup**, and click **Save changes**. Have your recovery key ready, because Windows may ask for it afterward.

### Running the Installer
These are the Linux Mint steps. Zorin OS and Ubuntu use different wording, but they ask the same questions.

> **Unplug any drive you aren't installing to.** This is especially important if you're erasing a drive. It stops you from picking the wrong one, and it keeps the boot files on the right drive.

1. Double-click **Install Linux Mint** on the desktop.
2. Choose your language and keyboard layout, and connect to the internet.
3. Tick the box to install multimedia codecs.
4. Choose your installation type:
   * **Erase disk and install Linux Mint** replaces everything on the drive.
   * **Install alongside** appears if the installer finds Windows. Use the slider to decide how much space each one gets.
   * **Something else** is for managing partitions by hand. Skip it unless you know you need it.
5. Pick your time zone.
6. Enter your name, a username, a computer name, and a strong password. Use lowercase letters for the username. Tick **Encrypt my home folder** if you want your files protected if the PC is stolen.
7. Wait for the slideshow to finish, then click **Restart Now**.
8. Remove the USB drive when asked and press **Enter**.

## Step 7: After the Install
1. **Install all updates.** Open **Update Manager** from the menu and apply everything. Do this first.
2. **Check your drivers.** Go to **Menu** > **Administration** > **Driver Manager**, tick any recommended drivers, click **Apply Changes**, and restart.
3. **Set up system snapshots.** Go to **Menu** > **Administration** > **Timeshift**, choose **RSYNC**, pick a drive, and choose a schedule. If an update ever breaks something, you can roll back.
4. **Copy your files back** from your backup.

On Zorin OS and Ubuntu, the update and driver tools have different names. Search for "updates" or "drivers" in the app menu.

> **Keeping files on a second drive?** Linux can read normal Windows drives, so you can leave your files there and open them from the file manager. A BitLocker-encrypted drive will need its key. The [Remove an Old Windows Install guide](https://github.com/ImmuneMoon/Remove-Old-Windows-Install-Keep-Your-Files) uses Windows commands, so it won't work from Linux.

## Where to Get Help
You don't have to do this alone. These communities exist to help people make this move, and they're free:

* **Project forums:** [Linux Mint](https://forums.linuxmint.com/), [Zorin OS](https://forum.zorin.com/), and [Ubuntu](https://discourse.ubuntu.com/).
* **[End of 10](https://endof10.org/):** A campaign that helps people move old PCs to Linux.
* **[Repair Cafés](https://www.repaircafe.org/en/):** Free volunteer events in many countries. Some help with PCs, so check first.
* **The Restart Project's [toolkit](https://therestartproject.org/end-of-windows-10-toolkit-for-repair-groups/) and [forum](https://talk.restarters.net/):** Volunteers working through the same decisions.

If you're leaving Windows 10, the [Windows 10 Community Support Guide](https://github.com/ImmuneMoon/Windows-10-Community-Support-Guide) covers your other options too. To see whether your PC can run Windows 11 instead, use the check in the [Windows Install Guide](https://github.com/ImmuneMoon/Windows-Install-Guide).

## If Something Goes Wrong
| What happens | What to do |
|---|---|
| **The PC ignores the USB drive** | Try another USB port, use the boot menu key instead of restarting normally, and check the drive in **Step 3** finished without errors. |
| **Secure Boot blocks it** | Linux Mint's [guide](https://linuxmint-installation-guide.readthedocs.io/en/latest/efi.html) gives two fixes: reinstall with the internet connected and without the third-party software option, or turn off Secure Boot in your BIOS. Some PCs instead need an option like **Microsoft Third-Party CA** turned on. |
| **No "alongside" option** | Make sure BitLocker and Fast Startup are off, and that Windows has free space. If it's still missing, ask on your project's forum rather than partitioning by hand. |
| **The PC goes straight to Windows** | Open the BIOS and move Linux to the top of the boot order. Linux Mint and Ubuntu may be listed as `ubuntu`. |
| **Windows updates removed the boot menu** | This can happen with a Windows reinstall. Mint's [multi-boot page](https://linuxmint-installation-guide.readthedocs.io/en/latest/multiboot.html) covers restoring it from the USB drive. |

## Fixes That Don't Help
* **Formatting the USB drive when Windows asks.** This erases the installer. Click **Cancel**.
* **Turning off Secure Boot right away.** It's often not needed, so try with it on first. Leave it on if you can.
* **Using balenaEtcher for a Windows installer.** It's for Linux and ready-made images. To make a Windows USB, use the [Windows Install Guide](https://github.com/ImmuneMoon/Windows-Install-Guide).
* **Skipping the backup because you chose "alongside".** That option resizes your Windows partition, which is exactly when a backup matters.

## Quick Checklist
- [ ] Backed up my files and saved my BitLocker recovery key
- [ ] Checked that my must-have apps work on Linux
- [ ] Downloaded the ISO from the project's own site and checked its hash
- [ ] Made the USB drive, and clicked **Cancel** if Windows offered to format it
- [ ] Tried Wi-Fi, sound, display, and other hardware from the USB drive
- [ ] Turned off BitLocker and Fast Startup, if installing alongside Windows
- [ ] Unplugged any drive I'm not installing to
- [ ] Installed Linux and removed the USB drive when asked
- [ ] Installed updates, checked drivers, and set up Timeshift

<!-- guide:end -->

## ☕ Support the Project

If you find this project helpful and want to support further development by Fulllion Creative Works, consider leaving a tip!

* [Donate via PayPal](https://www.paypal.com/donate/?hosted_button_id=LCDZX75HR4CLC)
* [Support on Ko-fi](https://ko-fi.com/fulllion)

---
© 2026 Fulllion Creative Works. All rights reserved.
