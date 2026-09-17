# ⚡ Kronos Kernel

**Custom kernel for Redmi Note 10S & Poco M5s (rosemary/_P)**

---

## 📱 Supported Devices

Redmi Note 10s & Poco M5s (4.19)

---

## ✨ Features

### Core
- **Kernel 4.19.325**
- **Neutron Clang v24**
- **Full LTO-friendly** (LLVM_IAS=1)
- **PREEMPT** (full kernel preemption)

### Network
- **BBRv3** TCP congestion control
- **CAKE** scheduler
- **FQ-CoDel** queue discipline
- **TCP Westwood+**

### Storage
- **Kyber** I/O scheduler (default)
- **MQ-Deadline** I/O scheduler
- **BFQ** I/O scheduler

### CPU & Timer
- **HZ 300** timer frequency
- **CPU Governors:** Performance, Schedutil, Ondemand
- **Mali GPU DVFS** support

### Charging
- **LN8000** charger support
- **BQ2597x** charger support
- **CP_QC30 + USBPD_PM** protocol
- **27W-33W** fast charging

### Root
- **KernelSU-Next** (manual hook)
  - Manager: **v3.1.0** (required)


## 🚀 Installation

1. Boot into TWRP
2. **Backup boot partition** (MANDATORY)
3. Flash `Kronos-Rosemary-vX.X.zip`
4. Reboot

---

🙏 Credits

    ZerokeLvinProject — Original Elea kernel base (

    KernelSU-Next Team — KernelSU-Next

    Neutron Toolchains — Neutron Clang

    rsuntk — KernelSU manual hook implementation

    LineageOS — Kernel base

    Xiaomi — Kernel source

📄 License

GPL v2
