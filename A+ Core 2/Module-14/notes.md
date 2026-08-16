# CompTIA A+ Core 2 – Module 14: Supporting and Troubleshooting Windows

## What I Studied

Module 14 focused heavily on **supporting, monitoring, recovering, and troubleshooting Windows systems**.

This module brought together many of the Windows tools covered previously and applied them to real troubleshooting situations, including:

- Remote support and file sharing
- Windows system information and logging
- Task Manager and performance monitoring
- Resource Monitor and Performance Monitor
- Startup processes and services
- Windows boot processes
- Windows Recovery Environment (WinRE)
- System Restore and restore points
- System images and Windows reinstallation
- Boot failures and black screens
- Performance problems
- BSODs and system instability
- USB troubleshooting
- Application and service failures
- Time synchronization problems

A major theme throughout the module was learning to **identify where a failure is occurring before attempting to fix it**.

---

# Key Concepts

## 1. Remote Support and File Sharing

Windows provides several ways to transfer files and remotely support users.

### Nearby Sharing

**Nearby Sharing** allows Windows devices to transfer files using:

- Bluetooth for discovery/pairing
- Wi-Fi for the actual file transfer

Because nearby sharing can potentially expose a device to unsolicited transfer requests, connections should only be accepted from trusted devices.

### VPN and Remote Access

A **Virtual Private Network (VPN)** creates an encrypted tunnel between a local device and a remote network.

A VPN can provide an additional security layer before establishing a remote connection.

For example:

1. Establish a VPN connection to the organization's network.
2. Connect to an internal system using Remote Desktop.
3. The Remote Desktop service does not need to be directly exposed to the public Internet.

---

## 2. System Information

The Windows **System Information** utility can be launched using:

`msinfo32.exe`

It provides a detailed inventory of the system, including:

- Hardware components
- Software environment
- System resources
- Firmware and OS versions
- Driver information
- Environment variables
- Network status

This is useful when gathering information before beginning troubleshooting.

---

## 3. Event Viewer

**Event Viewer** (`eventvwr.msc`) provides access to Windows event logs.

The four main Windows logs are:

- **System** – OS, driver, hardware, and system service events
- **Application** – Application and third-party software events
- **Security** – Security auditing and authentication events
- **Setup** – Installation and configuration events

Additional application-specific logs are available under **Applications and Services Logs**.

### Event Severity Levels

Events can be categorized as:

- **Critical** – Severe failures requiring immediate attention
- **Error** – Problems that should be investigated
- **Warning** – Conditions that may develop into problems
- **Information** – Normal or noteworthy system activity
- **Audit Success/Failure** – Security-related successes or failures

Event Viewer is especially useful when troubleshooting problems that leave behind an error, warning, or event ID that can be investigated further.

---

## 4. Task Manager

Task Manager is one of the first tools available for checking system performance.

It can be opened using:

`Ctrl + Shift + Esc`

Task Manager allows you to:

- View running processes
- Examine CPU usage
- Monitor memory
- Monitor disk activity
- Monitor network activity
- View GPU utilization
- Identify resource-heavy applications
- End unresponsive processes
- Manage startup applications
- View logged-in users
- Examine Windows services

The **Details** tab provides additional information about processes and allows process priority to be changed.

Changing priority can affect how CPU resources are allocated, but this should be done carefully.

---

## 5. Performance Monitoring in Task Manager

The **Performance** tab provides real-time information about the major system resources.

### Disk Monitoring

Useful statistics include:

- Active time
- Response time
- Read/write speed
- Disk capacity

High disk utilization combined with slow response times can indicate:

- Slow or failing storage
- Excessive paging
- File/cache corruption
- Bad sectors
- Heavy background activity

### Network Monitoring

Task Manager can display:

- Send throughput
- Receive throughput
- IP address
- MAC address
- SSID
- Connection type
- Signal strength

This provides a quick way to determine whether the network adapter is active and how heavily it is being used.

### CPU Monitoring

CPU information includes:

- Number of cores
- Logical processors
- Hyper-Threading
- Virtualization status
- CPU utilization
- Processes
- Threads
- Handles
- System uptime

A short spike in CPU utilization is not necessarily a problem.

**Sustained high utilization** is much more important when diagnosing performance problems.

### GPU Monitoring

GPU monitoring provides information such as:

- GPU utilization
- Dedicated graphics memory
- Graphics workload

---

## 6. Memory Monitoring

Task Manager also provides detailed RAM statistics.

Important values include:

### In Use

The amount of physical RAM currently being used.

### Committed

The amount of virtual memory requested compared with the total amount available from RAM and the page file.

### Cached

Frequently accessed data kept in memory to improve performance.

### Paged Pool

Kernel memory that can be moved to the page file.

### Non-Paged Pool

Kernel memory that must remain in physical RAM.

High RAM utilization alone does not necessarily mean the system has a problem.

However, excessive **page file activity** can indicate memory pressure and can significantly reduce performance.

---

## 7. Startup Processes and Services

The **Startup** section of Task Manager can be used to disable unnecessary applications that launch automatically.

Startup applications can affect:

- Boot time
- Memory usage
- CPU utilization
- Overall system responsiveness

The **Services** section displays background services running on Windows.

Services can support functions such as:

- Authentication
- Networking
- File indexing
- Security software
- Backup software
- Databases

Services may be configured with different startup behaviors.

Changing or disabling services requires caution because one service may depend on another.

---

## 8. Resource Monitor and Performance Monitor

Task Manager provides a quick overview, but Windows includes more advanced monitoring tools.

### Resource Monitor

Resource Monitor can be launched using:

`resmon.exe`

It provides more detailed information about resource activity than Task Manager, helping identify which processes are responsible for:

- CPU activity
- Memory usage
- Disk activity
- Network activity

### Performance Monitor

Performance Monitor can be launched using:

`perfmon.exe`

It provides real-time performance charts and can collect data over longer periods.

This is useful because some performance problems cannot be diagnosed from a single snapshot.

Performance Monitor can create **Data Collector Sets** to establish a performance baseline.

Two important types of logs are:

- **Counter logs** – Collect resource statistics over time
- **Trace logs** – Capture detailed service and system activity

---

## 9. Performance Counters

Performance Monitor organizes metrics into **objects, counters, and instances**.

Useful counters include:

### Processor – % Processor Time

Measures processor utilization.

Sustained utilization above approximately **85%** may indicate a CPU bottleneck.

### Processor – % Privileged Time

Measures CPU time spent executing kernel-mode operations.

Unusually high privileged time can point toward problems involving drivers or hardware.

### Physical Disk – % Disk Time

Shows how heavily a disk is being used.

Sustained high values can indicate a storage bottleneck.

### Physical Disk – Average Disk Queue Length

Shows outstanding disk requests.

High queue length combined with high disk utilization can indicate disk performance problems.

### Memory – Available Bytes

Shows available physical memory.

A continuous decline can indicate a possible memory leak.

### Memory – Pages/sec

Measures page reads and writes used to resolve hard page faults.

Paging is normal, but excessive paging can indicate memory pressure.

### Paging File – % Usage

Shows how much of the page file is currently being used.

Performance counters should always be interpreted **together rather than in isolation**.

For example, low available memory combined with heavy paging and high disk activity provides much stronger evidence of memory pressure than any single counter alone.

---

## 10. System Configuration

The **System Configuration** utility can be opened using:

`msconfig.exe`

It is primarily useful for diagnostic startup and troubleshooting.

Startup options include:

- **Normal startup**
- **Diagnostic startup**
- **Selective startup**

Other options allow configuration of:

- Boot settings
- Safe Mode
- Services
- Administrative tools

`msconfig` is particularly useful when attempting to isolate whether a startup component or service is causing a problem.

---

# Windows Boot and Recovery

## 11. Windows Boot Process

Understanding the Windows boot process helps determine **where a boot failure is occurring**.

### Legacy BIOS / MBR

The basic sequence is:

1. Firmware performs POST.
2. Firmware identifies the boot device.
3. BIOS reads the **Master Boot Record (MBR)**.
4. The boot sector loads Windows Boot Manager.
5. `BOOTMGR` reads the **Boot Configuration Data (BCD)**.
6. Windows Boot Manager launches the Windows boot loader.
7. `WINLOAD.EXE` loads the Windows kernel.
8. Windows initializes drivers and system processes.
9. The system reaches authentication/logon.

### UEFI / GPT

With UEFI systems:

1. Firmware performs POST.
2. UEFI reads the **GUID Partition Table (GPT)**.
3. The **EFI System Partition** is located.
4. Windows Boot Manager is loaded from the EFI partition.
5. `BOOTMGFW.EFI` reads the BCD.
6. `WINLOAD.EFI` continues loading Windows.

Understanding whether a machine uses BIOS/MBR or UEFI/GPT is important because some repair techniques apply only to one configuration.

---

## 12. Advanced Startup and Safe Mode

Windows Advanced Startup provides access to troubleshooting and recovery options.

In Windows 11 it can be accessed through:

**Settings → System → Recovery → Advanced startup**

From the recovery environment:

**Troubleshoot → Advanced options → Startup Settings**

Safe Mode loads Windows using only essential drivers and services.

This makes it useful for determining whether a problem is caused by:

- Third-party software
- Drivers
- Startup applications
- Background services

---

## 13. Windows Recovery Environment

If Windows cannot boot normally, the **Windows Recovery Environment (WinRE)** provides several repair options.

These can include:

- Startup Repair
- System Restore
- System Image Recovery
- Startup Settings
- Command Prompt
- Reset this PC

The recovery command prompt can also provide access to troubleshooting utilities such as:

`diskpart`

`chkdsk`

`sfc`

`bootrec`

`bcdedit`

---

## 14. System Restore

System Restore allows Windows configuration changes to be rolled back to an earlier restore point.

Restore points can protect system components such as:

- Registry configuration
- Drivers
- Installed applications
- System settings

System Restore generally does **not** restore or delete normal user data files.

Restore points may be created automatically during significant system changes, or they can be created manually.

### PowerShell

System Restore can also be managed using PowerShell.

Example:

`Enable-ComputerRestore -Drive "C:\"`

A restore point can be created using the `Checkpoint-Computer` cmdlet.

Restore point types include situations such as:

- Application installation
- Application removal
- System setting changes
- Device driver installation

---

## 15. Volume Shadow Copy Storage

Windows uses **Volume Shadow Copy** storage for technologies including System Restore.

The `vssadmin` utility can be used to manage shadow copy storage.

Example:

`vssadmin resize shadowstorage /on=C: /for=C: /maxsize=5%`

This configures the maximum storage space available for shadow copies.

---

## 16. Driver and Update Rollback

If a problem begins immediately after an update, the change itself may be responsible.

Windows provides several rollback options.

### Windows Updates

Installed updates can be removed through Windows update history when necessary.

### Device Drivers

Device Manager provides a **Roll Back Driver** option when a newly installed driver causes problems.

This can be particularly useful when a newer driver:

- Is unstable
- Is incompatible
- Introduces performance problems
- Causes system crashes

---

## 17. Recovery Images and Windows Reinstallation

A **system image** provides a complete backup of system configuration and data at the time the image was created.

System images can be restored through Windows recovery tools.

If recovery options are unsuccessful, Windows can also be reinstalled using **Reset this PC**.

Options include:

### Keep my files

Reinstalls Windows while preserving user files.

### Remove everything

Removes user data and applications and performs a more complete reset.

When transferring ownership of a PC, secure removal of data is preferable to a simple reset.

---

# Troubleshooting Windows

## 18. Boot Failures

Boot troubleshooting should begin by determining **how far the system progresses through the boot process**.

### No Boot Device / Invalid Boot Disk

Possible causes include:

- Incorrect boot order
- Removable media being selected
- Drive connection problems
- Failing storage
- Incorrect firmware configuration

The first steps include:

- Remove unnecessary removable media
- Check BIOS/UEFI boot order
- Verify that the storage device is detected
- Check physical connections
- Run storage diagnostics

### No Operating System Found

If the disk is detected but Windows cannot be located, possible causes include:

- Boot configuration corruption
- Damaged boot files
- File system corruption
- Storage failure

Useful tools include:

`chkdsk`

`bootrec`

`diskpart`

Examples of boot repair commands include:

`bootrec /fixmbr`

`bootrec /fixboot`

`bootrec /rebuildbcd`

`/fixmbr` should not be used as an MBR repair technique on GPT-based installations.

---

## 19. Black Screen and GUI Failures

If Windows appears to boot but does not successfully display the desktop, possible causes include:

- Graphics driver corruption
- System file corruption
- Failed updates
- Incorrect boot configuration

If Windows works in **Safe Mode**, the graphics driver or another non-essential startup component becomes a likely suspect.

Useful troubleshooting steps include:

- Boot into Safe Mode
- Reinstall or roll back the graphics driver
- Run `chkdsk`
- Run `sfc`
- Allow Windows updates sufficient time to finish
- Check for known issues

The keyboard shortcut:

`Windows + Ctrl + Shift + B`

can restart the graphics driver if Windows is still responsive.

---

## 20. Slow Startup and User Profile Problems

Slow Windows startup can be caused by:

- Drivers
- Services
- Network configuration
- File corruption
- Startup applications

If Windows itself loads normally but the desktop becomes slow after sign-in, the problem may be related to the **user profile**.

`NTUSER.DAT` contains user-specific Registry settings and can become corrupted.

A damaged local profile may require creating a new account and migrating the user's files while excluding corrupted profile-specific files.

---

## 21. Troubleshooting Performance Problems

A useful performance troubleshooting process is:

1. Open Task Manager.
2. Determine whether CPU, memory, disk, or another resource is heavily utilized.
3. Identify the process responsible.
4. Determine whether the activity is expected.
5. Wait for legitimate background activity to complete.
6. Restart a stuck service or terminate an unresponsive process if necessary.
7. Reboot if the problem continues.
8. Investigate recurring problems rather than repeatedly restarting the system.

Common causes of performance problems include:

- Windows Update
- Search indexing
- Security scans
- Insufficient RAM
- Excessive paging
- Low disk space
- Startup applications
- Malware
- Slow storage
- Power-management problems

Possible corrective actions include:

- Install updates
- Update hardware drivers
- Remove unnecessary startup applications
- Free disk space
- Check for malware
- Verify system requirements
- Add hardware resources when necessary
- Use SSD storage rather than HDD storage where appropriate

Performance problems should be diagnosed from **resource evidence**, rather than assuming that a slow computer automatically needs more RAM or a faster CPU.

---

## 22. BSOD and System Faults

A **Blue Screen of Death (BSOD)** represents a Windows stop error.

Common causes include:

- Faulty drivers
- Faulty hardware
- Memory problems
- File system corruption
- Overheating
- Recently installed software
- Recently installed hardware

Troubleshooting can include:

- System Restore
- Driver rollback
- Update rollback
- Removing recently installed hardware/software
- Hardware diagnostics
- `chkdsk`
- Malware scanning
- Checking temperatures and airflow
- Recording the stop code

If Windows automatically restarts before the stop code can be read, automatic restart can be disabled through advanced startup/recovery settings.

---

## 23. System Instability and Unexpected Shutdowns

A system that freezes, restarts, shuts down, or powers off unexpectedly may have:

- Overheating problems
- Power problems
- CPU problems
- Chipset problems
- RAM failures
- Corrupted system files

Windows Memory Diagnostic can help test system memory.

If memory errors occur, RAM modules can be tested individually to identify a faulty module.

System file and disk checks can include:

`chkdsk`

`sfc /verifyonly`

and, when repairs are required:

`sfc /scannow`

---

## 24. USB Troubleshooting

USB problems can involve:

- Drivers
- USB host controllers
- Power management
- Hubs
- Too many connected devices

Troubleshooting steps can include:

1. Update chipset and USB controller drivers.
2. Remove/reinstall USB host controllers through Device Manager.
3. Disable USB selective suspend when investigating power-related problems.
4. Reduce the number of connected devices.
5. Test devices individually.

An unpowered USB hub can also cause resource or power problems when too many devices are attached.

---

## 25. Application Crashes

When an application crashes, preserving unsaved data should be the first priority when possible.

Troubleshooting can include:

- Allow the application time to recover
- End the process if necessary
- Check Event Viewer
- Determine whether a particular file triggers the crash
- Check for application-specific updates
- Reinstall the application if necessary

Application updates may be separate from Windows Update, so the software vendor may need to be checked directly.

---

## 26. Services Not Starting

If Windows reports that a service failed to start:

- Check Event Viewer
- Check the Services console
- Attempt to restart the service
- Verify service dependencies
- Verify account permissions
- Verify service credentials
- Check system files
- Scan for malware

For application-related services, reinstalling the application may resolve damaged components.

`regsvr32` can also be used when troubleshooting software components that rely on DLL registration.

Orphaned startup entries can remain after incomplete software removal and may need to be investigated using system configuration or Registry tools.

---

## 27. Time Drift

Accurate time synchronization is important for services such as:

- Authentication
- Network access
- Backups
- Logging

The motherboard contains a battery-powered real-time clock, but individual PCs should not be treated as authoritative time sources.

Network systems should synchronize against reliable time sources.

In a domain environment, systems should use a consistent time hierarchy so that servers and clients remain synchronized.

Significant clock differences can cause authentication and other network services to fail.

---

# Hands-On Labs Completed

During Module 14, I completed several hands-on labs focused on Windows support and troubleshooting.

### Applied Live Labs

- **Provide Remote Support** – Completed 100%
- **Manage Applications** – Completed 100%
- **Support Windows OS** – Completed 100%

### Windows Recovery and Troubleshooting Labs

- **Boot Into the Windows Recovery Environment** – Completed 100%
- **Create a Restore Point** – Completed 100%
- **Configure the Boot Order** – Completed 100%

### Lesson Reviews

- Windows performance and troubleshooting review – Completed 100%
- Windows OS troubleshooting review – Completed 100%

The recovery and boot labs were particularly useful because they moved beyond simply knowing what tools such as System Restore, WinRE, and boot configuration utilities do and required actually navigating and using them.

---

# Key Takeaways

My biggest takeaways from Module 14 were:

- **Troubleshooting should begin by identifying the failure point**, not by immediately trying random fixes.
- Task Manager is useful for quick diagnosis, while **Resource Monitor and Performance Monitor** provide deeper information.
- Performance counters are most useful when **correlated with each other**.
- High resource utilization is not automatically a problem; sustained utilization and the surrounding context matter.
- Event Viewer is an important source of evidence when investigating Windows failures.
- Understanding the **Windows boot sequence** makes boot troubleshooting much more systematic.
- **Safe Mode and WinRE** are essential when Windows cannot operate normally.
- System Restore, driver rollback, Startup Repair, system images, and Windows Reset provide different levels of recovery.
- A slow system should be diagnosed before hardware upgrades are recommended.
- BSODs frequently point toward hardware or driver problems, especially when they occur during startup.
- Windows troubleshooting often involves combining multiple tools rather than relying on one utility.

---

# Reflection

Module 14 felt like one of the most practical modules of Core 2 so far because it brought together many of the Windows tools I had already learned and showed how they fit into an actual troubleshooting process.

The biggest improvement for me was moving away from thinking of tools individually.

Task Manager, Event Viewer, Resource Monitor, Performance Monitor, Safe Mode, System Restore, WinRE, `chkdsk`, `sfc`, and the boot repair tools all solve different parts of the same problem: **finding where something failed and gathering enough evidence to choose the correct fix**.

The performance troubleshooting sections were especially useful. Instead of seeing "100% disk" or "high CPU" and immediately assuming hardware is failing, I now have a better understanding of how to identify the process responsible, determine whether the activity is temporary or sustained, and correlate multiple resource counters before deciding what the actual bottleneck is.

The Windows boot and recovery sections also helped connect concepts that previously felt separate. Understanding the relationship between BIOS/UEFI, MBR/GPT, the boot manager, BCD, Windows loader, kernel, drivers, and finally the logon process makes boot failures much easier to reason through.

The hands-on labs reinforced this well, particularly working with **Windows Recovery Environment, restore points, boot configuration, remote support, and application management**.

Overall, this module felt much closer to the type of troubleshooting I expect to encounter in a real IT support role: identify the symptoms, determine the failure point, collect evidence, make the least disruptive fix possible, and escalate to recovery or reinstallation only when necessary.
