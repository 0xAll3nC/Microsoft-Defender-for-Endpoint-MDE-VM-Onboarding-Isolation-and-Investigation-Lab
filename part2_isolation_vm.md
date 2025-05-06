# Part 2: Isolating a Windows VM via Microsoft Defender for Endpoint (MDE)

In this part, you'll simulate a potential attack scenario and manually isolate a VM using Microsoft Defender for Endpoint (MDE). This action is commonly used by security teams to contain compromised machines during an incident response.

---

## Objective

Use MDE to isolate a virtual machine from the network, preventing further compromise while still allowing forensic and remediation actions.

---

## Why Isolation?

Isolating a device:

- Cuts off most network communication to and from the VM.
- Prevents lateral movement and data exfiltration.
- Still allows MDE and Defender services to operate for analysis and control.

---

## Pre-Isolation Setup (Optional but Recommended)

Setting this up allows you to visually observe the effects of isolation.

### 1. Turn Off Windows Firewall on the VM

- Press **`Win + R`**, type **`wf.msc`**, and hit Enter.
- Disable all firewall profiles (Domain, Private, Public).

This allows easier communication for ping tests.

### 2. Modify Network Security Group (NSG) Rules (If using Azure)

- Go to your VM's NSG settings in the Azure portal.
- Allow **All Inbound Traffic**, or at a minimum, allow **ICMP (Ping)**.

### 3. Start a Continuous Ping to the VM

From your local machine or any external host:

```bash
ping <VM_PUBLIC_IP> -t
````

* You should see regular ping replies.
* This sets a baseline to observe when isolation is applied.

---

## Steps to Isolate the VM in MDE

### 1. Log in to the Microsoft Defender Security Portal

Visit: [https://security.microsoft.com](https://security.microsoft.com)

### 2. Navigate to Device List

```
Assets → Devices
```

### 3. Locate Your Virtual Machine

* Use the search bar to find your VM by hostname or IP.

### 4. Initiate Isolation

* Click the three-dot menu (⋯) in the upper-right corner.
* Select **Isolate device**.
* Confirm the prompt.

### 5. Observe Ping Timeout

* The ongoing ping command should stop receiving replies.
* This indicates the device has been successfully isolated from regular network traffic.

---

## Releasing the Device from Isolation (Optional)

After validation:

* Go back to the same device in MDE.
* Click the three-dot menu (⋯) again.
* Choose **Release from isolation**.
* Confirm.

---

## Result

* The device is now isolated from the network except for secure MDE communications.
* You can proceed with further actions like collecting investigation packages or performing remediation.

---

## 💡 Additional Tip

Isolation actions can also be automated as part of detection rules and incident response playbooks in MDE, enabling faster containment in enterprise environments.
