# Part 3: Collecting and Analyzing an Investigation Package via MDE

After isolating a suspicious endpoint, the next step is to collect forensic data for analysis. Microsoft Defender for Endpoint (MDE) allows you to remotely trigger and download an investigation package from any onboarded device.

---

## Objective

Simulate a real-world post-incident response by collecting system artifacts from an isolated VM to analyze signs of compromise.

---

## Prerequisites

- A VM that is onboarded to MDE
- Admin access to the Microsoft Defender portal
- Internet access to download the package from the portal

---

## Steps to Collect an Investigation Package

### 1. Log in to the MDE Portal

Visit: [https://security.microsoft.com](https://security.microsoft.com)

### 2. Navigate to Your Devices

**Assets → Devices**

### 3. Locate and Select Your VM

Use the search bar if needed.

### 4. Trigger the Investigation Package

- Click the three-dot menu (⋯) on the top right of the VM page.
- Choose **Collect investigation package**.
- Add a brief comment for context (e.g., "Post-isolation scan for suspicious behavior").
- Confirm the action.

### 5. Track Progress in Action Center

- Navigate to:

**⋯ → Action Center**

- Wait for the collection process to complete.
- You may need to refresh after a few minutes.

---

## Download and Extract the Package

Once the investigation package is ready:

1. Click the download link in the Action Center.
2. Unzip the `.zip` file on your local machine.
3. Explore the contents.

---

## Contents of the Investigation Package

The package typically includes:

- **Running processes** (`processlist.csv`)
- **Scheduled tasks**
- **Autoruns** (startup items)
- **Open network connections**
- **Loaded drivers**
- **Security, application, and system event logs**
- **Registry snapshot**
- **WMI persistence checks**

---

## Use Cases

- Identify suspicious persistence mechanisms (e.g., unusual startup programs)
- Analyze network activity or unauthorized connections
- Compare current processes with baseline behavior
- Correlate log events to timelines of suspicious activity

---

## Best Practices

- Correlate findings with threat intelligence or known indicators of compromise (IOCs)
- Compare multiple devices if multiple endpoints were affected
- Use investigation package data to guide next steps like remediation or full malware analysis

---

## Tip

You can also automate investigation package collection using Microsoft Defender’s Live Response or Microsoft Sentinel integration.

---

## Summary

Investigation packages provide rich, low-level data about the state of a system. Combined with isolation, they offer a safe and effective way to investigate potential breaches without tipping off adversaries or risking further damage.

