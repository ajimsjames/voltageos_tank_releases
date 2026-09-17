# VoltageOS 6.1 for Motorola Edge 50 (tank)

<div align="center">

![VoltageOS Banner](https://raw.githubusercontent.com/ajimsjames/voltageos_tank_releases/main/assets/banner.png)

[![Android 17](https://img.shields.io/badge/Android-17.0-blue.svg?style=for-the-badge&logo=android)](https://www.android.com/)
[![VoltageOS](https://img.shields.io/badge/VoltageOS-v6.1-cyan.svg?style=for-the-badge&logo=lightning)](https://github.com/VoltageOS)
[![Device](https://img.shields.io/badge/Device-Motorola_Edge_50_(tank)-purple.svg?style=for-the-badge&logo=motorola)](https://github.com/ajimsjames/android_device_motorola_tank)
[![Maintainer](https://img.shields.io/badge/Maintainer-ajimsjames-green.svg?style=for-the-badge&logo=github)](https://github.com/ajimsjames)
[![Website](https://img.shields.io/badge/Release_Portal-Live-00f0ff.svg?style=for-the-badge&logo=google-chrome)](https://ajimsjames.github.io/voltageos_tank_releases/)

**⚡ Pure Performance. Cybernetic Elegance. Android 17. ⚡**

[🌐 **Visit Release Website & Interactive Download Portal**](https://ajimsjames.github.io/voltageos_tank_releases/)

</div>

---

## 📱 Hardware & Device Specifications

| Specification | Details |
| :--- | :--- |
| **Device Model** | Motorola Edge 50 |
| **Codename** | `tank` |
| **Platform / SoC** | Qualcomm Snapdragon 7s Gen 2 (`SM7450` / 4nm) |
| **Architecture** | Octa-core (`4x 2.40 GHz Cortex-A78` + `4x 1.95 GHz Cortex-A55`) |
| **GPU** | Adreno 710 |
| **Display** | 6.7" Curved pOLED, 1.5K (1220 x 2712), 120Hz, HDR10+, 1900 nits peak |
| **Cameras** | 50 MP (Sony LYT-700C, OIS) + 10 MP (Telephoto 3x, OIS) + 13 MP (Ultrawide) \| 32 MP Front |
| **Battery & Charging** | 5000 mAh, 68W TurboPower wired, 15W wireless |
| **Security / Biometrics**| Under-display Optical Fingerprint (Goodix UDFPS), Face Unlock |
| **Audio & Codecs** | Stereo Speakers, Dolby Atmos, LDAC (990kbps), aptX HD / Adaptive, LHDC v5 |
| **Kernel / Root** | KernelSU-Next Pre-integrated (`CONFIG_KSU=y`) |

---

## ⚡ Key Highlights & Features

- **VoltageOS 6.1**: Powered by Android 17 with buttery smooth UI, electric customization engine, and performance governor tuning.
- **KernelSU-Next Support**: Built with root-level hook support for KernelSU-Next without tripping Play Integrity.
- **Full Hardware Support**: 120Hz dynamic refresh rate, Sony LYT-700C camera sensor pipeline, UDFPS, Fast Charging 68W, and Hi-Res wireless audio codecs.
- **SafetyNet / Play Integrity**: Passes Basic & Device Integrity out of the box.

---

## 📥 Download Links

You can browse all builds, mirrors, changelogs, and fastboot images directly on our [**Interactive Release Portal**](https://ajimsjames.github.io/voltageos_tank_releases/).

- **GitHub Releases**: [Releases Page](https://github.com/ajimsjames/voltageos_tank_releases/releases)

---

## 🛠️ Flashing & Installation Guide

> [!IMPORTANT]
> - Ensure your bootloader is unlocked.
> - Take a full backup of your internal storage before proceeding.
> - Ensure you are on the latest stock Motorola Android 14/15 firmware baseline.

### Method 1: Recovery Sideload (Recommended)

1. Reboot your phone to Fastboot mode:
   ```bash
   adb reboot bootloader
   ```
2. Flash the custom boot/vendor_boot/recovery partitions:
   ```bash
   fastboot flash boot boot.img
   fastboot flash vendor_boot vendor_boot.img
   fastboot flash dtbo dtbo.img
   fastboot flash recovery recovery.img
   ```
3. Reboot to Recovery:
   ```bash
   fastboot reboot recovery
   ```
4. In Recovery, perform a **Factory Reset / Format Data** (`Wipe data/factory reset`).
5. Select **Apply Update** > **Apply from ADB**, and run:
   ```bash
   adb sideload voltage-6.1-tank-OFFICIAL.zip
   ```
6. Reboot System and enjoy VoltageOS!

---

## 🏗️ Source Code & Building

To build VoltageOS 6.1 for Motorola Edge 50 (`tank`):

1. Initialize VoltageOS source tree:
   ```bash
   repo init -u https://github.com/VoltageOS/manifest.git -b 17
   ```
2. Place `sm7450.xml` inside `.repo/local_manifests/`:
   ```bash
   mkdir -p .repo/local_manifests
   curl -sL https://raw.githubusercontent.com/ajimsjames/voltageos_tank_releases/main/sm7450.xml -o .repo/local_manifests/sm7450.xml
   ```
3. Sync repository:
   ```bash
   repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
   ```
4. Build VoltageOS:
   ```bash
   . build/envsetup.sh
   lunch voltage_tank-userdebug
   m voltage
   ```

---

## 🤝 Maintainer & Credits

- **Device Maintainer**: [AJIMS JAMES](https://github.com/ajimsjames)
- **VoltageOS Team**: [VoltageOS GitHub](https://github.com/VoltageOS)
- **KernelSU-Next**: [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next)
- **Motorola Mobility LLC**: For kernel sources and device components

---

<div align="center">
  <sub>Maintained with ⚡ for Motorola Edge 50 Community</sub>
</div>
