CompTIA A+ Core 2 --- Module 19: Managing Security Settings

Module 19 complete. This module continued the security focus by moving
into Windows account policies, endpoint protection, encryption, browser
security, malware types, malware symptoms, removal procedures, and
end-user security awareness.

A major theme throughout the module was protecting the endpoint from
multiple directions. Strong account policies help prevent unauthorized
access, encryption protects data, antivirus and endpoint monitoring help
detect threats, browser controls reduce exposure, and a structured
malware-removal process helps contain and recover from an infection.

🔑 Account and Password Security

Windows provides several account and password policies that can reduce
the risk of unauthorized access.

Password policies can define requirements such as:

Password complexity

Minimum password length

Password history

Maximum password age

Minimum password age

These controls help prevent users from selecting weak passwords or
repeatedly reusing the same credentials.

Account security also requires managing which accounts are allowed to
access the system and when that access should expire.

👤 Disabling Unnecessary Accounts

Unused or unnecessary accounts should be disabled.

Built-in or guest accounts can provide another potential method of
accessing a system if they are left enabled without a legitimate reason.

A basic security principle is:

Only enable accounts that are actually required.

Disabling unused accounts reduces the number of possible entry points
into the system.

📅 Account Expiration

Accounts can be configured with an expiration date.

This is useful when access should only exist temporarily, such as for:

Contractors

Temporary employees

Short-term projects

Visiting personnel

Once the expiration date is reached, the account can no longer be used
to sign in.

Account expiration reduces the risk of temporary accounts remaining
active long after they are needed.

🔒 Account Lockout Policies

An account lockout policy can temporarily prevent access after a
specified number of failed sign-in attempts.

Important settings include:

Account lockout threshold

Account lockout duration

Time before the failed-attempt counter resets

Lockout policies help defend against repeated password-guessing and
brute-force attacks.

However, overly aggressive lockout settings can also create availability
problems if legitimate users repeatedly mistype their passwords or if an
attacker intentionally triggers account lockouts.

🛡️ Antivirus and Microsoft Defender

Endpoint systems should use security software to detect and remove
malicious software.

Microsoft Defender Antivirus provides built-in anti-malware
protection in Windows.

Antivirus software can use several detection methods, including:

Malware signatures

Behavioral analysis

Heuristics

Real-time monitoring

Security software should be kept updated so that it can recognize newer
threats.

Regular scans and real-time protection provide different layers of
detection.

🔐 BitLocker

BitLocker provides full-volume encryption in Windows.

Encryption protects data by making it unreadable without the appropriate
decryption key.

BitLocker can help protect information if a device is:

Lost

Stolen

Accessed without authorization

BitLocker can work with a Trusted Platform Module (TPM) to securely
store cryptographic information used during the startup process.

Recovery information should also be stored securely because losing
access to the encryption keys can make legitimate data recovery
difficult.

📁 Encrypting File System

Encrypting File System (EFS) provides file-level encryption on
supported Windows file systems.

Unlike full-volume encryption, EFS can encrypt individual:

Files

Folders

This allows specific information to be protected without encrypting the
entire drive.

BitLocker and EFS therefore protect data at different levels:

BitLocker --- volume-level encryption

EFS --- file/folder-level encryption

🌐 Browser Security

Web browsers are a major point of interaction between users and internet
content.

Browser security therefore requires careful configuration.

Important controls can include:

Privacy settings

Security settings

Pop-up controls

Cookie management

Certificate validation

Extension management

Proxy configuration

DNS configuration

Browsers should also be kept updated because vulnerabilities in the
browser itself can be used to compromise the endpoint.

📜 Browser Certificates

Digital certificates allow browsers to establish trust with secure
websites.

When connecting through HTTPS, the browser examines the server's
certificate.

Certificates can help verify:

The identity of the server

The organization associated with the certificate

Whether the certificate is trusted

Whether the certificate is still valid

Certificate warnings should not simply be ignored.

A warning could indicate:

An expired certificate

An untrusted issuer

A hostname mismatch

A possible interception attempt

Users should understand that bypassing certificate warnings can expose
sensitive information.

🌍 DNS and Proxy Settings

Browser and operating-system network settings can affect where internet
traffic is sent.

DNS converts hostnames into IP addresses.

If DNS settings are maliciously modified, users can potentially be
redirected toward fraudulent systems even when they attempt to visit a
legitimate hostname.

A proxy server acts as an intermediary between a client and another
network.

Organizations may use proxies for legitimate purposes such as:

Filtering

Monitoring

Access control

Privacy

Network management

Unexpected proxy configuration can also be a sign of unwanted software
or malicious activity.

🧩 Browser Extensions

Browser extensions add functionality to a browser.

However, extensions can also introduce security and privacy risks.

A malicious or poorly designed extension may be able to:

Monitor browsing

Read website data

Modify pages

Redirect searches

Display unwanted advertisements

Collect user information

Extensions should therefore be obtained from trusted sources and
reviewed before installation.

Unused or suspicious extensions should be removed.

🦠 Malware

Malware can behave in very different ways depending on its purpose.

Some infections are designed to steal information, others provide remote
access, some generate revenue for an attacker, and others attempt to
make data or systems unavailable.

Understanding malware behavior helps identify what type of infection may
be present and what remediation steps are appropriate.

🚪 Backdoors

A backdoor provides an attacker with unauthorized remote access to a
compromised system.

Once installed, a backdoor may allow an attacker to:

Access the computer remotely

View or modify files

Upload additional malware

Exfiltrate information

Add the computer to a botnet

Use the compromised machine as part of another attack

Backdoors commonly communicate with a command-and-control server.

Communication can use protocols such as:

IRC

HTTPS

DNS

Using normal network protocols can make malicious traffic more difficult
to distinguish from legitimate traffic.

📢 Adware

Adware displays unwanted advertising on a computer.

It may appear as:

Browser pop-ups

Redirects

Additional advertisements

Modified browser behavior

Adware can be bundled with legitimate software or installed alongside
another application.

Some adware is mainly a nuisance, while other implementations may also
monitor user activity or collect browsing information.

👁️ Spyware and Keyloggers

Spyware monitors a user's activity without their knowledge or
authorization.

It may collect information about:

Browsing activity

Search activity

Applications

Personal information

System usage

A keylogger specifically records keyboard input.

This can allow an attacker to capture:

Usernames

Passwords

Messages

Credit-card information

Other sensitive data

Keylogging technology can also have legitimate uses when monitoring is
properly authorized.

💰 Ransomware

Ransomware attempts to deny access to data or systems and demands
payment from the victim.

One common form is crypto-ransomware, which encrypts files and
demands payment for the decryption key.

Another form can lock access to the device or operating system itself.

Paying a ransom does not guarantee that the attacker will restore access
to the data.

One of the strongest defenses against ransomware is maintaining reliable
backups.

Backups should be:

Separate from the affected system

Protected from unauthorized access

Tested

Recoverable

A backup that remains continuously accessible from an infected system
could also be encrypted by ransomware.

⛏️ Cryptomining Malware

Cryptomining malware secretly uses a victim's computing resources to
mine cryptocurrency.

Possible symptoms include:

High CPU usage

High GPU usage

Slow system performance

Excessive heat

Increased fan activity

Increased power consumption

The malware may attempt to remain unnoticed so that it can continue
using the victim's resources.

⚠️ Malware Symptoms

Malware does not always produce one obvious symptom.

Different infections can modify different parts of the operating system,
applications, browser, network configuration, or file system.

Performance Problems

Possible symptoms include:

Slow startup

Slow applications

Poor overall performance

High resource usage

System lockups

Freezing

Unexpected shutdowns or restarts

Performance problems alone do not prove that malware is present.
Hardware faults, software problems, and resource limitations can produce
similar symptoms.

Browser and Network Symptoms

Possible signs include:

Browser redirects

Unexpected pop-ups

Changed homepage

Changed search engine

Unwanted extensions or toolbars

Unusual network connections

Unexpected network activity

File-System Symptoms

Malware may cause:

Missing files

Renamed files

Inaccessible files

Unexpected files

Changed permissions

File corruption

Security Symptoms

An infection may attempt to weaken the computer's defenses by:

Disabling antivirus software

Disabling firewall protection

Preventing security tools from running

Preventing operating-system updates

Interfering with security services

A technician should investigate the overall pattern of symptoms rather
than assuming that one unusual behavior automatically means malware.

🚨 Desktop Alerts and Fake Security Warnings

Some malware uses fake warnings to convince the user that the computer
is infected.

The warning may pressure the user to:

Click a link

Download software

Call a telephone number

Purchase a product

Provide information

This type of attack is commonly associated with scareware or fake
antivirus software.

A legitimate security notification should normally come from a security
product that the user or organization recognizes as being installed on
the computer.

Unexpected warnings should be treated carefully rather than trusted
simply because they claim to be security software.

🛡️ Endpoint Monitoring Solutions

Modern organizations can use endpoint monitoring technologies to detect
suspicious behavior across computers and other devices.

EDR

Endpoint Detection and Response (EDR) focuses on monitoring endpoint
devices.

EDR solutions can:

Detect suspicious activity

Collect endpoint security information

Investigate incidents

Support threat response

MDR

Managed Detection and Response (MDR) provides security monitoring
and response as a managed service.

Security specialists can monitor systems and help investigate and
respond to threats rather than requiring the organization to perform
every security function internally.

XDR

Extended Detection and Response (XDR) expands detection beyond
individual endpoints.

XDR can correlate security information from multiple systems and
security technologies, providing a broader view of suspicious activity
across an environment.

🌐 Troubleshooting Browser Symptoms

Browser problems are a common symptom of adware and other malware.

Possible symptoms include:

Homepage changes

Search-engine changes

Browser redirects

Pop-ups

Unwanted extensions

Unwanted toolbars

Slow browser performance

Excessive resource usage

Troubleshooting may involve:

Checking installed browser extensions

Removing suspicious add-ons

Checking browser settings

Removing unwanted software

Scanning the computer for malware

Resetting the browser when necessary

Browser problems should be investigated carefully because not every
browser issue is caused by malware.

🧹 Malware Removal

Malware removal should follow a structured process.

The goal is not simply to delete one suspicious file. A technician must
prevent the infection from spreading, remove the malicious software,
confirm that the system is clean, restore normal protections, and reduce
the chance of reinfection.

🔎 Investigate and Verify Malware Symptoms

The first step is to determine whether malware is actually present.

A technician can examine:

User reports

System behavior

Security alerts

Running processes

Network activity

Browser behavior

File-system changes

The symptoms should be investigated before assuming that malware is the
cause.

🔌 Quarantine Infected Systems

Once malware is suspected or confirmed, the infected system should be
isolated.

This can involve disconnecting:

Ethernet

Wi-Fi

Other network connections

Isolation helps prevent:

Malware spreading to other computers

Communication with command-and-control infrastructure

Additional malware downloads

Further data exfiltration

The important principle is:

Isolate the infected system before beginning remediation.

♻️ Disable System Restore

Windows System Restore may contain copies of infected files.

During malware remediation, System Restore may need to be disabled so
that an infected restore point does not later reintroduce the malware.

After the system has been cleaned:

Re-enable System Restore.

Create a new clean restore point.

🧰 Malware Removal Tools and Methods

Different infections may require different remediation methods.

Possible tools and techniques include:

Antivirus software

Anti-malware software

Safe Mode

Bootable recovery environments

Manual removal

Restoring from a known-good backup

Reimaging or reinstalling the operating system

A bootable recovery environment can be useful because malware
running inside the normal operating system may attempt to:

Hide itself

Prevent deletion

Disable security tools

Interfere with antivirus scanning

Booting into a separate trusted environment can allow the technician to
examine and remove malicious files without the infected operating system
running normally.

💾 OS Reinstallation and Reimaging

Sometimes an infection is too severe or sophisticated to remove with
confidence.

If the integrity of the operating system can no longer be trusted, the
safest solution may be to:

Reimage or reinstall the operating system.

After reinstalling:

Apply operating-system updates

Install required security updates

Restore clean user data

Reinstall trusted applications

Re-enable security protections

Confirm the system is operating normally

A clean reinstall can provide greater confidence than attempting to
remove every component of a deeply embedded infection.

🔄 Recovery and Prevention

Once the malware has been removed, the technician should complete the
recovery process.

This can include:

Updating anti-malware software

Running additional scans

Applying operating-system updates

Updating applications

Re-enabling System Restore

Creating a clean restore point

Scheduling future scans

Confirming security software is enabled

Reviewing the original cause of the infection

The technician should also educate the user about how the infection may
have occurred.

👤 End-User Security

User behavior is an important part of malware prevention.

Users should understand common threats such as:

Phishing

Social engineering

Malicious links

Malicious email attachments

Fake security warnings

Suspicious downloads

Password and account attacks

Users should be encouraged to:

Be suspicious of unexpected communications

Verify unusual requests

Avoid blindly opening links or attachments

Keep software updated

Use secure authentication practices

Report suspicious activity

Technical security controls are important, but user awareness provides
another layer of defense.

🧪 Practical Work Completed

Alongside the theory in Module 19, I completed the associated practical
work and reviews, including:

Windows account and password security material

Account expiration and lockout configuration

Endpoint protection and Microsoft Defender material

BitLocker and EFS encryption work

Browser security and certificate material

DNS, proxy, and browser-extension security

Malware behavior and symptom identification

Browser symptom troubleshooting

Endpoint monitoring concepts

Ransomware and cryptomining material

Malware removal procedures and recovery methods

End-user security awareness material

These activities helped connect the security concepts to real
troubleshooting and protection scenarios rather than treating malware,
encryption, account security, and endpoint protection as isolated
definitions.

🎯 Key Takeaways

The biggest takeaway from Module 19 is that endpoint security depends on
multiple layers of protection and a structured response when something
goes wrong.

Strong account policies reduce the risk of unauthorized access, but they
need to be combined with endpoint protection, encryption, secure browser
configuration, updates, and good user behavior.

BitLocker and EFS also reinforced the importance of protecting data
itself. Preventing unauthorized access is important, but encryption
provides another layer when a device or file falls into the wrong hands.

Malware troubleshooting requires careful investigation because symptoms
such as slow performance, crashes, browser problems, or unusual network
activity can have several possible causes.

Once malware is identified, isolation becomes critical. Disconnecting an
infected machine can prevent it from spreading to other systems,
communicating with an attacker, or continuing to exfiltrate information.

The malware-removal process I want to remember is:

Investigate → Quarantine → Disable System Restore → Remediate → Update
and Scan → Reimage if necessary → Re-enable System Restore → Educate the
user

Module 19 brought together account security, data protection, browser
security, malware detection, troubleshooting, recovery, and user
awareness. It felt like another practical security module because these
are controls and procedures I will need to understand when supporting
and securing real endpoints.

Module 19 complete. ✅
