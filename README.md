<h1 align="center">🛡️ Onkar's Secure Vault (OSV) v1.0</h1>

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

## 📥 Beta Installation Guide
Currently, OSV is in a closed beta testing phase. To install the software, you must have been issued a personal `license.txt` cryptographic signature file by Onkar.

1. Navigate to the **[Releases](../../releases)** page on this repository.
2. Download the latest `OSV Installation Setup.zip` file and extract it to your desktop.
3. Download the personal `license.txt` file provided to you via email.
4. Place the `license.txt` file directly inside the extracted setup folder, sitting exactly next to the `Onkars Secure Vault Setup v1.0.exe` file.
5. Run the Setup executable. The software will automatically ingest your license, verify the signature, and permanently secure it to your local environment.

---

## ⚖️ Legal, Licensing, & Terms of Use

### Non-Commercial & Educational Use
This software is built explicitly for educational purposes, portfolio demonstration, and personal use by the developer and authorized beta testers. **It is strictly prohibited to copy, distribute, modify, or deploy this software for commercial, enterprise, or financial gain.**

### Strict Zero-Knowledge Disclaimer
This is a true Zero-Knowledge application. The developer has absolutely no access to your data, no cloud backups exist, and there are no developer "backdoors." **If you forget your Master Password and lose your Recovery Keyfile, your data is mathematically irretrievable.**

### Limitation of Liability (No Warranty)
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS, DEVELOPERS, OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE. 

**By installing and utilizing this software, you explicitly agree that the developer (Onkar) holds absolutely zero liability for any data loss, file corruption, or system issues that may occur.** Always maintain secondary backups of your critical plaintext data before utilizing standalone encryption tools.

---
<p align="center">
  <i>Engineered and Designed by Mr. Onkar Shengule</i>
</p>
