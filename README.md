<h1 align="center">🛡️ Onkar's Secure Vault (OSV)</h1>

<p align="center">
  <strong>An enterprise-grade, offline desktop encryption architecture built for absolute data privacy.</strong>
</p>

---

Click here to get application releases: **[Releases](../../releases)**

---

**Current Version:** 1.3.0 (BETA / EVALUATION BUILD)  
**Principal Architect:** Mr. Onkar Shengule

---

## 📖 Overview
**Onkar's Secure Vault (OSV)** is a standalone desktop file encryption engine designed to provide true zero-knowledge security without relying on cloud synchronization, background web services, or external servers. 

Developed as a comprehensive software architecture project, OSV simulates commercial-grade DRM (Digital Rights Management) and OS-level integrations. It utilizes an **AES-256-GCM** cryptographic backend and a strictly local SQLite database to ensure that the user retains complete, offline control over their sensitive files.

> 🚨 **CRITICAL ANTI-FRAUD & BETA TESTING DECLARATION** 🚨
> This Software is currently in a closed Beta/Testing evaluation phase. **The Author is NOT currently selling, licensing for profit, or monetizing this Software in any capacity, locally or globally.** 
> * If you have paid any amount of money to acquire this Software, you have been defrauded by an unauthorized third party. 
> * **Mr. Onkar Shengule assumes absolutely no liability for financial losses, and is under no obligation to provide support, premium upgrades, or refunds for copies of this Software obtained or purchased through unauthorized third parties.**

---

## ✨ Core Features & Capabilities

### 1. The Master Dashboard (Base Edition)
A sleek, locally hosted interface built with PyQt6. It allows users to create virtual folder hierarchies, drag-and-drop files, and manage encrypted data seamlessly. 

### 2. Native Windows OS Integration (Premium Tier)
OSV natively binds to the Windows context menu. You can right-click any file or folder directly on your desktop or file explorer to:
*   **Lock Here Using OSV:** Encrypts the file in its current location, leaving behind a mathematically locked `.osv` file.
*   **Send to Vault:** Encrypts and securely moves the file into your central, hidden vault database.
*   **Unlock / Restore:** Right-click any `.osv` file to instantly decrypt and restore it to its original state (requires Master Password authorization).

### 3. Plausible Deniability / Decoy Vault (Premium Tier)
Built for extreme threat models, OSV features a mathematically isolated secondary vault. By entering a specific "Decoy Password" at the login screen, the system boots into a completely separate SQLite database. The Decoy Vault has zero cryptographic awareness of the Master Vault, and vice versa. 

### 4. Deep-Kernel Data Shredder (Premium Tier)
Standard file deletion leaves massive security loopholes. The OSV Shredder explicitly opens targeted external or internal vault files and overwrites the physical disk sectors with random cryptographic noise three consecutive times utilizing DoD 5220.22-M military standards, making forensic recovery impossible.

### 5. Secure Notes Sandbox (Premium Tier)
A specialized encrypted text editor for highly sensitive data. Text exists strictly in volatile system RAM and is encrypted directly into the secure vault container upon saving, leaving zero forensic text remnants on the physical hard drive.

---

## 🛡️ IMP Features & Subsystems
*   **Deep-Kernel Data Shredder:** Completely bypasses the Windows Recycle Bin. Explicitly overwrites targeted disk sectors with random cryptographic noise three consecutive times (DoD 5220.22-M military standard) before deletion, making forensic data recovery physically impossible.
*   **Secure Notes Sandbox:** An isolated, encrypted text editor designed for highly sensitive passwords or PINs. Text is processed strictly in volatile system RAM and encrypted directly into the Vault container, leaving zero forensic `.txt` remnants on the hard drive.
*   **Aggressive RAM Locking:** Cryptographic Master Keys (MEK) are bound exclusively to volatile memory. The application now explicitly purges and zeroes out the key from RAM the millisecond the vault is locked or panic-exited, neutralizing memory-scraping malware and cold-boot attacks.
*   **Atomic I/O Transactions:** Original plaintext files are never securely shredded until the AES-GCM encrypted payload and SQLite ledger records are 100% mathematically verified and physically committed to the disk. This eliminates data corruption risks during sudden power losses or system crashes.

--- 

## 💳 Tiered Licensing & Future Commercial Plans

The Software operates on a structured licensing framework:

*   **Free Base Tier:** You are granted a limited, temporary license to evaluate the core encryption engine for personal, non-commercial testing purposes.
*   **Premium Tier:** Access to advanced subsystems (Data Shredder, Secure Notes, OS Integration) requires an authorized Cryptographic License Key issued directly by the Author for testing purposes.

### Future Pricing & Refund Policy
In the event that the Author initiates official commercial distribution in the future, the following refund policy applies universally: 
*   **Non-Refundable:** Because Premium Licenses are offline, mathematically node-locked cryptographic keys bound specifically to a user's physical hardware fingerprint, they cannot be remotely deactivated or returned. Therefore, all authorized license issuances are STRICTLY NON-REFUNDABLE. 
*   **Terms of Service regarding "Lifetime":** All licenses grant access to the current software version "as-is". The developer reserves the right to modify, restrict, or discontinue future updates, features, or support services at any time without notice. "Lifetime" refers to the lifespan of this software product, not a guarantee of eternal updates or service availability.

---

## 🏗️ Technical Stack & Dependencies
*   **Backend Logic:** Python 3.x
*   **Cryptographic Engine:** `cryptography` (AES-256-GCM, Argon2id)
*   **Database:** SQLite3 (Local, air-gapped schema)
*   **User Interface:** PyQt6
*   **OS Integration:** Native Windows Registry manipulation
*   **Deployment Wrapper:** Inno Setup & PyInstaller 

---

## 📥 Installation Guide

1. Navigate to the **Releases** page on this repository.
2. Download the latest `OSV Installation Setup.zip` file and extract it to your desktop.
3. Download the personal `license.txt` file provided to you (if participating in the Premium Beta).
4. Place the `license.txt` file directly inside the extracted setup folder, sitting exactly next to the `Onkars Secure Vault Setup v1.x.x.exe` file.
5. Run the Setup executable. The software will automatically ingest your license, verify the signature, and permanently secure it to your local environment.

---

## ⚖️ Proprietary Licensing, Legal Framework, & Terms of Use

### 1. Ownership of Intellectual Property & Authority
**Copyright © 2026 Mr. Onkar Shengule. All Rights Reserved.**

All intellectual property rights, source code, graphical interfaces, and design architecture belong exclusively to the Principal Architect, Mr. Onkar Shengule. Onkar's Secure Vault is strictly proprietary software. All distribution and future commercialization rights are exclusively held by Mr. Onkar Shengule.

You are strictly PROHIBITED from:
*   Selling, renting, leasing, reselling, or white-labeling the Software.
*   Decompiling, reverse-engineering, or bypassing the cryptographic license verification gates.
*   Distributing your assigned testing license key (`license.txt`) to any third parties.

### 2. Zero-Knowledge Architecture & Irreversible Data Loss
This Software employs strict zero-knowledge, local AES-256-GCM encryption. By utilizing this Software, you acknowledge the following absolute cryptographic realities:
*   **No Backdoors:** The Author has absolutely zero access to your locked files, your Master Password, or your Decoy Password.
*   **Irreversible Data Loss:** If you forget your Master Password and lose access to your Account Recovery methods, your data is mathematically impossible to recover.
*   **100% Offline Integrity:** Your files never leave your device. The Author does not store, sync, collect telemetry, or transmit your data to any external cloud servers.

### 3. Limitation of Liability & High-Risk Features
THE SOFTWARE IS PROVIDED "AS IS" AND "AS AVAILABLE," WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED. THE AUTHOR EXPLICITLY DISCLAIMS ALL WARRANTIES, INCLUDING THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT. THE AUTHOR DOES NOT WARRANT THAT THE SOFTWARE WILL BE UNINTERRUPTED, BUG-FREE, OR ENTIRELY IMMUNE TO FORENSIC OPERATING SYSTEM VULNERABILITIES.

**UNDER NO CIRCUMSTANCES SHALL Mr. Onkar Shengule BE HELD LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE SOFTWARE.** THIS INCLUDES, BUT IS NOT LIMITED TO:
*   Permanent data loss due to forgotten Master or Decoy passwords.
*   Intentional or accidental permanent data destruction executed via the in-app DoD 5220.22-M Data Shredder.
*   Data corruption resulting from hardware failure, power loss, or unexpected computer shutdowns during I/O operations.
*   Loss of data due to user deletion of raw `.osv` files or the core Vault Database.

**Your use of this Software is entirely at your own risk.** It is highly recommended that you maintain external offline backups of highly critical files before committing them to the Vault or executing shredding operations.

---
<p align="center">
  <i>Engineered and Designed by Mr. Onkar Shengule</i>
</p>
