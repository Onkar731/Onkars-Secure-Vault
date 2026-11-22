<h1 align="center">🛡️ Onkar's Secure Vault (OSV)</h1>

<p align="center">
  <strong>An enterprise-grade, offline-first zero-knowledge desktop encryption architecture built for total local data sovereignty.</strong>
</p>

---

Click here to download official releases: **[Releases](../../releases)**

---

**Current Version:** 1.5.0 (CLOSED BETA / PRE-RELEASE EVALUATION BUILD)

**Principal Architect & Exclusive Owner:** Mr. Onkar Shengule

**Supported Platforms:** Windows 10 & Windows 11 (64-bit Only) — **macOS & Linux are NOT Supported**

---

> 🚫 **IMPORTANT PLATFORM NOTICE — WINDOWS 64-BIT ONLY (NOT FOR macOS)** 🚫
> **Onkar's Secure Vault (OSV) v1.5.0 is engineered exclusively for 64-bit Microsoft Windows (Windows 10 / Windows 11).**
> * **Does NOT Work on macOS:** OSV relies directly on native Windows Kernel security APIs (Windows DPAPI, DWM Screen Capture Shield, NTFS ACLs / EFS, Hardware SSD TRIM IOCTLs, Windows Restart Manager, and a native Win32 C Explorer batch launcher). **It will NOT work on macOS and is strictly NOT recommended for macOS, Linux, or compatibility layers/emulators (Wine, CrossOver, etc.).**
> * **Zero Owner Responsibility:** Any attempt to install, run, emulate, modify, or force-execute this software on macOS or any unsupported operating system is strictly at your own risk. **Mr. Onkar Shengule assumes zero responsibility or liability** for crashes, incompatibility, system issues, or data loss on unsupported platforms.

> ⚠️ **LEGACY / PREVIOUS RELEASES WARNING (v1.4.0 & EARLIER)** ⚠️
> Earlier builds listed under **Releases** (v1.4.0 and older) are **deprecated archival builds** retained strictly for version history.
> * Legacy versions are **no longer supported or maintained** and lack critical v1.5.0 security upgrades (including unified single-database steganography, Windows Capture Shield, 2-of-3 quorum hardening, and modern recovery controls).
> * **Recommendation:** Do **not** install or store sensitive data in v1.4.0 or earlier builds. Always download the latest **v1.5.0** release. **Mr. Onkar Shengule bears zero responsibility or liability** for any bug, compatibility issue, or data loss arising from downloading or using previous/deprecated versions.

> 🚨 **CRITICAL ANTI-FRAUD & CLOSED BETA EVALUATION DECLARATION** 🚨
> This Software is currently in an **invitation-only Closed Beta / Pre-Release Testing phase**. **The Author is NOT currently selling, charging for, licensing for profit, or monetizing this Software in any capacity, locally or globally (Actual Fee Charged: ₹0.00 / $0.00).**
> * **Simulated Commercial UI:** All in-app pricing matrices, subscription tiers, payment QR codes, UTR reference prompts, and system-generated PDF invoice previews exist strictly for end-to-end UI/UX and cloud architecture evaluation. They carry **zero commercial, financial, refund, or tax liability**.
> * **Fraud Warning:** If you paid any actual currency to any individual, group, or website to acquire this Closed Beta build or unlock keys, you have been defrauded by an unauthorized third party.
> * **Zero Liability for Unauthorized Sales:** **Mr. Onkar Shengule assumes absolutely no liability for financial losses**, and is under no obligation to provide support, licenses, or refunds for copies obtained through unauthorized third parties.

---

## 📖 Overview

**Onkar's Secure Vault (OSV)** is a standalone, offline-first Windows desktop encryption engine built to deliver true zero-knowledge security without uploading your private vault to corporate cloud storage. Your encrypted files and metadata remain strictly on your local computer.

Built on **AES-256-GCM** (64 KB authenticated chunk streaming), **Argon2id**, **HKDF-SHA512**, **X25519**, and **RSA-2048** trust anchors with a **PySide6** interface, OSV v1.5.0 pairs local vault isolation with optional encrypted peer-to-peer sharing (**OSV Beam**), zero-knowledge browser links (**Web Drops**), a **Concurrent Document Sandbox**, and a **Vault Recovery Card** system.

---

## ✨ Core Features & Capabilities (v1.5.0)

### 1. Zero-Knowledge Vault, Unified Encrypted Database & Global Search (Base Edition)
* **Unified Single-Database Steganography:** All vault metadata is stored on disk exclusively as uniform 512-byte padded AES-256-GCM blobs (unified with Decoy records and random chaff blobs) with zero plaintext file or folder names on disk.
* **Unique Per-File Encryption Keys (FEK):** Every imported file is encrypted under its own random 256-bit FEK wrapped by your Master Encryption Key (MEK).
* **High-Speed Global Search & Async Batch Engine:** Instant B-Tree indexed search across all folders and subfolders (*Contains, Begins With, Ends With, Exact Match, Extension*), plus non-blocking background workers for mass imports, copies, extractions, and secure wipes.

### 2. Zero-Disk Viewers, Capture Shield & Document Sandbox
* **RAM-Only Viewers & PID-Verified Media Streaming:** View photos, multi-page PDFs, and 20+ text/code formats strictly in RAM (with integrated Find & Replace). Large videos and audio stream in 64 KB chunks over a token-authenticated localhost server with Windows Kernel PID verification that blocks external capture tools (`VLC`, `ffmpeg`, `curl`, browsers).
* **Windows Kernel Capture Shield & Privacy Blur:** Blocks PrintScreen, Snipping Tool, OBS, and Windows Recall (rendering solid black) across vault windows, viewers, and dialogs, paired with an inactivity Privacy Blur overlay and re-authentication lockdown.
* **Concurrent Document Sandbox & Crash Guardian (Premium):** Edit Word, Excel, and PowerPoint files natively under NTFS EFS or Kernel Protected Mode (anti-indexing + single-user ACLs). A detached crash watchdog automatically closes exposed editors, shreds temporary working copies if OSV crashes or locks, and displays a verified Shredding Assurance Report on next login.

### 3. OSV Beam & Zero-Knowledge Web Drops (Ultimate & Business Tiers)
Share encrypted files and full folder hierarchies across 4 channels with ephemeral **X25519 + HKDF-SHA512** encryption and 6-digit visual security PINs:
* **Local Wi-Fi / Hotspot Radar:** Auto-discovers nearby OSV nodes with unlimited size and zero internet usage (supports 1-to-1, 1-to-Many Broadcast, and parallel transfers).
* **Wired USB / Ethernet Cable:** Direct high-speed cable transfers with unlimited size.
* **Global Beam Code:** Live OSV-to-OSV transfers across cities or countries (up to 1 GB) via a zero-knowledge blind relay (0 bytes stored on server).
* **Web Drop Links (No App Needed):** Browser-decrypted links (up to 100 MB) where the decryption key stays in the URL `#fragment` (never sent to OSV servers), protected by Recipient Email OTP or a 10+ character passphrase with **Burn-on-3-Fails**.
* **Safety Controls, History & Remote Kill-Switch:** Enforce Expiry TTL, Max Views/Downloads, View-Only mode, No Re-Share locks, Online UTC anti-clock-tamper checks, dynamic viewer watermarks, encrypted Share History, and instant remote Web Drop revocation.

### 4. Vault Recovery Card, Stealth Keyfile & 5-Minute Security Enclave
* **Vault Recovery Card (Free at Setup):** Automatically generates a single-line 40-character Vault Recovery Key with QR code and a print-ready 1-page A4 vector PDF card. Regenerating a fresh card (permanently invalidating the old one) is supported on Ultimate & Business plans.
* **Zero-Modification Stealth Keyfile (Premium):** Binds a recovery key to any everyday file via non-destructive Keyed BLAKE2b fingerprinting without altering a single byte.
* **5-Minute Time-Bounded Credential Rotation:** Update Security Questions (Free), rotate your Stealth Keyfile (Premium), or regenerate your Vault Recovery Card (Ultimate & Business) inside a monitored 5-minute enclave requiring Step-Up Master Password + Email 2FA OTP, with strictly isolated 24-hour failure lockouts and 24-hour post-change cooldowns per option.

### 5. Native Windows OS Integration & Multi-File Batch Launcher (Premium Tier)
Integrates directly into Windows Explorer right-click menus via a windowless native C batch launcher (`osv_launcher.exe`) so selecting dozens or hundreds of files prompts for your Master Password **once**:
* **Lock Here Using OSV:** Encrypts standalone files into `.osv` files or compresses & locks entire folders into `.osvd` archives with NTFS anti-deletion ACLs and custom icons.
* **Send to Vault:** Encrypts and moves normal files, folders, or already-locked `.osv`/`.osvd` items straight into your Master Vault.
* **Unlock & Restore:** Double-click or right-click any `.osv` or `.osvd` item to decrypt and restore it in-place.

### 6. Unified Plausible Deniability / Decoy Vault (Premium Tier)
Entering your secondary Decoy Password at login opens an isolated fake vault stored indistinguishably inside the exact same single encrypted database file — leaving zero observable on-disk trace of whether a hidden vault exists.

### 7. Media-Aware Hardware Data Shredder & Secure Notes (Premium Tier)
* **Hardware-Aware Shredder:** Automatically detects SSD/NVMe vs. HDD storage controllers to issue hardware `FSCTL_FILE_LEVEL_TRIM` on flash drives and DoD 5220.22-M 3-pass overwrites on magnetic drives, followed by 0-byte truncation and 5 random filename renames.
* **Secure Notes Sandbox:** Write and encrypt sensitive text directly from RAM into the vault without Notepad disk or Search Index remnants.

### 8. Modular Iron State Backups & 2-Step Selective Restoration (Premium Tier)
Export customizable AES-256-GCM `.osvbackup` snapshots (Mandatory Core plus selectable Sharing Policies, Audit Logs, Share History, Decoy Vault, Received Beam Folder, and Security Preferences) and restore selectively via **Merge** or **Wipe & Replace**.

### 9. Account Profile, Sentinel Sync & RSA-2048 Signed Updates
* **Identity Enclave & 2FA OTP:** Encrypted profile storage with server-authoritative 6-digit Email OTP verification and international E.164 phone validation.
* **90-Day Offline Sovereign Grace & 4-State Lifecycle:** Hardware-bound Activation Fingerprint (`OSV-XXXX-XXXX-XXXX-XXXX`), offline RSA-2048 license verification, Plan Queueing (zero days lost), Pause/Suspension handling, 4-step Device Migration Wizard, and automatic RSA-2048 + SHA-256 verified update checks.

---

## 🛡️ Key Security & Architectural Safeguards

* **Tri-Guard 2-of-3 Quorum Self-Healing:** Seals key envelopes via Windows Kernel DPAPI across 3 independent anchors with hardware-peppered HMAC-SHA512 and MEK-bound core locks, automatically repairing any single corrupted or missing anchor.
* **Hardware Memory Zeroization:** Sensitive keys are held in mutable memory buffers and explicitly overwritten with zeros via `ctypes.memset` upon completion, vault lock (`Ctrl+Shift+L`), or Panic Exit (`Ctrl+Shift+E`).
* **Atomic I/O Transactions:** Original plaintext files are never shredded until encrypted payloads and database commits are verified and flushed to storage.
* **Enterprise Audit Trail:** Immutable encrypted event logging across Master and Decoy partitions with certified PDF and formula-sanitized CSV exports (Ultimate & Business).

---

## 💳 Tiered Licensing Framework (Simulated in Closed Beta)

During this Closed Beta phase, all plan tiers are for evaluation only and carry a **₹0.00 / $0.00 actual charge**:

* **Free Base Edition:** Core AES-256-GCM Vault, RAM Viewers & Media Streaming, Global Search, Initial Vault Recovery Card, and Security Question updates.
* **Personal Plans (Non-Commercial):** *Personal Starter (1-Month)*, *Personal Standard (6-Months)*, *Personal Pro (1-Year)*, and *Personal Ultimate Pro (1-Year)* progressively unlock Secure Notes, Data Shredder, OS Integration, Decoy Vault, Stealth Keyfile, Iron State Backups, Document Sandbox, OSV Beam & Web Drops, Certified Audit Exports, and Vault Recovery Card Regeneration.
* **Business Plans (Commercial Workstation Use):** *Business Solo (1-Seat)* and *Business Team (3-Seats)* authorize commercial deployment with full enterprise capabilities.

### Future Commercial Refund Policy
When official commercial distribution launches in the future, all paid licenses will be issued as hardware-bound cryptographic keys bound to a device's Activation Fingerprint that cannot be physically returned. Accordingly, all future authorized commercial license purchases will be **STRICTLY NON-REFUNDABLE**. Users are encouraged to thoroughly evaluate the Free Base Edition before purchasing any future license.

---

## 🏗️ Technical Stack

* **Core Engine & GUI:** Python 3.x, PySide6 (Qt6 + QtPdf + QtMultimedia + QtSvg), Native C (`osv_launcher.exe` Windows Explorer batch wrapper)
* **Cryptography:** `cryptography` (AES-256-GCM, HKDF-SHA512, X25519, RSA-2048), `argon2-cffi` (Argon2id), Keyed BLAKE2b, Windows Kernel DPAPI
* **Local Storage & Parsing:** SQLite3 (Unified Encrypted Records + `:memory:` B-Tree Engine), `defusedxml`, `Pillow`, `qrcode`, `keyring`
* **Cloud Services (Optional / Licensing / Relay):** Google Firebase Firestore REST API (License Ledger & RSA-Signed Config), Server-Authoritative OTP Relay, Cloudflare Workers & Durable Objects (Zero-Knowledge Blind WSS Relay & Web Drops)
* **Packaging:** PyInstaller & Inno Setup (64-bit Windows Installer)

---

## 📥 Installation Guide (Windows 10 / 11 64-bit)

1. Open the **[Releases](../../releases)** page on this repository and select the latest **`v1.5.0`** release.
2. Download **`OSV_Setup_v1.5.0.exe`** (optionally verify its published **SHA-256 checksum** via PowerShell: `Get-FileHash .\OSV_Setup_v1.5.0.exe -Algorithm SHA256`).
3. Run **`OSV_Setup_v1.5.0.exe`** and review/accept the End User License Agreement (`Terms.txt`).
   * *Windows SmartScreen Note:* Because this Closed Beta installer is not yet signed with a commercial EV Code Signing Certificate, Windows Defender SmartScreen may display *"Windows protected your PC"*. Click **More info → Run anyway** to proceed.
4. Launch **Onkar's Secure Vault**, complete the Setup Wizard, and safely save/print your **Vault Recovery Card**.
5. *(Optional Beta License Activation)* Complete your **Profile** email verification and either click **🔄 Authenticate** for Zero-Touch Cloud Sync or click **🎫 Apply License** to deploy an assigned RSA-signed `license.txt`.
6. **Before Uninstalling:** Always unlock and restore any desktop `.osv` files or `.osvd` locked folders first. Running the uninstaller automatically launches the OSV Uninstallation Recovery & Shredder utility to safely export or wipe your vault.

---

## ⚖️ Proprietary Licensing, Legal Framework & Terms of Use

### 1. Exclusive Ownership of Intellectual Property & Authority

**Copyright © 2026 Mr. Onkar Shengule. All Rights Reserved.**

All intellectual property rights, source code, compiled binaries, cryptographic architecture, icons, graphical interfaces, and documentation belong exclusively to the Principal Architect and Owner, **Mr. Onkar Shengule**. Onkar's Secure Vault is strictly proprietary software. All distribution and commercialization rights are exclusively reserved by Mr. Onkar Shengule.

You are strictly **PROHIBITED** from:
* Selling, renting, leasing, sublicensing, redistributing, repackaging, or white-labeling the Software.
* Decompiling, disassembling, reverse-engineering, or attempting to bypass cryptographic or license verification controls.
* Sharing, reselling, or distributing any assigned license key (`license.txt`) to any third party.

### 2. Zero-Knowledge Architecture & Sole User Responsibility

This Software operates on strict local zero-knowledge encryption. By installing or using OSV, you explicitly acknowledge:
* **No Backdoors or Key Escrow:** Neither OSV nor Mr. Onkar Shengule stores, transmits, or has access to your Master Password, Decoy Password, Security Question answers, Stealth Keyfile, Vault Recovery Key, or Backup Passwords.
* **Vault Recovery Key & Card:** The Vault Recovery Key and optional PDF card are provided strictly as a secondary convenience safeguard. Printing on a trusted personal printer, physically securing the card, shredding digital PDF copies, and preventing theft or exposure is **100% the sole responsibility of the user**.
* **Irreversible Data Loss:** Losing your Master Password along with your recovery credentials renders your encrypted data mathematically unrecoverable.
* **Transparent Network Scope:** Vault files stay 100% local on your machine. Network communication occurs strictly for optional Email 2FA OTP verification, hardware node license ledger & RSA-2048 signed update checks, and user-initiated OSV Beam Global Relay / Web Drop sharing.

### 3. Platform Restriction, Legacy Builds & Limitation of Liability

**THE SOFTWARE, DOCUMENTATION, AND RECOVERY UTILITIES ARE PROVIDED STRICTLY "AS-IS" AND "AS-AVAILABLE," WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, OR NON-INFRINGEMENT. THE AUTHOR DOES NOT WARRANT THAT THE SOFTWARE WILL BE UNINTERRUPTED, BUG-FREE, OR IMMUNE TO OPERATING SYSTEM OR HARDWARE VULNERABILITIES.**

**UNDER NO CIRCUMSTANCES SHALL ONKAR'S SECURE VAULT OR ITS DEVELOPER, PRINCIPAL ARCHITECT, COPYRIGHT HOLDER, OR OWNER (MR. ONKAR SHENGULE) BE HELD LEGALLY, FINANCIALLY, OR OPERATIONALLY LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, OR CONSEQUENTIAL DAMAGES ARISING FROM EVALUATING, INSTALLING, OR USING THIS SOFTWARE (CURRENT OR PREVIOUS RELEASES).** THIS INCLUDES, WITHOUT LIMITATION:
* Permanent data loss due to forgotten Master or Decoy passwords, or lost/exposed Vault Recovery Cards.
* Intentional or accidental permanent data destruction via the Data Shredder (SSD TRIM / DoD 5220.22-M).
* Data loss from uninstalling OSV without first unlocking desktop `.osv` files or `.osvd` folders, or unsaved edits lost during emergency Sandbox watchdog closure.
* Any failure, crash, or data loss resulting from attempting to run OSV on **macOS**, Linux, or any unsupported OS, or from using **deprecated previous releases (v1.4.0 and earlier)**.
* Data corruption caused by hardware failure, power loss, or unexpected system shutdowns during I/O operations.
* Any unauthorized third-party sales, browser-side screenshots of Web Drop files, or mishandling of shared links/passphrases.

**Your use of this Software is strictly at your own risk.** Always maintain independent offline backups of critical files before storing them in any encryption vault or executing shredding operations.

---

<p align="center">
  <i>Engineered, Architected &amp; Owned by Mr. Onkar Shengule &bull; Official Support: onkar.securevault.admin@gmail.com</i>
</p>
