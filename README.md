<h1 align="center">🛡️ Onkar's Secure Vault (OSV)</h1>

<p align="center">
  <strong>An enterprise-grade, offline desktop encryption architecture built for absolute data privacy.</strong>
</p>

---

Click here to get application releases: **[Releases](../../releases)**

---

## 📖 Overview
**Onkar's Secure Vault (OSV)** is a standalone desktop file encryption engine designed to provide true zero-knowledge security without relying on cloud synchronization, background web services, or external servers. 

Developed as a comprehensive software architecture project, OSV simulates commercial-grade DRM (Digital Rights Management) and OS-level integrations. It utilizes an **AES-256-GCM** cryptographic backend and a strictly local SQLite database to ensure that the user retains complete, offline control over their sensitive files.

> ⚠️ **NOTICE FOR PUBLIC DOWNLOADERS:** While this repository and the application files are publicly visible, the application itself is cryptographically locked. **You cannot use this software without a digitally signed `license.txt` file issued directly by the developer.** 

---

## ✨ Core Features & Capabilities

### 1. The Master Dashboard
A sleek, locally hosted interface built with PyQt6. It allows users to create virtual folder hierarchies, drag-and-drop files, and manage encrypted data seamlessly. 

### 2. Native Windows OS Integration
OSV natively binds to the Windows context menu. You can right-click any file or folder directly on your desktop or file explorer to:
*   **Lock Here Using OSV:** Encrypts the file in its current location, leaving behind a mathematically locked `.osv` file.
*   **Send to Vault:** Encrypts and securely moves the file into your central, hidden vault database.
*   **Unlock / Restore:** Right-click any `.osv` file to instantly decrypt and restore it to its original state (requires Master Password authorization).

### 3. Plausible Deniability (The Decoy Vault)
Built for extreme threat models (forced disclosure scenarios), OSV features a mathematically isolated secondary vault. 
*   By entering a specific "Decoy Password" at the login screen, the system boots into a completely separate SQLite database and cryptographic environment.
*   The Decoy Vault has zero cryptographic awareness of the Master Vault, and the Master Vault has zero awareness of the Decoy. 

### 4. Smart Uninstallation & Data Recovery
Handling the lifecycle of encrypted data is critical. OSV features a custom Windows uninstaller intercept. If a user attempts to uninstall the software via Windows Settings, OSV launches a secure recovery sequence, allowing the user to automatically decrypt and export all central vault files to a safe folder before the application footprint is wiped.

### 5. "Consume & Lock" DRM Engine
OSV uses a frictionless, hardware-agnostic licensing system. Upon first launch, the application reads the provided plaintext `license.txt`, verifies the developer's cryptographic signature, encrypts the payload into a hidden system cache, and permanently shreds the original text file to prevent unauthorized offline sharing.

---

## 🏗️ Technical Stack
*   **Backend Logic:** Python 3.x
*   **Cryptographic Engine:** `cryptography` (AES-256-GCM, PBKDF2 HMAC SHA256)
*   **Database:** SQLite3 (Local, air-gapped schema)
*   **User Interface:** PyQt6 (Asynchronous rendering, stacked widget routing)
*   **OS Integration:** Native Windows Registry manipulation (`ctypes`, `subprocess`)
*   **Deployment:** PyInstaller (Executable compilation) & Inno Setup (Pascal-based installation wizard)

---

## 📥 Installation Guide
Currently, OSV is in a closed beta testing phase. To install the software, you must have been issued a personal `license.txt` cryptographic signature file by Onkar.

1. Navigate to the **[Releases](../../releases)** page on this repository.
2. Download the latest `OSV Installation Setup.zip` file and extract it to your desktop.
3. Download the personal `license.txt` file provided to you via email.
4. Place the `license.txt` file directly inside the extracted setup folder, sitting exactly next to the `Onkars Secure Vault Setup v1.x.exe` file.
5. Run the Setup executable. The software will automatically ingest your license, verify the signature, and permanently secure it to your local environment.

---

## ⚖️ Proprietary Licensing, Legal Framework, & Terms of Use

### 1. Ownership of Intellectual Property & Copyright Notice
**Copyright © 2026 Mr. Onkar Shengule. All Rights Reserved.**

All components of this software application, including but not limited to the underlying source code (`.py`, `.iss`, configuration scripts, structural architectures), graphical user interface (UI) layouts, visual assets, binary executables (`.exe`), embedded local database schemas, and specialized cryptographic implementations, are the sole and exclusive intellectual property of the developer, **Mr. Onkar Shengule**. 

This software is protected under international copyright frameworks, proprietary desktop utility regulations, and digital property conventions. Unauthorized reproduction, modification, translation, reverse engineering, decompilation, or redistribution of any resource within this repository is strictly actionable under civil and criminal software piracy statutes.

---

### 2. Strict Restrictions on Use & Exclusive Commercialization
This repository is hosted publicly **strictly and exclusively for portfolio demonstration, technical peer review, and personal code evaluation.** 

By accessing, downloading, cloning, or interacting with this repository, you explicitly agree to the following legally binding constraints:
* **Exclusive Commercial Rights:** Only **Mr. Onkar Shengule** retains the absolute, unconditional, and exclusive rights for the commercialization, corporate deployment, white-label distribution, and monetization of this software application in professional terms. No other party is authorized to lease, sell, or license this code.
* **Prohibition of Derivative Works:** The designation of this software as an educational or portfolio project does **not** constitute a public license. You are strictly forbidden from modifying, rebranding, creating forks, or generating derivative software variants under the pretext of "educational use," "personal practice," or "academic research." 
* **No Public Binary Hosting:** You are legally unauthorized to host, mirror, package, or distribute compiled versions (`.exe` installers) of this application on third-party download portals, corporate servers, or decentralized torrent networks.

*Any violation of these terms, including the unauthorized extraction of core cryptographic logic or UI assets for commercial exploitation, will result in immediate legal escalation, including formal DMCA takedown requests and claims for intellectual property damages.*

---

### 3. Cryptographic Architecture & Cloud Connectivity Roadmap
The application's underlying security architecture is built upon the following strict parameters:
* **Current Offline Zero-Knowledge State:** Current operational versions of the software feature absolute local execution. The engine has no active external databases, remote tracking hooks, or telemetry layers capable of inspecting or filtering user files.
* **Future Cloud Implementation Notice:** While current builds maintain zero cloud dependencies for maximum local isolation, **future production releases may integrate targeted cloud network endpoints.** These cloud-based features will be implemented exclusively to handle secure global sales distribution, automated cryptographic license key verification, and over-the-air (OTA) updates.
* **Irreversible Mathematical Locked State:** Local encryption routines depend entirely on user-defined strings. If you forget your Master Password and lose access to your Stealth Recovery Keyfile, **your secured files are mathematically and physically irretrievable.** The developer, **Mr. Onkar Shengule**, holds no secret backdoors and cannot recover your data under any circumstances.

---

### 4. Comprehensive Limitation of Liability & Warranty Waiver
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, OPERATIONAL STABILITY, AND NON-INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS, DEVELOPERS, OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES, OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT, OR OTHERWISE, ARISING FROM, OUT OF, OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

**By installing, compiling, or executing this application, you explicitly and unconditionally agree that the developer, Mr. Onkar Shengule, holds zero legal, financial, or operational liability for:**
1. Any catastrophic data loss, structural file corruption, or permanent denial of access to local host directories.
2. Operating system conflicts, registry path errors, or system stability degradation following context menu shell integration.
3. Exploits arising from compromised user execution environments, weak passwords, or physical unauthorized access to the target hardware.

It remains the exclusive responsibility of the end-user to maintain redundant, unencrypted backups of critical personal or enterprise documents in an isolated, secure location prior to parsing them through any standalone desktop encryption engine.

---
<p align="center">
  <i>Engineered and Designed by Mr. Onkar Shengule</i>
</p>
