# Module 4 – Troubleshooting PC Hardware

## CompTIA A+ Core 1 (220-1201)

---

## Related Hands-On Lab

After studying the concepts in this module, I completed a practical troubleshooting lab on my Apple M2 MacBook Air to apply the theory in a real-world environment.

➡️ [Module 4 MacBook Air Troubleshooting Lab](https://github.com/eduardo-durigon/endpoint-troubleshooting-labs-2026/tree/main/lab03-module4-troubleshooting-PC-hardware)

The lab includes hardware identification, Disk Utility diagnostics, Startup Options, Safe Mode testing, Activity Monitor analysis, battery health checks, display troubleshooting, audio and camera testing, log analysis, and backup configuration review.

# Overview

This module focused on troubleshooting PC hardware, firmware, boot issues, storage problems, overheating, display problems, and performance-related faults. The lessons covered how BIOS/UEFI initializes hardware, how the boot process works, and how technicians diagnose hardware failures using systematic troubleshooting methods.

The module also explored:

* Secure Boot and TPM
* POST and beep codes
* PSU and power troubleshooting
* Boot sector corruption
* MBR vs GPT
* RAID troubleshooting
* BSOD analysis
* Drive reliability and SMART
* Overheating and thermal issues
* Video/display troubleshooting
* Projector troubleshooting
* Performance bottlenecks

This module strongly emphasized logical troubleshooting processes and real-world diagnostic thinking.

---

# 4.1 BIOS and UEFI

## BIOS and UEFI Fundamentals

Firmware is low-level software stored in flash memory that initializes hardware during startup and prepares the system to load the operating system.

Older systems used:

* BIOS (Basic Input/Output System)

Modern systems primarily use:

* UEFI (Unified Extensible Firmware Interface)

### Advantages of UEFI

* Supports 64-bit operation
* Graphical interface with mouse support
* Faster startup
* Better security features
* Secure Boot support
* Networking support during boot
* Improved partition support using GPT

Some systems can still operate in Legacy BIOS compatibility mode.

---

## Accessing BIOS/UEFI

The firmware setup utility is usually accessed during startup by pressing keys such as:

* Delete
* Esc
* F1
* F2
* F10
* F12

Legacy BIOS interfaces mainly use keyboard navigation, while UEFI interfaces often support mouse input.

---

# 4.1.3 Boot and Device Options

The boot order determines which device the system checks first for boot files.

## Common Boot Devices

### Fixed Disk (HDD/SSD)

* Main operating system storage device
* Modern systems commonly use:

  * SATA SSDs
  * NVMe SSDs
  * M.2 drives

### Optical Drives

* CD/DVD/Blu-ray drives
* Often used for:

  * OS installation
  * recovery tools
  * diagnostics

### USB Devices

* Used for:

  * bootable installers
  * recovery utilities
  * diagnostics

### Network/PXE Boot

* Boots from a server over the network
* Common in enterprise environments

---

# 4.1.4 USB Permissions

UEFI/BIOS can enable or disable USB controllers and ports.

This helps:

* improve security
* restrict unauthorized devices
* prevent malware infections through USB devices

---

# 4.1.5 Fan Considerations and Temperature Monitoring

Cooling systems are critical for maintaining system stability and hardware lifespan.

## Fan Profiles

### Balanced

* Standard cooling profile

### Cool

* Higher fan speeds for maximum cooling

### Quiet

* Lower fan speeds with less noise

### Fanless

* Passive cooling only

### Custom

* User-defined fan curves and temperatures

---

## Temperature Monitoring

### Manual Monitoring

Temperatures can be viewed through BIOS/UEFI sensor menus.

### Third-Party Applications

Monitoring software can:

* track CPU/GPU temperatures
* display fan speeds
* trigger alerts when temperatures exceed safe limits

---

# 4.1.6 Boot Passwords and Secure Boot

## BIOS/UEFI Passwords

### Supervisor/Administrator Password

* Protects BIOS/UEFI settings

### User/System Password

* Prevents the system from booting without authentication

---

## Secure Boot

Secure Boot is a UEFI security feature that ensures only trusted, digitally signed bootloaders are allowed to run.

### Secure Boot Functions

* Prevents rootkits and boot malware
* Verifies bootloader integrity
* Uses cryptographic signatures
* Blocks unsigned or modified bootloaders

Modern operating systems commonly support Secure Boot, including:

* Windows
* Ubuntu
* Fedora
* openSUSE

---

# 4.1.8 Trusted Platform Module (TPM)

A TPM is a hardware security chip that stores:

* encryption keys
* certificates
* passwords
* cryptographic hashes

## TPM Functions

* Supports Secure Boot
* Protects encryption keys
* Prevents unauthorized access
* Provides hardware-based security

TPMs are commonly used with:

* BitLocker
* disk encryption systems
* enterprise security environments

---

# 4.2 Power and Disk Issues

## PSU Fundamentals

The Power Supply Unit (PSU):

* converts AC power to DC power
* powers internal components
* provides stable voltage rails

Common voltages include:

* +3.3V
* +5V
* +12V

---

# 4.2.1 Troubleshooting Power Issues

## Common Symptoms

* PC will not power on
* random shutdowns
* reboot loops
* fans spinning without POST
* no display output

---

## Power Troubleshooting Steps

### 1. Check Other Equipment

Verify the electrical circuit works.

### 2. Test the Wall Socket

Use a known-good device.

### 3. Verify PSU Connections

Ensure all connectors are secure.

### 4. Try Another Power Cable

Faulty cables or fuses can prevent startup.

### 5. Disconnect Extra Devices

Remove non-essential hardware.

### 6. Test the PSU

Use:

* multimeter
* PSU tester

Never open a PSU casing.

---

# 4.2.3 POST Troubleshooting

POST (Power-On Self-Test) checks critical hardware before booting.

Modern systems often hide POST messages behind manufacturer logos.

---

## POST Failure Symptoms

* blank screen
* no beep codes
* continuous beeps
* no boot activity

---

## POST Troubleshooting Steps

### Ask What Changed

Check for:

* firmware updates
* hardware upgrades
* recent maintenance

### Check Cabling and Connections

Verify:

* power cables
* RAM seating
* GPU seating
* storage connections

### Remove Non-Essential Devices

Disconnect unnecessary hardware.

### Test PSU

Fans spinning does not guarantee the PSU works correctly.

### Check CPU and Firmware

Potential causes include:

* faulty CPU
* corrupted firmware
* failed firmware update

---

## Common Beep Codes

| Beep Code             | Meaning                  |
| --------------------- | ------------------------ |
| 1 short beep          | Normal POST              |
| 2 short beeps         | POST error               |
| No beep               | PSU/motherboard issue    |
| Continuous beep       | RAM issue                |
| Repeating short beeps | PSU or motherboard fault |
| 1 long, 1 short       | Motherboard problem      |
| 1 long, 2-3 short     | Video adapter issue      |
| 3 long beeps          | Keyboard issue           |

---

# 4.2.5 Troubleshooting Boot Issues

After POST completes, the firmware searches for a bootable device.

If no valid boot device is found, errors may appear such as:

* Operating System not found
* No bootable device
* Invalid drive specification

---

## Boot Troubleshooting Steps

### Check Boot Order

Ensure the correct drive is prioritized.

### Remove External Media

USB devices may interfere with booting.

### Verify Drive Detection

Check whether drives appear in BIOS/UEFI.

### Check Power and Data Cables

Loose cables commonly cause boot failures.

### Verify SATA/RAID/AHCI Settings

Incorrect storage modes may prevent startup.

### Check NVMe/M.2 Seating

Improper installation can prevent detection.

---

# 4.2.7 Boot Sector Issues

If power and hardware issues are ruled out, the boot sector may be corrupted.

## Causes of Boot Sector Corruption

* malware
* sudden power failure
* disk faults
* corrupted boot files
* incorrect multi-boot installation

---

# MBR vs GPT

## MBR (Master Boot Record)

### Characteristics

* Legacy partitioning system
* Located in first disk sector
* Supports BIOS systems
* Only one active partition
* Limited flexibility

Used with:

* Windows BCD
* Linux GRUB/LILO boot managers

---

## GPT (GUID Partition Table)

### Characteristics

* Modern partitioning system
* Used with UEFI
* More reliable
* Multiple partition tables
* Better redundancy
* More flexible partition management

---

## MBR vs GPT Comparison

| Feature                   | MBR               | GPT                |
| ------------------------- | ----------------- | ------------------ |
| Type                      | Legacy            | Modern             |
| Firmware Support          | BIOS              | UEFI               |
| Partition Info            | First sector only | Multiple locations |
| Reliability               | Lower             | Higher             |
| Flexibility               | Limited           | More flexible      |
| Active Partition Required | Yes               | No                 |

---

# Boot Sector Troubleshooting

## Common Symptoms

* OS not found
* boot device not found
* blank screen during startup
* invalid drive specification

---

## Troubleshooting Steps

### Check Display Connections

A loose monitor cable may appear as a boot failure.

### Inspect Error Messages

Identify whether errors point to:

* MBR corruption
* GPT corruption
* missing boot files

### Use Malware Removal Tools

Bootable antivirus tools can repair infected boot sectors.

### Use OS Recovery Tools

Recovery media can:

* rebuild boot records
* repair startup files
* restore boot configuration

---

# 4.2.8 Troubleshooting OS Errors and Crash Screens

## Blue Screen of Death (BSOD)

BSODs commonly indicate:

* driver failures
* faulty hardware
* corrupted system files
* memory faults
* overheating
* PSU instability

---

## BSOD Troubleshooting

### Scan QR Codes or Error Codes

Use the stop code for research.

### Check Event Viewer

Errors are often logged as:

* BugCheck

### Analyze Memory Dumps

Crash dumps help diagnose system failures.

---

## Other OS Crash Examples

### macOS

* Spinning pinwheel

### Linux

* Kernel panic

---

# 4.2.9 Troubleshooting Drive Availability

## HDD vs SSD Reliability

### HDDs

* mechanical components
* prone to physical wear

### SSDs

* faster and more reliable
* limited write lifespan

---

## Common Drive Failure Symptoms

### Unusual Noises (HDD)

* clicking
* scraping
* grinding

### No Drive Activity LED

Could indicate:

* power issue
* failed drive
* failed RAID array

### Continuous Disk Activity

Possible causes:

* insufficient RAM
* malware
* failing drive

### Read/Write Errors

Examples:

* Cannot read from source disk

May indicate:

* bad sectors
* failing SSD blocks

### Missing Drives

If not detected:

* check Disk Management
* verify initialization
* inspect cables

### BSODs

Drive corruption may cause system crashes.

---

# 4.2.11 SMART Diagnostics

SMART (Self-Monitoring Analysis and Reporting Technology) monitors drive health.

SMART can detect:

* bad sectors
* excessive read/write times
* failing storage mechanisms

---

## Performance Issues Related to Storage

Potential causes include:

* limited free space
* application load
* HDD fragmentation
* bad sectors
* failing SSD blocks

---

# 4.2.12 RAID Failure Troubleshooting

RAID protects data using:

* redundancy
* mirroring
* parity

---

## RAID Failure Scenarios

### Device Failure

A failed drive may degrade the array.

RAID 0 has:

* no redundancy
* complete failure if one drive fails

### Array Failure

Multiple failed drives may destroy the array.

---

## RAID Troubleshooting

### Replace Failed Drives

Many RAID systems support hot swapping.

### Rebuild the Array

Use:

* RAID controller utility
* operating system utility

### Check RAID Utility Status

Verify array integrity.

### Controller Failure

Install a replacement controller or move drives to another compatible system.

---

# 4.3 System and Display Issues

## Troubleshooting Component Issues

Common symptoms include:

* system lockups
* random shutdowns
* reboot loops
* BSODs
* application crashes

---

## Diagnostic Process

### Eliminate Software Causes

Check for:

* malware
* corruption
* driver issues

### Identify Patterns

Determine whether failures are:

* intermittent
* heat-related
* load-related

### Check Power Stability

Verify PSU output.

### Suspect Hardware

Possible hardware causes:

* RAM
* CPU
* motherboard

### Observe Physical Symptoms

Look for:

* overheating
* physical damage
* unusual smells

---

# 4.3.2 Overheating

Excessive heat can damage:

* CPUs
* GPUs
* motherboards
* power supplies

---

## Signs of Overheating

* burning smell
* sudden shutdowns
* fan noise
* instability
* thermal throttling

---

## Overheating Troubleshooting

### Check Temperature Sensors

Use monitoring tools.

### Verify CPU Fan Operation

Ensure fans spin correctly.

### Inspect the Heat Sink

Verify proper contact and thermal paste.

### Clean Dust

Dust buildup restricts airflow.

### Improve Airflow

Use balanced airflow design.

### Check Room Temperature

Hot environments increase thermal problems.

---

# 4.3.3 Physical Damage

## Possible Causes

* ESD
* electrical spikes
* overheating
* careless insertion
* liquid spills
* transport damage

---

## Visible Signs of Damage

### Bent Pins

Common on ports and connectors.

### Swollen Capacitors

May indicate motherboard failure.

### Burn Marks

Can indicate electrical faults.

### Loose Components

Chip creep may occur over time.

---

# 4.3.4 Performance Issues

## Common Causes

* overheating
* misconfiguration
* insufficient RAM
* storage bottlenecks
* software issues
* malware

---

## Troubleshooting Performance Problems

### Monitor Temperatures

Thermal throttling reduces performance.

### Verify Hardware Configuration

Incorrect configurations may reduce speed.

### Compare Against Baselines

Use diagnostic benchmarks.

### Rule Out Software Causes

Check operating system and applications.

---

## Bottlenecks

A bottleneck occurs when one component limits system performance.

Examples:

* slow HDD with modern CPU
* insufficient RAM
* limited PCIe bandwidth
* poor NVMe configuration

---

# 4.3.5 Incorrect System Date and Time

Incorrect date/time settings may cause:

* authentication failures
* scheduling issues
* network problems

---

## RTC and CMOS Battery

The Real-Time Clock (RTC) uses a coin-cell battery, commonly:

* CR2032

Modern systems store configuration data in:

* NVRAM
* flash memory

---

# 4.3.6 Missing Video Issues

## Basic Troubleshooting

### Verify Monitor Power

Ensure the display is powered on.

### Check Input Source

Select the correct:

* HDMI
* DisplayPort
* DVI
* VGA input

### Check Cables

Inspect for:

* loose connections
* bent pins
* cable damage

### Test with Known-Good Components

Swap cables or monitors.

---

## Compatibility Issues

Modern displays may require:

* HDMI 2.1
* DisplayPort 1.4
* high-speed HDMI cables
* USB-C compatibility

---

# Projector Troubleshooting

## Burned-Out Bulbs

Symptoms include:

* dim image
* flickering
* projector warnings
* popping sounds

Modern LED and laser projectors reduce bulb failures.

---

## Intermittent Shutdowns

Common causes include:

* overheating
* blocked vents
* fan failure
* firmware problems

---

# 4.3.7 Troubleshooting Video Quality Issues

## Dim Image

Possible causes:

* low brightness
* failed backlight
* power-saving modes

---

## Fuzzy Image

Often caused by incorrect resolution settings.

Use the monitor's native resolution.

---

## Flashing/Flickering Screen

Possible causes:

* loose cables
* failing backlight
* failing GPU
* overheating video card

---

## Dead or Stuck Pixels

### Stuck Pixel

* permanently lit

### Dead Pixel

* black/non-functional

---

## Display Burn-In

Static images displayed too long may leave permanent ghost images.

More common on:

* OLED
* plasma displays

---

## Incorrect Color Display

Possible causes:

* faulty cables
* poor calibration
* graphics adapter issues

---

## Audio Issues

HDMI and DisplayPort carry audio signals.

DVI and VGA do not.

Check:

* audio output settings
* speaker power
* volume controls

---

## Sizing Issues

Incorrect scaling may cause:

* stretched images
* black borders
* compressed display

Adjust:

* display resolution
* monitor OSD settings

---

# Important Exam Notes

## Key Terms

| Term  | Meaning                                           |
| ----- | ------------------------------------------------- |
| BIOS  | Basic Input/Output System                         |
| UEFI  | Unified Extensible Firmware Interface             |
| POST  | Power-On Self-Test                                |
| TPM   | Trusted Platform Module                           |
| MBR   | Master Boot Record                                |
| GPT   | GUID Partition Table                              |
| BSOD  | Blue Screen of Death                              |
| SMART | Self-Monitoring Analysis and Reporting Technology |
| RAID  | Redundant Array of Independent Disks              |

---

# Key Takeaways

* UEFI provides better security and flexibility than legacy BIOS.
* Secure Boot helps prevent boot-level malware.
* TPM stores encryption keys securely in hardware.
* POST errors and beep codes help diagnose startup failures.
* MBR is legacy while GPT is the modern partitioning standard.
* SMART diagnostics help predict drive failures.
* Overheating is a major cause of instability and hardware damage.
* Troubleshooting should always follow a logical step-by-step process.
* Many display issues are caused by simple cable or configuration problems.
* RAID improves redundancy but does not replace backups.

---

# Reflection

This module significantly improved my understanding of how computers boot, initialize hardware, and recover from hardware or operating system failures. I learned how BIOS/UEFI, Secure Boot, TPM, POST, storage systems, and power supplies work together to maintain system stability and security.

The troubleshooting sections helped me think more like a technician by focusing on systematic diagnostics, isolating causes, checking hardware step-by-step, and identifying patterns in failures. I also gained a much better understanding of storage reliability, RAID recovery, overheating, display troubleshooting, and performance bottlenecks.

Overall, this module reinforced the importance of logical troubleshooting methods, preventive maintenance, and understanding both hardware and firmware interactions in modern computer systems.
