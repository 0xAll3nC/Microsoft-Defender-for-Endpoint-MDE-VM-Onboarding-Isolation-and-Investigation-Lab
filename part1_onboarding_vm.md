## ✅ `part1_onboarding_vm.md`

```markdown
# 🚀 Part 1: Onboarding a Windows VM to Microsoft Defender for Endpoint (MDE)

This section explains how to onboard a Windows Virtual Machine (VM) into Microsoft Defender for Endpoint (MDE), enabling real-time visibility and control over endpoint activity.

---

## 🎯 Objective

Securely onboard a Windows VM to MDE for monitoring, detection, and control capabilities.

---

## 🛠️ Prerequisites

- Access to [Microsoft Defender Security Portal](https://security.microsoft.com)
- A running Windows 10/11 or Windows Server VM (Azure, VMware, Hyper-V, or local)
- Admin rights on the VM
- Internet connectivity

---

## 🧩 Step-by-Step Instructions

### 1. Create a Windows Virtual Machine

-   Use a strong password during setup.
-   **Avoid using default credentials**, as weak credentials are vulnerable to brute-force attacks.

### 2. Log into Microsoft Defender Portal

- Go to: [https://security.microsoft.com](https://security.microsoft.com)

### 3. Navigate to the Onboarding Page

- Go to: **Settings → Endpoints → Device Management → Onboarding**

### 4. Download the Appropriate Onboarding Package

Choose the correct package for your OS:

- Windows 10/11
- Windows Server 2019/2022
- Linux (Ubuntu) — Python script

### 5. Install the Onboarding Script on the VM

- Transfer the package to your VM.
- **Right-click → Run as Administrator** to execute the onboarding script.

### 6. Verify Onboarding Success

- Go to: **Assets → Devices**

- Your VM should appear in the device list if onboarding was successful.

---

## 💡 Notes

- This step is foundational — you will use the onboarded VM for subsequent steps like isolation and investigation.
- You may power off the VM after onboarding. If deleted, you'll need to re-create and onboard a new VM.

---
