# Module 3 – Installing System Devices

## Topics Covered

* Power Supply Units (PSUs)
* Wattage and PSU efficiency
* 80 Plus certifications
* Redundant power supplies
* Cooling systems and thermal management
* Fans, heat sinks, and liquid cooling
* Storage devices (HDDs, SSDs, NVMe)
* RAID configurations
* Flash memory and SD cards
* Optical drives
* System memory and RAM technologies
* DDR generations and memory channels
* ECC memory
* CPU architecture
* x86/x64 and ARM processors
* CPU sockets and installation
* Chipsets and motherboard compatibility
* Virtualization technologies

---

# 3.1 Power Supply Units (PSUs)

## 3.1.1 PSU Functions

The Power Supply Unit (PSU) converts alternating current (AC) from a wall outlet into low-voltage direct current (DC) used by computer components.

### Main PSU Components

* Rectifier
* Transformers
* Voltage regulators
* Cooling fan
* Power rails

### Important Notes

* Most desktop PSUs follow the ATX form factor.
* North America commonly uses 120 VAC.
* Many other countries use 230 VAC.
* Modern PSUs are usually dual-voltage and auto-switching.

### Key Concept

A PSU must provide stable and sufficient power for all connected hardware components.

---

# 3.1.2 PSU Wattage Ratings

Power is measured in watts (W).

## Formula

* Voltage × Current = Wattage (V × I)

### Typical PSU Ratings

| System Type        | Typical Wattage |
| ------------------ | --------------- |
| Standard Desktop   | 400–500W        |
| Gaming PC          | 600W+           |
| Workstation/Server | 800W–1000W+     |

### Risks of an Underpowered PSU

* Random shutdowns
* System instability
* Reboots and crashes
* Hardware overheating
* Component damage

### Important Note

Modern systems rely heavily on the +12V rail because CPUs and GPUs consume most of their power from it.

---

# 3.1.3 Power Rails

PSUs distribute power through different voltage rails.

| Rail        | Purpose                |
| ----------- | ---------------------- |
| +3.3V       | Motherboard logic      |
| +5V         | Legacy devices         |
| +12V        | CPU, GPU, fans         |
| -12V        | Legacy serial hardware |
| +5V Standby | Sleep/wake functions   |

---

# 3.1.4 PSU Efficiency

Efficiency measures how effectively the PSU converts AC power into DC power.

### Example

A 300W PSU operating at 75% efficiency draws approximately 400W from the wall.

### Effects of Low Efficiency

* Increased heat
* Higher electricity costs
* Greater cooling requirements

---

# 3.1.5 80 Plus Certifications

The 80 Plus certification system measures PSU efficiency.

| Certification | Efficiency |
| ------------- | ---------- |
| Bronze        | ~82–85%    |
| Silver        | ~85–88%    |
| Gold          | ~87–90%    |
| Platinum      | ~90–92%    |
| Titanium      | Up to 94%+ |

### Benefits

* Reduced heat output
* Lower energy consumption
* Better reliability
* Longer hardware lifespan

---

# 3.1.6 Modular Power Supplies

## Types

### Non-Modular PSU

* All cables permanently attached

### Semi-Modular PSU

* Some detachable cables

### Fully Modular PSU

* All cables detachable

### Advantages of Modular PSUs

* Better cable management
* Improved airflow
* Easier maintenance
* Cleaner builds

---

# 3.1.7 Redundant Power Supplies

Redundant PSUs are commonly used in servers and enterprise systems.

### Benefits

* Increased uptime
* Fault tolerance
* Continuous operation if one PSU fails

---

# 3.1.8 PSU Connectors

## Common PSU Connectors

| Connector   | Purpose           |
| ----------- | ----------------- |
| 24-pin ATX  | Motherboard power |
| 4/8-pin EPS | CPU power         |
| PCIe        | GPU power         |
| SATA Power  | SSD/HDD power     |
| Molex       | Legacy devices    |

---

# 3.1.9 Cooling Systems

Computer components generate heat that must be removed efficiently.

### Cooling Goals

* Prevent overheating
* Maintain performance
* Improve hardware lifespan

---

# 3.1.10 Heat Sinks and Thermal Paste

## Heat Sinks

Metal cooling devices attached to CPUs or GPUs.

### Types

* Passive heat sinks
* Active heat sinks (fan-assisted)

## Thermal Paste

Applied between the CPU and cooler to improve heat transfer.

### Important Notes

* Too little paste reduces cooling efficiency.
* Too much paste can reduce performance.

---

# 3.1.11 Fans and Airflow

## Fan Placement

* Front fans → intake
* Rear/top fans → exhaust

### Important Concepts

* Positive airflow reduces dust buildup.
* Clean fans regularly.
* Fan failures can cause overheating.

---

# 3.1.12 Liquid Cooling Systems

Liquid cooling is used in high-performance systems.

## Components

* Water block
* Pump
* Radiator
* Tubing
* Reservoir

### Advantages

* Better cooling efficiency
* Lower temperatures
* Reduced noise

### Disadvantages

* More expensive
* More maintenance
* Risk of leaks

---

# 3.2 Storage Devices

## 3.2.1 Storage Types

### HDD (Hard Disk Drive)

Mechanical storage using spinning platters.

### SSD (Solid State Drive)

Flash-based storage with no moving parts.

### NVMe SSD

High-speed SSD using PCIe lanes.

---

# HDD Characteristics

### Advantages

* Large capacities
* Lower cost per GB

### Disadvantages

* Slower speeds
* Mechanical wear
* More heat/noise

### Typical RPM Speeds

| RPM         | Performance                 |
| ----------- | --------------------------- |
| 5400 RPM    | Basic storage               |
| 7200 RPM    | Standard desktop            |
| 10,000+ RPM | Enterprise/high-performance |

---

# SSD Characteristics

### Advantages

* Faster boot times
* Lower power usage
* Silent operation
* Better durability

### Disadvantages

* Higher cost per GB
* Limited write endurance

---

# 3.2.2 SATA and NVMe

## SATA SSD

* Uses SATA interface
* Maximum ~600 MB/s

## NVMe SSD

* Uses PCIe lanes
* Much faster than SATA
* Lower latency

### PCIe Speeds

| PCIe Version | Approx Speed |
| ------------ | ------------ |
| PCIe 4.0     | ~16 GT/s     |
| PCIe 5.0     | ~32 GT/s     |

---

# 3.2.3 M.2 Drives

M.2 is a compact SSD form factor.

### Common Sizes

* 2230
* 2242
* 2260
* 2280

### Advantages

* No cables required
* Smaller size
* High performance

---

# 3.2.4 RAID

RAID = Redundant Array of Independent Disks

RAID improves:

* Redundancy
* Performance
* Fault tolerance

---

# RAID Levels

| RAID Level | Description             |
| ---------- | ----------------------- |
| RAID 0     | Striping, no redundancy |
| RAID 1     | Mirroring               |
| RAID 5     | Striping + parity       |
| RAID 6     | Double parity           |
| RAID 10    | RAID 1 + RAID 0         |

### Important Notes

* RAID 0 improves speed but has no fault tolerance.
* RAID 1 duplicates data for redundancy.
* RAID 5 requires at least 3 drives.
* RAID 6 can survive two drive failures.
* RAID 10 provides excellent speed and redundancy.

---

# 3.2.5 Removable Storage

## Examples

* USB flash drives
* External HDDs
* External SSDs
* NAS devices

---

# 3.2.6 Flash Memory and SD Cards

## SD Card Types

| Type | Maximum Capacity |
| ---- | ---------------- |
| SD   | Up to 2GB        |
| SDHC | Up to 32GB       |
| SDXC | Up to 2TB        |
| SDUC | Up to 128TB      |

### Speed Standards

| Standard | Speed          |
| -------- | -------------- |
| UHS-I    | Up to 104 MB/s |
| UHS-II   | Up to 312 MB/s |
| UHS-III  | Up to 624 MB/s |

---

# 3.2.7 Optical Drives

## Formats

| Format  | Capacity    |
| ------- | ----------- |
| CD      | Up to 700MB |
| DVD     | 4.7GB–17GB  |
| Blu-ray | 25GB+       |

### Media Types

* Read-only
* Recordable
* Rewritable

---

# 3.3 System Memory

## 3.3.1 RAM Overview

RAM temporarily stores data actively used by the CPU.

### Important Notes

* RAM is volatile memory.
* Data is lost when power is removed.

---

# 3.3.2 RAM Types

## DRAM

Dynamic RAM requiring periodic refresh.

## SRAM

Faster memory typically used for CPU cache.

---

# 3.3.3 DDR Memory

DDR = Double Data Rate

### DDR Generations

| Type | Speed Range    |
| ---- | -------------- |
| DDR  | 200–400 MT/s   |
| DDR2 | 400–1066 MT/s  |
| DDR3 | 800–2133 MT/s  |
| DDR4 | 1600–3200 MT/s |
| DDR5 | 4800+ MT/s     |

---

# 3.3.4 DIMM and SODIMM

## DIMM

Desktop memory modules.

## SODIMM

Smaller laptop memory modules.

---

# 3.3.5 Memory Channels

## Single Channel

* One memory path

## Dual Channel

* Two memory paths
* Improved bandwidth

## Triple/Quad Channel

* Higher-end systems
* Increased memory performance

---

# 3.3.6 ECC Memory

ECC = Error Correcting Code memory

### Purpose

Detects and corrects memory errors.

### Common Usage

* Servers
* Workstations
* Enterprise systems

---

# 3.4 CPU Architecture

## 3.4.1 CPU Operation

The CPU performs four basic operations:

1. Fetch
2. Decode
3. Execute
4. Write-back

### Key Components

* ALU (Arithmetic Logic Unit)
* FPU (Floating Point Unit)
* Cache memory
* Registers

---

# 3.4.2 Cache Levels

| Cache Level | Description      |
| ----------- | ---------------- |
| L1          | Fastest/smallest |
| L2          | Larger/slower    |
| L3          | Shared cache     |

---

# 3.4.3 x86 and x64

## x86

* 32-bit architecture

## x64

* 64-bit architecture
* Supports more RAM
* Better performance

---

# 3.4.4 ARM Architecture

ARM processors use a RISC architecture optimized for:

* Low power consumption
* Mobile devices
* Efficiency

### Common ARM Devices

* Smartphones
* Tablets
* Apple Silicon Macs

---

# RISC vs CISC

| RISC                     | CISC                      |
| ------------------------ | ------------------------- |
| Simpler instructions     | More complex instructions |
| Lower power usage        | Higher compatibility      |
| Efficient/mobile systems | General-purpose computing |

---

# 3.4.5 Multicore CPUs and SMT

## Multicore CPUs

Multiple cores on one processor.

## SMT / Hyper-Threading

Allows a single core to process multiple threads simultaneously.

### Benefits

* Better multitasking
* Improved workload efficiency

---

# 3.4.6 Virtualization

Virtualization allows multiple virtual machines (VMs) to run on one physical system.

## Technologies

| Vendor | Technology |
| ------ | ---------- |
| Intel  | VT-x       |
| AMD    | AMD-V      |

### Common Uses

* Testing environments
* Servers
* Cloud computing

---

# 3.4.7 CPU Socket Types

## Intel

### LGA (Land Grid Array)

Pins located on motherboard socket.

## AMD

### PGA (Pin Grid Array)

Pins located on CPU.

---

# Common Socket Examples

| Platform            | Socket    |
| ------------------- | --------- |
| Intel 10th/11th Gen | LGA 1200  |
| Intel 12th Gen+     | LGA 1700  |
| AMD Ryzen           | AM4 / AM5 |

---

# 3.4.8 CPU Installation

## Installation Steps

1. Align CPU correctly
2. Secure locking mechanism
3. Apply thermal paste
4. Install cooler
5. Connect CPU fan header

### Important Reminder

Bent pins or incorrect alignment can permanently damage components.

---

# 3.4.9 Chipsets and Motherboard Compatibility

Motherboard chipsets determine:

* CPU compatibility
* RAM support
* PCIe lanes
* Overclocking features
* Expansion support

### Examples

* Intel Z-series chipsets
* AMD X-series chipsets

---

# 3.4.10 Desktop, Server, and Mobile CPUs

## Desktop CPUs

Focused on general performance and gaming.

## Server CPUs

Optimized for:

* Reliability
* ECC memory
* Heavy multitasking
* Large core counts

## Mobile CPUs

Designed for:

* Battery efficiency
* Lower heat output
* Compact systems

---

# Key Takeaways

* PSUs provide stable DC power to computer components and must match system power requirements.
* Efficient cooling systems are essential for maintaining hardware stability and performance.
* SSDs and NVMe drives provide major speed improvements over traditional HDDs.
* RAID configurations improve redundancy, performance, or both depending on the level used.
* Modern RAM technologies greatly improve memory bandwidth and system performance.
* CPU architecture impacts efficiency, power usage, compatibility, and performance.
* ARM processors dominate mobile devices due to efficiency, while x86/x64 remain common in desktops and servers.
* Proper CPU installation, thermal management, and motherboard compatibility are critical for system stability.

---

# Reflection

This module greatly expanded my understanding of how modern computer hardware operates together as a complete system. I learned how power delivery, cooling, storage, memory, and CPU architecture all directly affect system performance, reliability, and efficiency.

One of the most valuable topics for me was understanding the differences between HDDs, SSDs, NVMe drives, and RAID configurations, as well as how modern CPUs use multicore processing, cache memory, and virtualization technologies to improve performance.

I also gained a better understanding of system memory technologies such as DDR generations, memory channels, and ECC RAM, along with the importance of selecting compatible motherboards, chipsets, and CPU sockets during upgrades or system builds.

This module helped connect many hardware concepts together and gave me a much clearer picture of how computers are designed, optimized, and maintained in both consumer and enterprise environments.

## Related Lab

This module includes a hands-on hardware analysis lab completed on an Apple M2 MacBook Air.

➡️ **View the lab:** [Module 3 – Computer Hardware and Architecture Analysis](https://github.com/eduardo-durigon/endpoint-troubleshooting-labs-2026/tree/main/lab02-module3-hardware-architecture)
