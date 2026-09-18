# Kronos-Rosemary-Kernel

A custom Linux kernel for **Xiaomi Redmi Note 10S / POCO M5s (rosemary)**.

Kronos-Rosemary-Kernel is built with a focus on performance, responsiveness, I/O flexibility, networking, charging support, and KernelSU-Next compatibility.

---

## 📱 Device

| Device | Codename |
|--------|----------|
| Xiaomi Redmi Note 10S | `rosemary` |
| POCO M5s | `rosemary_p` |

---

## ⚙️ Kernel

- Linux `4.19.325`
- Neutron Clang `v24`
- LLVM Integrated Assembler (LLVM_IAS)
- Full kernel preemption (`PREEMPT`)
- `HZ 300`
- LTO-friendly kernel configuration

---

## 💾 I/O Scheduler

Kronos includes multiple I/O schedulers:

- Noop
- Deadline
- CFQ
- Kyber
- MQ-Deadline
- BFQ

The available scheduler can be selected manually using **FKM (Franco Kernel Manager)** or another compatible kernel manager.

Check the currently active scheduler:

```bash
cat /sys/block/sda/queue/scheduler
```

Example:

```text
noop [deadline] cfq
```

The scheduler inside `[ ]` is the currently active scheduler.

> The default scheduler may vary depending on the kernel configuration, ROM, and device state.

---

## 🚀 CPU / GPU

### CPU Governors

- Performance
- Schedutil
- Ondemand

### GPU

- Mali GPU DVFS support

---

## 🌐 Network

Kronos includes additional networking and congestion-control options:

- BBRv3
- CAKE
- FQ-CoDel
- TCP Westwood+

---

## 🔋 Charging

Charging-related support includes:

- LN8000 charger support
- BQ2597x charger support
- CP_QC30 + USBPD_PM support
- 27W–33W fast-charging support

Actual charging speed depends on the device, charger, cable, battery temperature, battery condition, ROM, and charging configuration.

---

## 🔐 KernelSU-Next

Kronos provides separate builds with and without KernelSU-Next.

### KSU Build

```text
Kronos-Rosemary-ksu.zip
```

Includes KernelSU-Next support.

### Non-KSU Build

```text
Kronos-Rosemary-nonksu.zip
```

Standard kernel build without KernelSU-Next.

For the KSU build, use a compatible **KernelSU-Next Manager v3.3.0**.

---

## 📦 Downloads

Download the latest builds from the **Releases** section:

- `Kronos-Rosemary-ksu.zip` — KernelSU-Next build
- `Kronos-Rosemary-nonksu.zip` — Non-KSU build

Each release contains its own changelog and release-specific information.

---

## 🛠️ Installation

### Requirements

- Xiaomi Redmi Note 10S / POCO M5s (`rosemary`)
- Unlocked bootloader
- Compatible custom recovery or kernel flashing method
- Backup of your current boot image

### Flash

1. Boot into your custom recovery.
2. **Create a backup of your current boot partition.**
3. Flash the appropriate Kronos kernel ZIP.
4. Reboot the device.
5. If using the KSU build, configure KernelSU-Next after boot.

> Always make sure you are using the correct build for your device and ROM.

---

## 🔧 I/O Scheduler Configuration

You can check the current I/O scheduler through ADB:

```bash
adb shell
su
cat /sys/block/sda/queue/scheduler
```

Example output:

```text
[noop] deadline cfq
```

This means `noop` is currently active.

To change the scheduler manually:

```bash
echo kyber > /sys/block/sda/queue/scheduler
```

or use FKM if the scheduler is exposed by the kernel manager.

> Changes made directly through `/sys` are generally temporary and may be reset after reboot.

---

## 📝 Changelog

Release-specific changes are documented on the GitHub Releases page.

See:

**Releases → Select a version → Changelog**

---

## 🤝 Credits

- **ZerokeLvinProject** — Original Elea kernel base
- **KernelSU-Next Team** — KernelSU-Next
- **Neutron Toolchains** — Neutron Clang
- **rsuntk** — KernelSU manual hook implementation
- **LineageOS** — Kernel base and related work
- **Xiaomi** — Original device and kernel sources

Special thanks to everyone involved in the open-source Android kernel community.

---

## ⚠️ Disclaimer

> **Flash at your own risk.**

Installing a custom kernel modifies the boot/kernel environment of your device.

Always keep a backup of your original boot image before flashing.

The maintainer is not responsible for:

- Bootloops
- Soft-bricks
- Data loss
- Recovery issues
- Hardware damage
- Incorrect flashing
- Incompatible ROM/device configurations

If the device does not boot after flashing, restore your previously backed-up boot image or follow the appropriate recovery procedure for your ROM/device.

---

## 📜 License

This project is based on the Linux kernel and other open-source projects.

Source code remains subject to the licenses of the respective components and projects included in this repository.

---


*Built for `rosemary`.*
