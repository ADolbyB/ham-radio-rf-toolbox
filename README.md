# Ham Radio RF Toolbox
### A New School Solution for Old School Surplus Part 90 Radios

<div align="center">

[![Repo Size](https://img.shields.io/github/repo-size/ADolbyB/ham-radio-rf-toolbox?style=for-the-badge&logo=github&color=blue)](https://github.com/ADolbyB/ham-radio-rf-toolbox)
[![License](https://img.shields.io/github/license/ADolbyB/ham-radio-rf-toolbox?style=for-the-badge)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/ADolbyB/ham-radio-rf-toolbox?style=for-the-badge&logo=github)](https://github.com/ADolbyB/ham-radio-rf-toolbox/commits/main)

**Developed by:** [![ADolbyB](https://img.shields.io/badge/ADolbyB-Profile-blue?style=for-the-badge&logo=github)](https://github.com/ADolbyB)

</div>

---

## 📡 Project Overview

This project provides a modern, automated solution for programming, servicing, and tuning legacy Part 90 commercial radios using publicly available abandonware resources. Born from the need to breathe new life into surplus radio equipment, this toolbox eliminates the headache of maintaining ancient hardware and operating systems.

**The Problem:** Valuable surplus radios collecting dust because the original programming tools require obsolete hardware and unsupported operating systems.

**The Solution:** A dual-boot FreeDOS/Linux system that runs on modern, affordable hardware while maintaining compatibility with legacy radio programming software.

---

## 🎯 Project Requirements

For this project to be considered successful, it must meet these three critical requirements:

| Requirement | Description | Status |
|-------------|-------------|--------|
| **1. Modern Infrastructure** | Use only currently supported operating systems and low-cost/surplus hardware | ✅ In Progress |
| **2. Real Hardware R/W** | Execute Read/Write operations on real surplus radios without VMs or emulators | 🔄 Testing |
| **3. Production Deployment** | Deploy miniaturized production model using current hardware | 📋 Planned |

---

## 🛠️ Supported Radio Equipment

### Motorola Radios
- **Genesis Series** - VHF & UHF Handhelds
- **Jedi Series** - VHF & UHF Handhelds
- **MaxTrac** - Mobile radios
- **M1225** - Mobile radios
- **Spectra Series** - Mobile radios
- **Astro Spectra** - Trunked mobile radios
- **MTS2000** - Portables
- **Astro XTS Series** - Digital portables
- **Astro XTL Series** - Digital mobiles
- **MotoTRBO** - DMR radios

### Kenwood Radios
- **TK-730** - Mobile radios
- **TK-280/380** - Handhelds
- **TK-780/880** - Mobiles
- **TK-290/390** - Handhelds
- **TK-190** - Low band handhelds
- **TK-6110** - Low band mobiles
- **NX Series** - Digital radios

### EF Johnson Radios
- **5100 Series** - P25 Phase 1 FDMA portables
- **5300 Series** - P25 Phase 1 FDMA mobiles

### Other Manufacturers
- **Hytera** - DMR radios

---

## 🗺️ Project Roadmap

### Stage 0.9: Research & Planning ⚡ *Current Stage*
- Research software and hardware solutions
- Budget requirements and time criteria
- Document compatibility requirements
- *All subsequent stages are prospective*

### Stage 1: Prototype Development 🔧
**Objective:** Create and test dual-boot image

**System Configuration:**
- **Partition 1:** [FreeDOS 1.3](https://freedos.org/) - Legacy DOS programming software
- **Partition 2:** [Linux Mint 22.2](https://www.linuxmint.com/download.php) - Modern tools with WINE compatibility

**Why Linux Mint?**
- Smaller image size than Ubuntu 24.04
- Better resource efficiency
- Excellent WINE compatibility for Windows-based programming software

**Testing Objectives:**
- ✅ Clone, compress, and restore partitions on prototype hardware
- ✅ Create comprehensive installation documentation
- ✅ Test compatibility using `install.sh` automation script
- ✅ Validate RIB (Radio Interface Box) and RIBless cable functionality

**RIB Interface Strategy:**
- Kenwood and EF Johnson radios don't require RIB boxes
- Most Motorola software updated for Windows XP+ compatibility
- Linux Mint partition handles newer software via WINE
- Legacy RIB available for testing
- RIBless cables provide alternative connectivity
- DIY solutions available through open-source KiCad designs

**✅ Fulfills Requirement 1:** Modern, supported software with affordable hardware

### Stage 2: Hardware Testing & Debugging 🧪
**Objective:** Validate read/write operations on real radios

**Prototype Hardware:**
- Dell Latitude E6430 i5 laptop
- Port replicator with genuine RS-232 serial port
- Professional programming cables (RIB and RIBless)
- Multiple test radios across manufacturers

**Testing Protocol:**
- Manual software installation and configuration
- Read/write operations on multiple radio models
- Serial communication validation
- Cable compatibility verification

**✅ Fulfills Requirement 2:** Real hardware operations without VM/emulator unreliability

### Stage 3: Production Deployment 🚀
**Objective:** Deploy on compact, modern hardware

**Production Hardware Platform:**
- **Mini PC:** [Beelink MINI S12 Pro](https://www.amazon.com/Beelink-Computers-1000Mbps-Displays-Support/dp/B09J4D6TMG/) or similar
  - Intel N95 processor (amd64/x86_64 architecture)
  - Dual NVMe bays for expansion
  - Small form factor

**Serial Port Solution:**
- **Hardware:** PCIe to dual RS-232 DB9 card
- **Connectivity:** 
  - 1x [NVMe to PCIe Riser Cable](https://www.amazon.com/NGFF-Express-Riser-Speed-Cable/dp/B07KSZ62B8/)
  - 1x [PCIe to RS-232 DB9 Card](https://www.amazon.com/2-Port-Converter-Adapter-Bracket-Desktop/dp/B08F779RTS)
- **Ports:** DE9/DE15 connectors for both RIB and RIBless cables
  - [Beelink MINI S12 Pro](https://www.amazon.com/Beelink-Computers-1000Mbps-Displays-Support/dp/B09J4D6TMG/) or similar already equipped with USB for any current/legacy radio which uses a USB cable.

**Why Not Raspberry Pi?**
❌ **Wrong Architecture:**
- Raspberry Pi: `arm64` (RISC - Reduced Instruction Set Computer)
- **Required:** `amd64/x86_64` (CISC - Complex Instruction Set Computer)
- Legacy radio software compiled for x86 architecture
- ARM emulation introduces compatibility issues

**Software Distribution:**
- Pull from publicly available archives
- Avoid re-hosting proprietary software
- Automated download and installation scripts

**✅ Fulfills Requirement 3:** Modern, supported hardware platform

---

## 📚 Software Archives

All software is sourced from public domain repositories that have existed for years:

| Archive | Content | Platform |
|---------|---------|----------|
| [Archive 1](https://pauhh.planet.ee/programmid/) | MS-DOS software for Motorola & Kenwood | DOS |
| [Archive 2](https://wiki.w9cr.net/index.php/EF_Johnson) | EF Johnson 2-way radio software | Windows |
| [Archive 3](https://wiki.w9cr.net/index.php/Astro_Saber/XTS3000) | Motorola Astro XTS3000 CPS | Windows |
| [Archive 4](https://wiki.w9cr.net/index.php/Astro_Firmware_Upgrades) | Motorola Astro XTS3000 Depot | Windows |
| [Archive 5](https://wiki.w9cr.net/index.php/Astro_Spectra) | Motorola Astro Spectra & Depot | Windows |
| [Archive 6](https://archive.org/download/astro25portablecpsr20.01.00) | Motorola Astro25 Portable CPS | Windows |

---

## 🔧 Additional Ham Radio Tools

### NanoVNA - Vector Network Analyzer

**Project:** [NanoVNA Official Site](https://nanovna.com/)

**Resources:**
- [Using NanoVNA Guide](http://ha3hz.hu/hu/home/top-nav/12-seged-berendezesek/15-nanovna) by HA3HZ
- **Firmware Versions:**
  - [Stock Firmware](https://github.com/hugen79/NanoVNA-H/releases) by hugen79
  - [Enhanced Firmware](https://github.com/DiSlord/NanoVNA-D/releases) by DiSlord

**Special Tools:**
- [NanoVNA_TDR](https://github.com/nuclearrambo/NanoVNA_TDR) - Time Domain Reflectometry
  - Written in Python for desktop analysis
  - [Accurately measuring cable length guide](https://nuclearrambo.com/wordpress/accurately-measuring-cable-length-with-nanovna/)
  - Ideal for measuring electrical lengths of coax cables

### tinySA - Spectrum Analyzer

**Project:** [tinySA Official Wiki](https://tinysa.org/wiki/pmwiki.php?n=Main.HomePage)

**Model Comparison:** [Version Comparison Table](https://www.tinysa.org/wiki/pmwiki.php?n=TinySA4.Comparison)

**Firmware Downloads:**
- [tinySA Basic Firmware](http://athome.kaashoek.com/tinySA/DFU/)
- [tinySA Ultra/Ultra+ Firmware](http://athome.kaashoek.com/tinySA4/DFU/)
  - Models: ZS405, ZS406, ZS407

---

## 🖼️ Project Gallery

### Real-World Application

[![RSS Service: Setting RF Power](img/RSS-Service.jpg)](img/RSS-Service.jpg)

*Setting RF power softpots on a Motorola HT1000 via RSS Service menu using custom CF-27 laptop, Bird 43 wattmeter, and dummy load.*

---

## 📖 Background Story

### The Genesis

This project began with a salvaged Pentium III 500MHz Panasonic CF-27 Toughbook rescued from eBay's junk pile. Built as a custom dual-boot system running:
- **MS-DOS 6.22** with Direct Access 5.19 menu program
- **Windows XP SP3** for radio programming and service

It was the perfect solution for programming surplus commercial radios that friends and fellow hams had accumulated over the years.

### The Problem

As a new ham operator, I wanted the ability to flash and program the collection of surplus radios we'd gathered:
- Vintage Motorola handhelds and mobiles
- Kenwood commercial gear across multiple bands
- EF Johnson P25 equipment
- Modern digital radios (Astro25, MotoTRBO, Hytera DMR)

The old laptop worked brilliantly... until it didn't. Hardware failure was inevitable.

### The Solution

Fortunately, the hard drive was new/old stock (NOS - unopened, never-sold vintage inventory) and survived intact. This project aims to:
1. **Restore** all backup config files, codeplugs, and software
2. **Automate** downloading, installing, and configuring publicly available software
3. **Modernize** the platform using current hardware and supported operating systems
4. **Document** the entire process for the ham community

---

## 🚀 Getting Started

### Prerequisites

**Hardware Requirements:**
- x86_64/amd64 compatible PC (not ARM)
- RS-232 serial port (native or PCIe card)
- Programming cables (RIB or RIBless depending on radio)
- USB drive for installation media

**Software Requirements:**
- FreeDOS 1.3 bootable image
- Linux Mint 22.2 ISO
- Radio programming cables and drivers

### Installation

```bash
# Clone the repository
git clone https://github.com/ADolbyB/ham-radio-rf-toolbox.git
cd ham-radio-rf-toolbox

# Run automated installation script
chmod +x install.sh
./install.sh
```

Detailed installation documentation coming in Stage 1 completion.

---

## 🤝 Contributing

This is an open-source community project. Contributions are welcome!

**Areas for Contribution:**
- Additional radio model support
- Software compatibility testing
- Documentation improvements
- Hardware setup guides
- Cable pinout diagrams

---

## ⚖️ Legal Disclaimer

**Important Notice:**

All software linked in this repository exists in the public domain and has been publicly available for years. I did not upload this software to its current locations, nor do I claim ownership of any proprietary tools.

**If you have concerns** about any linked software, please contact the original hosting parties, not this repository.

This project merely provides:
- Links to existing public archives
- Installation automation scripts
- Hardware compatibility documentation
- Community knowledge sharing

---

## 📋 Project Topics

`motorola` `kenwood` `efjohnson` `linux-mint` `freedos` `radio-service-software` `ham-radio` `part-90` `commercial-radio` `rf-tools` `customer-programming-software`

---

## 📄 License

This project is licensed under the [GPL-3.0 License](LICENSE).

Open source, community-driven, and built for hams by hams.

---

<div align="center">

**73 de ADolbyB**

*Keeping vintage radios alive with modern solutions*

[![GitHub](https://img.shields.io/badge/Follow-ADolbyB-blue?style=for-the-badge&logo=github)](https://github.com/ADolbyB)

</div>