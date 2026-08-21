# CompTIA A+ Core 2 — Module 15: Securing Windows

Completed **Module 15 — Securing Windows**.

This module moved from general security concepts into practical Windows security: authentication, encryption, user accounts, Active Directory, Group Policy, Windows shares, and NTFS permissions.

---

## 🔐 Logical Security & Access Control

Security controls can be classified as **physical, procedural, or logical**.

The core objectives of information security are represented by the **CIA triad**:

- **Confidentiality** — sensitive information is accessible only to authorized users.
- **Integrity** — data remains accurate and trustworthy.
- **Availability** — resources remain accessible when required.

Identity and Access Management (IAM) builds on these principles through:

- **Identification** — identifying users, devices, and applications.
- **Authentication** — proving an identity.
- **Authorization** — determining which resources and actions an authenticated identity can access.
- **Access control** — enforcing those authorization decisions.

Two important principles are **implicit deny** and **least privilege**: access should be denied unless explicitly permitted, and users should receive only the permissions necessary to perform their jobs.

---

## ⚠️ Vulnerabilities, Threats & Risk

Three concepts that are easy to confuse:

- **Vulnerability** — a weakness that could be exploited.
- **Threat** — something capable of exploiting a vulnerability.
- **Risk** — the likelihood and potential impact of a threat exploiting a vulnerability.

A useful relationship is:

`Vulnerability + Threat → Risk`

---

## 🔑 Encryption & Hashing

Three major cryptographic technologies covered were:

### Symmetric Encryption

Uses the **same secret key** for encryption and decryption.

It is fast and efficient, making it useful for encrypting large amounts of data. The major challenge is securely distributing and protecting the secret key.

**AES** is a common symmetric encryption standard.

### Asymmetric Encryption

Uses a mathematically linked **public/private key pair**.

- Public key → can be distributed.
- Private key → must remain secret.

Data encrypted with one key can only be reversed using its corresponding paired key.

### Cryptographic Hashing

A hash function converts input data into a **fixed-length value**.

Unlike encryption, hashing is designed to be **one-way**. It is useful when the original value does not need to be recovered, such as securely storing passwords.

Common secure hash algorithms include **SHA-256** and **SHA-3**.

---

## ✍️ Digital Signatures & Key Exchange

A **digital signature** helps prove that a message has not been altered and verifies its origin.

The sender:

1. Hashes the message.
2. Encrypts the hash using their private key.
3. Attaches the result as the digital signature.

The recipient can use the sender's public key and compare hashes to verify the message.

Asymmetric cryptography can also solve the symmetric-key distribution problem. A symmetric session key can be protected using asymmetric encryption and then used for the actual data exchange because symmetric encryption is considerably faster.

---

## 👤 Windows User Accounts & Groups

Windows supports both **local accounts** and **Microsoft accounts**.

A local account exists only on the individual computer and is stored in the **Security Account Manager (SAM)**.

Windows also provides security groups to simplify permission management.

Important built-in groups include:

- **Administrators** — extensive system-management privileges.
- **Users** — standard user privileges.
- **Guest** — legacy group with restricted/default access.
- **Power Users** — retained mainly for compatibility with legacy applications.

Permissions should generally be assigned to **groups rather than individual users**, making access easier to manage.

The **Local Users and Groups** console and `net user` commands can be used to manage local accounts.

---

## 🛡️ User Account Control (UAC)

**User Account Control (UAC)** protects Windows from unauthorized use of administrative privileges.

Even when an administrator is logged in, normal tasks operate without unrestricted elevated privileges. Actions requiring elevation trigger a UAC consent or credential prompt.

This implements the principle of **least privilege** and helps prevent malicious software from silently gaining administrative control.

---

## 🔒 Authentication Methods

Authentication factors fall into categories such as:

- **Something you know** — password/PIN.
- **Something you have** — smart card/security token.
- **Something you are** — biometrics.

**Multifactor Authentication (MFA)** requires credentials from at least two different factor categories.

Examples of authentication technologies covered include:

- Passwords
- PINs
- Fingerprints
- Facial recognition
- Smart cards/security keys
- One-time passwords
- Authenticator applications
- Hard tokens

### OTP Methods

**TOTP (Time-based One-Time Password)** generates a code that expires after a specified period.

**HOTP (HMAC-based One-Time Password)** uses a counter so each generated password is unique.

**Challenge-response** generates an OTP based on a challenge supplied by the authentication service.

---

## 🪟 Windows Hello

Windows Hello provides alternative authentication methods including:

- PIN
- Fingerprint
- Facial recognition
- Security keys

A Windows Hello PIN is tied to the specific device and protected using hardware such as the **TPM**, rather than functioning like a conventional password transmitted across a network.

---

## 🌐 Single Sign-On & SAML

**Single Sign-On (SSO)** allows a user to authenticate once and subsequently access multiple applications or services.

This improves convenience but also increases the importance of protecting the account because compromise could provide access to multiple services.

**Security Assertion Markup Language (SAML)** provides an SSO mechanism involving:

- **Identity Provider (IdP)**
- **Service Provider (SP)**
- **SAML assertion**

The user authenticates with the IdP, which generates a signed SAML assertion. The service provider verifies that assertion and grants access without requiring the user to authenticate separately to that application.

---

## 🏢 Windows Domains & Active Directory

A **workgroup** is a peer-to-peer model where accounts and resources are managed separately on individual computers.

This works for small environments but does not scale well because accounts and passwords must be maintained independently.

A **Windows domain** centralizes administration.

A **Domain Controller (DC)** maintains **Active Directory (AD)**, which stores objects including:

- Users
- Groups
- Computers

Domain accounts can then authenticate to resources throughout the domain rather than requiring separate local accounts on every computer.

### Organizational Units

**Organizational Units (OUs)** divide a domain into administrative structures.

They can be used to organize users and computers and delegate administrative responsibilities without granting complete control over the domain.

---

## ⚙️ Group Policy

**Group Policy Objects (GPOs)** centrally configure computer settings and user profiles.

GPOs can be linked to domains or OUs, allowing administrators to apply configuration and security policies to many systems simultaneously.

Two useful commands:

```powershell
gpupdate /force
gpresult
```

`gpupdate /force` reapplies Group Policy, while `gpresult` displays the **Resultant Set of Policy (RSoP)** applied to a computer/user.

---

## 📁 Windows File Sharing

Windows workgroups can share folders and printers over a network.

For discovery and sharing to work, **Network Discovery** and **File and Printer Sharing** generally need to be enabled.

Network resources can be accessed using a **UNC path**:

```text
\\server\share
```

A share can also be mapped to a drive letter.

Useful commands include:

```powershell
net view
net view \\MYSERVER
net use M: \\MYSERVER\DATA /persistent:yes
net use M: /delete
net use * /delete
```

Administrative shares such as `C$` and `ADMIN$` are automatically created and restricted to administrators.

---

## 🖨️ Printer Sharing

A network-capable printer can communicate directly over Ethernet/Wi-Fi and be installed using its IP address or hostname.

A printer connected to a Windows computer can alternatively be **shared through that host**, allowing other network users to access it while the host remains available.

---

## 🛂 NTFS vs. Share Permissions

This was one of the most important sections of the module.

**Share permissions** apply when a folder is accessed across the network.

**NTFS permissions** apply to both local and network access and can be configured for individual files and folders.

Common NTFS permissions include:

- **Read / List / Execute**
- **Write**
- **Modify**
- **Full Control**

**Full Control** includes the ability to modify permissions and ownership.

Permissions can be **Allow** or **Deny**, as well as **explicit** or **inherited**.

When permissions conflict, Windows determines the user's **effective permissions**, with explicit Deny being highly restrictive.

When both **share and NTFS permissions** apply to network access, the **most restrictive combination wins**.

---

## 🧬 Permission Inheritance

Files and subfolders normally inherit NTFS permissions from their parent folder.

Inheritance can be disabled through Advanced Security settings when resources require different permissions.

An important distinction is that **explicitly assigned permissions take precedence over inherited permissions**.

Command-line permission management can also be performed using `icacls`, including controlling inheritance, removing permissions, and granting permissions to users or groups.

Example:

```powershell
icacls "C:\Users\UserName\Pictures" /inheritance:d
icacls "C:\Users\UserName\Pictures" /remove:g Users
icacls "C:\Users\UserName\Pictures" /grant GroupName:(OI)(CI)F
```

---

## 🌍 Domain Setup & User Data

A computer joining a domain requires:

- Connectivity to the domain network.
- Correct IP configuration.
- DNS capable of resolving the domain.
- Appropriate credentials to authorize the computer account.

Once joined, users can authenticate using domain credentials.

Active Directory environments can also centralize user data through:

### Home Folders

Private network locations where users can store personal files.

### Roaming Profiles

Store a user's profile on a network share so the profile can follow them between computers.

### Folder Redirection

Redirects folders such as Documents or Pictures to network storage without necessarily roaming the entire profile.

Folder redirection can be deployed through **Group Policy**.

---

## 🧪 Practical Work Completed

During Module 15 I also completed hands-on labs covering:

- Creating user accounts
- Creating Organizational Units
- Using Windows system commands
- Group Policy management
- Configuring NTFS permissions
- Supporting Active Directory domain networking
- Managing domain accounts

I also worked through troubleshooting challenges and exercises involving Windows authentication, security policies, Windows shares, and security features.

---

## ✅ Key Takeaways

Module 15 connected several concepts that previously felt separate: **identity, authentication, authorization, encryption, Windows accounts, Active Directory, Group Policy, file sharing, and NTFS permissions**.

The biggest takeaway for me was seeing how Windows security is layered.

Authentication establishes **who the user is**, authorization determines **what they can access**, groups make those permissions manageable, UAC limits unnecessary administrative privileges, and Active Directory/Group Policy extend those controls across an entire organization.

The NTFS and share-permission sections were particularly useful because they showed how seemingly simple file access can depend on **multiple overlapping permission systems, inheritance, group membership, and whether the resource is accessed locally or over the network**.

**Module 15 complete. ✅**
