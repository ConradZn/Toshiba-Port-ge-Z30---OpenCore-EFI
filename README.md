# OpenCore 1.0.7 EFI for Toshiba Portege Z30T-B

<img width="1672" height="941" alt="ChatGPT Image 7  5  2026 15_10_59" src="https://github.com/user-attachments/assets/436c39aa-c27b-4a2d-b2cf-898214f08728" />

This repository provides a fully optimized OpenCore EFI configuration for the **Toshiba Portege Z30T-B** running **macOS Ventura**.

The EFI already contains everything required for installation and daily usage, including working Wi-Fi, Bluetooth, sleep, iServices, and graphics acceleration support through OCLP.

---

# 💻 Supported Hardware

| Model | CPU Generation | Architecture | Integrated GPU | Version |
| --- | --- | --- | --- | --- |
| **Toshiba Portege Z30T-B** | 5th Gen | Broadwell | Intel HD 5500 | `Up to Sequoia` |

---

# ✅ Supported macOS Version

This EFI is designed only for:

* **macOS Ventura**
* **macOS Sonoma** (For native Wi-Fi read it down below)
* **macOS Sequoia** (Change SMBIOS model to higher)

(For Sonoma and Sequoia, you will need to do trick to get native Wi-Fi working, I've already prepared the EFI for it.)
Follow this guide https://github.com/randomappleboi/Native-Wifi-for-Hackintoshes-with-Intel-Wireless-cards-on-macOS-sequoia

---

# ⚙️ BIOS Settings

Before installing macOS, configure the BIOS with the following settings:

* **Secure Boot:** Disabled
* **VT-d:** Disabled
* **CSM:** Disabled
* **Boot Mode:** UEFI Only

---

# 🚀 Installation

## 1. Prepare EFI

1. Download this EFI
2. Copy the EFI folder to your USB installer or EFI partition
3. Generate your own SMBIOS information using **GenSMBIOS**

You must generate:

* Serial Number
* Board Serial Number
* SmUUID
* ROM (use your Ethernet MAC address)

Add these values to:

```text
PlatformInfo -> Generic
```

---

## 2. Install macOS Ventura

Install macOS Ventura normally using OpenCore.

---

## 3. Enable Graphics Acceleration

macOS Ventura requires **OpenCore Legacy Patcher** for Intel HD 5500 graphics acceleration.

After installation:

1. Boot into macOS Ventura
2. Download OpenCore Legacy Patcher
3. Run:
   * **Post-Install Root Patch**
4. Reboot

---

# ✅ What Works

* Graphics acceleration (OCLP Patches)
* Audio (ALCID=3)
* Internal microphone
* Headphone jack
* Wi-Fi
* Bluetooth
* iServices (iMessages etc.)
* Keyboard shortcuts
* Trackpad gestures
* Battery percentage
* USB 3.0 ports
* Ethernet
* HDMI video output
* HDMI audio
* Sleep
* Wake from sleep
* Lid wake support

---

# ❌ Known Issues

* VGA output is not supported
* Fingerprint sensor is not supported
* Touchscreen (never will)

---

# 🛠 Recommended Utilities

| Utility | Description | Download |
| --- | --- | --- |
| **OpenCore Legacy Patcher** | Graphics acceleration patches for Ventura | https://github.com/dortania/OpenCore-Legacy-Patcher |
| **DiscreteScroll** | Fixes external mouse wheel scrolling without affecting trackpad scrolling | https://github.com/emreyolcu/discrete-scroll |
| **OCAT** | OpenCore config.plist editor | https://github.com/ic005k/OCAuxiliaryTools |
| **GenSMBIOS** | SMBIOS generator for OpenCore | https://github.com/corpnewt/GenSMBIOS |
| **ProperTree** | OpenCore plist editor | https://github.com/corpnewt/ProperTree |
| **Stats** | Hardware monitoring utility | https://github.com/exelban/stats |
| **Rectangle** | Window management utility | https://github.com/rxhanson/Rectangle |

---

# 🙌 Credits

* [Acidanthera](https://github.com/acidanthera) for OpenCore
* [OpenIntelWireless](https://github.com/OpenIntelWireless) for Intel Wi-Fi and Bluetooth support
* [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) for documentation
* [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher)
