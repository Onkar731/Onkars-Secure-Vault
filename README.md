<h1 align="center">🛡️ Onkar's Secure Vault (OSV)</h1>

<p align="center">
  <strong>An enterprise-grade, offline desktop encryption architecture built for absolute data privacy.</strong>
</p>

---

Click here to get application releases: **[Releases](../../releases)**

---

**Current Version:** 1.4.0 (BETA / EVALUATION BUILD)

**Principal Architect:** Mr. Onkar Shengule

**Supported Platforms:** Windows & macOS

---

## 📖 Overview

**Onkar's Secure Vault (OSV)** is a standalone desktop file encryption engine designed to provide true zero-knowledge security without relying on cloud file synchronization, background web services, or external storage servers. Your private files never leave your local device.

Engineered as a comprehensive software architecture project, OSV simulates commercial-grade DRM (Digital Rights Management), automated cloud licensing workflows, and OS-level integrations. It utilizes a high-performance **AES-256-GCM** cryptographic backend, a strictly local SQLite database schema, and an intuitive **PySide6** user interface to ensure that the user retains complete, offline control over their sensitive data.

> 🚨 **CRITICAL ANTI-FRAUD & SIMULATED COMMERCIAL DECLARATION** 🚨
> This Software is currently in a closed Beta/Testing evaluation phase. **The Author is NOT currently selling, licensing for profit, or monetizing this Software in any capacity, locally or globally.**
> * **Simulated Checkout & QR Code:** The in-app "Premium Upgrade" pricing matrices, payment QR codes, and UTR input forms are strictly for UI/UX testing and cloud architecture demonstration. No real financial transactions are executed.
> * If you have paid any actual currency to acquire this Software or unlock keys, you have been defrauded by an unauthorized third party.
> * **Mr. Onkar Shengule assumes absolutely no liability for financial losses, and is under no obligation to provide support, premium upgrades, or refunds for copies of this Software obtained or purchased through unauthorized third parties.**
> 
> 

---

## ✨ Core Features & Capabilities

### 1. The Master Dashboard (Base Edition)

A sleek, locally hosted interface built with PySide6. Designed for both Windows and macOS, it allows users to create virtual folder hierarchies, drag-and-drop desktop files, view media natively with auto-scaling aspect ratios, and navigate encrypted data seamlessly.

### 2. Account Profile & Identity Verification (New in v1.4.0)

A modern, dual-column Account & Billing Profile tab featuring:

* **Live Email OTP Engine:** Verifies user identity via a live 6-digit OTP dispatched directly to their inbox using custom SMTP templates, tracked by visual verification badges.
* **Dynamic Telecom Validation:** Validates international phone numbers against strict ITU E.164 standards using a country-code selector and digit length verification.

### 3. Automated Cloud Licensing Ledger (New in v1.4.0)

A SaaS-ready licensing architecture that automates upgrade requests:

* **Hardware-Bound Activation:** License requests are mathematically bound to the machine's unique Activation Fingerprint (`OSV-XXXX-XXXX`), guaranteeing strict 1-to-1 machine-to-license mapping.
* **Stateful Queue & Anti-Spam:** Requests are routed to a secure Google Firebase database with local daily rate-limiting (max 7 attempts/day) to prevent system abuse.
* **Automated Admin Fulfillment:** An automated Admin Node scans requests, cross-references active ledgers, paints PDF invoices in RAM, signs cryptographic key files, and dispatches them via email.

### 4. Native Windows OS Integration (Premium Tier)

OSV natively binds to the Windows context menu. You can right-click any file or folder directly on your desktop or file explorer to:

* **Lock Here Using OSV:** Encrypts the file in its current location, leaving behind a mathematically locked `.osv` file.
* **Send to Vault:** Encrypts and securely moves the file into your central, hidden vault database.
* **Unlock / Restore:** Right-click any `.osv` file to instantly decrypt and restore it to its original state (requires Master Password authorization).

### 5. Plausible Deniability / Decoy Vault (Premium Tier)

Built for extreme threat models, OSV features a mathematically isolated secondary vault. By entering a specific "Decoy Password" at the login screen, the system boots into a completely separate SQLite database. The Decoy Vault has zero cryptographic awareness of the Master Vault, and vice versa.

### 6. Deep-Kernel Data Shredder (Premium Tier)

Standard file deletion leaves massive security loopholes. The OSV Shredder explicitly opens targeted external or internal vault files and overwrites physical disk sectors with random cryptographic noise three consecutive times utilizing DoD 5220.22-M military standards, making forensic recovery impossible.

### 7. Secure Notes Sandbox (Premium Tier)

A specialized encrypted text editor for highly sensitive data. Text exists strictly in volatile system RAM and is encrypted directly into the secure vault container upon saving, leaving zero forensic text remnants on the physical hard drive.

---

## 🛡️ Key Safety & Cryptographic Subsystems

* **Aggressive RAM Locking:** Cryptographic Master Encryption Keys (MEK) are bound exclusively to volatile memory. The application explicitly purges and zeroes out keys from RAM the millisecond the vault is locked or panic-exited (`Ctrl+Shift+L` or `Ctrl+Shift+E`), neutralizing memory-scraping malware and cold-boot attacks.
* **Buffer Overflow & Capping Safeguards:** All master and decoy passwords are strictly capped at a maximum of 64 characters across all input forms to prevent memory exhaustion and buffer overflow vulnerabilities.
* **Atomic I/O Transactions:** Original plaintext files are never securely shredded until the AES-256-GCM encrypted payload and SQLite ledger records are 100% mathematically verified and physically committed to disk, eliminating corruption risks during unexpected power losses.
* **Hardware-Accelerated UI Engine:** Automatically calculates optimal display bounds (85% target monitor resolution), centers geometry, and executes a smooth 800ms opacity fade-in transition upon authentication.

---

## 💳 Tiered Licensing & Future Commercial Plans

The Software operates on a structured licensing framework:

* **Free Base Tier:** Granted a limited, temporary license to evaluate the core encryption engine for personal, non-commercial testing purposes.
* **Premium Tier:** Access to advanced subsystems (Data Shredder, Secure Notes, Decoy Vault, OS Integration) requires an authorized Cryptographic License Key (`license.txt`) issued directly by the Author for testing purposes.

### Future Pricing & Refund Policy

In the event that the Author initiates official commercial distribution in the future, the following refund policy applies universally:

* **Non-Refundable:** Because Premium Licenses are offline, mathematically node-locked cryptographic keys bound specifically to a user's physical hardware fingerprint, they cannot be remotely deactivated or returned. Therefore, all authorized license issuances are **STRICTLY NON-REFUNDABLE**.
* **Terms of Service Regarding "Lifetime":** All licenses grant access to the current software version "as-is". The developer reserves the right to modify, restrict, or discontinue future updates, features, or support services at any time without notice. "Lifetime" refers to the lifespan of this software product, not a guarantee of eternal updates or service availability.

---

## 🏗️ Technical Stack & Dependencies

* **Language Backend:** Python 3.x
* **Graphical User Interface:** PySide6 (Qt for Python)
* **Cryptographic Engine:** `cryptography` (AES-256-GCM, PBKDF2/HMAC-SHA256, Argon2id, PKCS#1 v1.5 RSA Signing)
* **Database Schema:** SQLite3 (Local, air-gapped relational database)
* **Cloud Infrastructure:** Google Firebase Firestore REST API (Licensing queue), Google SMTP SSL (OTP Verification & PDF Invoice Delivery)
* **Document Generation:** PyFPDF / FPDF (In-memory PDF Tax Invoice rendering)
* **OS Shell Integration:** Windows Registry Manipulation (`winreg`, ShellExecute UAC triggers)
* **Deployment & Packaging:** Inno Setup Compiler & PyInstaller

---

## 📥 Installation Guide

1. Navigate to the **Releases** page on this repository.
2. Download the latest `Onkar's Secure Vault Setup v1.4.x.exe` installer file.
3. If participating in the Premium Beta, obtain your assigned `license.txt` file provided by the Author.
4. Place the `license.txt` file directly inside the same directory as the installer prior to running setup (or drop it into the main application directory post-installation).
5. Run the Setup executable. The software will automatically ingest your license key, verify its asymmetric cryptographic signature, and secure it to your local environment.

---

## ⚖️ Proprietary Licensing, Legal Framework, & Terms of Use

### 1. Ownership of Intellectual Property & Authority

**Copyright © 2026 Mr. Onkar Shengule. All Rights Reserved.**

All intellectual property rights, source code, graphical interfaces, branding, and design architecture belong exclusively to the Principal Architect, Mr. Onkar Shengule. Onkar's Secure Vault is strictly proprietary software. All distribution and future commercialization rights are exclusively held by Mr. Onkar Shengule.

You are strictly PROHIBITED from:

* Selling, renting, leasing, reselling, white-labeling, or commercializing the Software.
* Decompiling, reverse-engineering, disassembling, or bypassing cryptographic license verification gates.
* Distributing your assigned testing license key (`license.txt`) to any unauthorized third parties.

### 2. Zero-Knowledge Architecture & Irreversible Data Loss

This Software employs strict zero-knowledge, local AES-256-GCM encryption. By utilizing this Software, you acknowledge the following absolute cryptographic realities:

* **No Backdoors:** The Author has absolutely zero access to your locked files, your Master Password, or your Decoy Password.
* **Irreversible Data Loss:** If you forget your Master Password and lose access to your Account Recovery methods, your data is mathematically impossible to recover.
* **100% Offline Vault Storage:** Your private vault files never leave your physical device. The Author does not store, sync, collect telemetry on, or transmit your vault data to any external cloud servers. The only cloud connectivity utilized is for testing the simulated license issuance via Firebase and sending OTP verification emails.

### 3. Limitation of Liability & High-Risk Features

**THE SOFTWARE IS PROVIDED "AS IS" AND "AS AVAILABLE," WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED. THE AUTHOR EXPLICITLY DISCLAIMS ALL WARRANTIES, INCLUDING THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT. THE AUTHOR DOES NOT WARRANT THAT THE SOFTWARE WILL BE UNINTERRUPTED, BUG-FREE, OR ENTIRELY IMMUNE TO FORENSIC OPERATING SYSTEM VULNERABILITIES.**

**UNDER NO CIRCUMSTANCES SHALL MR. ONKAR SHENGULE BE HELD LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE SOFTWARE.** THIS INCLUDES, BUT IS NOT LIMITED TO:

* Permanent data loss due to forgotten Master or Decoy passwords.
* Intentional or accidental permanent data destruction executed via the in-app DoD 5220.22-M Data Shredder.
* Data corruption resulting from hardware failure, power loss, or unexpected computer shutdowns during file I/O operations.
* Loss of data due to user deletion of raw `.osv` files or the core Vault Database.

**Your use of this Software is entirely at your own risk.** It is highly recommended that you maintain external offline backups of highly critical files before committing them to the Vault or executing shredding operations.

---

<p align="center">
  <i>Engineered and Designed by Mr. Onkar Shengule</i>
</p> 



