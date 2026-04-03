# Lab: Resolving Windows Explorer Loop & System-Wide App Failure

## Scenario
The workstation experienced a persistent "Windows Explorer" crash loop (buffering taskbar) and a complete failure of system tools, including PowerShell and Command Prompt. This lab demonstrates the escalation from basic GUI fixes to the "Nuclear Option" (System Reset).

## Tools & Concepts Used
* **Windows Recovery Environment (WinRE)**
* **System File Checker (SFC)**
* **CompTIA A+ Core 2 Troubleshooting Theory**
* **OS Reinstallation (Local Reset)**

---

## Step 1: Initial Troubleshooting (GUI Level)
I first attempted to clear the File Explorer history to resolve potential cache corruption. 
* **Theory:** Corrupt thumbnails or recent file links can cause `explorer.exe` to hang.

![File Explorer Options](your_screenshot_name.png)

## Step 2: Escalation to WinRE (Recovery Mode)
When PowerShell and Command Prompt failed to launch within the OS, I forced the system into **WinRE** using the "Shift + Restart" method (and the "3-time Power Button" hard-stop trick).

![Recovery Menu](your_screenshot_name.png)

## Step 3: Diagnostic & System Repair
Inside the Advanced Options, I executed `sfc /scannow`. 
* **Result:** The system reported it "cannot find" the requested files, confirming deep registry or System32 corruption.

## Step 4: The "Nuclear Option" - System Reset
Since the OS could not identify its own repair tools, I initiated a **System Reset** while choosing "Keep my files."
* **Action:** Troubleshoot > Reset this PC > Local Reinstall.

![Resetting PC Progress](your_screenshot_name.png)

---

## Final Evaluation (A+ Iterative Learning)
1. **The Problem:** The Windows Registry and System32 file paths were likely corrupted by a failed update or malware, preventing `.exe` execution.
2. **The Resolution:** A Local Reset replaced the corrupted system image with a fresh copy while preserving user data.
3. **Next Steps:** Post-reset, I performed a **Windows Update** and re-installed **Display Drivers** to ensure hardware compatibility.
