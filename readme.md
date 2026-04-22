# Samuel's iPad Downgrade: Automated Tethered Downgrades (iOS 10.0.1-17.7.9) for A9 & A10 Devices

*Maintained and updated by Samuel Bowers*

Don’t let your older iDevices go to a landfill. **Samuel's iPad Downgrade** is a streamlined utility that automates the process of performing tethered downgrades to iOS versions 10.0.1 through 17.7.9 on devices equipped with A9, A9X, A10, and A10X chips. This project integrates several community-driven tools into a single, user-friendly workflow.

---

### Key Resources
*   **Version History:** See the [Changelog](changelog.md) for past updates.
*   **Use Cases:** Discover [Practical uses for Legacy iOS](#legacy-ios-use-cases).
*   **Guidelines:** Review the [Essential Information](#essential-information) before starting.
*   **Support:** Consult the [Troubleshooting/FAQ](#troubleshooting-and-faq) section or [open a new Github issue](https://github.com/SamuelTogepi/Samuel-siPadDowngrade/issues/new?template=issue.md) if you encounter problems.

---

### Compatible Hardware
*   iPad 5th gen
*   iPad Pro 9.7-inch
*   iPad Pro 12.9-inch
*   iPad 6th gen
*   iPad Pro 10.5-inch
*   iPad Pro 12.9-inch

| [Project Repository](https://github.com/SamuelTogepi/Samuel-siPadDowngrade) | [Official Homepage](https://github.com/Samuel-siPadDowngrade) |

---

## Table of Contents
1.  [Downloads](#downloads)
2.  [Essential Information](#essential-information)
3.  [System Requirements](#system-requirements)
4.  [Instructions](#instructions)
5.  [Legacy iOS Use Cases](#legacy-ios-use-cases)
6.  [Troubleshooting and FAQ](#troubleshooting-and-faq)
7.  [Project Credits](#project-credits)
8.  [Licensing](#licensing)
9.  [Build Guide](build.md)

---

## Downloads
Dusk Downgrade is compatible with Debian and Fedora Linux, as well as macOS 10.12 or later. It supports both x86_64 and ARM64 architectures.

### Latest Release: v2.0.4 (March 14, 2026)
*   [**samuel-siPadDowngrade.zip**] (Universal package for macOS and Linux)

**What’s New:**
*   Enhanced stability for Fedora users via the latest [idevice-tool-kit](https://github.com/alex-free/idevice-tool-kit) updates. Credits to Alex-Free, I'm sorry for copying a999

---

## Essential Information
*   **A10X & iOS 10 Warning:** Restoring an A10 device to iOS 10 may result in activation or cellular/baseband failures. In many cases, you can still use the device via WiFi by enabling Airplane Mode. A9 devices and any devices running iOS 11 or higher are generally unaffected by this.
*   **Patience is Key:** Particularly on A10/A10X devices running iOS 10/11, the boot or restore process may require several attempts before succeeding. Persistence is usually rewarded!

---

## System Requirements
### macOS
*   Version 10.11 (El Capitan) or higher.
*   An active installation of [Homebrew](https://brew.sh/) or [MacPorts](https://www.macports.org/install.php).

### Linux
*   Fedora or Debian (x86_64 / arm64 architecture).

---

## Instructions
1.  Download and unzip the most recent software package.
2.  Launch your Terminal.
3.  To run the tool, type `./samuel` followed by a space, then drag your chosen `.ipsw` file into the terminal window.
    *   **Linux Users:** You must run this with root permissions: `sudo ./samuel <ipsw_file>`.
    *   **macOS Users:** Sudo is not required.
4.  Interact with the on-screen prompts to complete the process.

---

## Legacy iOS Use Cases
Wondering what you can do on an older firmware?
*   **App Compatibility:** Many apps, including GarageBand, remain functional via the App Store.
*   **Ad-Free Video:** Safari-based YouTube allows you to bypass many ads simply by refreshing the page.
*   **Communication:** FaceTime and iMessage sync correctly with modern iPhones.
*   **Daily Driving:** These devices remain capable of basic tasks. For example, T-Mobile and Mint Mobile (USA) have been confirmed to work even on the oldest supported firmwares.

---

## Troubleshooting and FAQ

**The tool is stuck on "Waiting for Restore Mode."**
Perform a hard reset (Power + Home) and restart the process. Early iOS 11 builds on A10X hardware often require multiple tries.

**Fedora Linux is not recognizing my iPhone.**
If this is your first time using the tool on Fedora, reboot your workstation and try the process again.

**The process is hung on "Checkmate."**
Briefly unplug the Lightning cable and plug it back in to trigger the next step.

**I see a "Failed to open handle" error after Checkmate.**
On Linux (especially A10/A10X), this error often resolves itself. For A9, reconnect the cable; the error may appear again, but it should not be fatal to the process.

**The restore failed.**
When prompted to re-enter DFU mode, disconnect and reconnect your cable before proceeding. The subsequent attempt usually succeeds.

**How do I restart the device after it powers off?**
Because this is a tethered downgrade, you must use the `boot` command generated during the initial install. Put your device into Recovery Mode, connect it to your PC, and execute the `boot*` script found in your Dusk Downgrade folder.

**The device isn't being detected at all.**
Ensure you are using a USB-A to Lightning cable. Avoid USB-C to Lightning cables if possible; if your computer only has USB-C ports, use a USB-A adapter.

**Why is the first run so slow?**
The initial setup performs several one-time configurations and caches data. Subsequent downgrades will be much faster because the tool utilizes the `data` folder. **Always back up your `data` folder and `boot` scripts**, as they are unique to your specific device.

---

## Project Credits
This utility is made possible by the foundational work of:
*   **The Sep.lol Team:** Creators of the *turdus merula* exploit.
*   **LukeZGD:** Developer of [Legacy-iOS-Kit](https://github.com/LukeZGD/Legacy-iOS-Kit).
*   **Alex-Free:** For the idea from Dusk-Downgrader and everything to fork from this

---

## Licensing
Samuel's iPad Downgrade is distributed under the **3-BSD License** (refer to `license.md`). Please note that this tool relies on third-party dependencies governed by their own licenses:
*   **Turdus Merula:** Currently closed source.
*   **Legacy-iOS-Kit:** Licensed under GNU GPL v3.0.
*   **Dusk Downgrade Scripting:** 3-BSD.
