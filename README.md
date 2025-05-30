# 📄 Setup and Use a Firewall on Windows

## 🎯 Objective

To configure and test basic Windows Firewall rules to **block and allow specific network traffic**, demonstrating fundamental firewall management skills and understanding of how traffic filtering works.

---

## 🧰 Tools Used

* **Windows Defender Firewall with Advanced Security**
* **Telnet Client (enabled via DISM)**
* **Command Prompt (cmd)**

---

## 🪜 Steps to Reproduce

### 🔹 1. Open Windows Firewall Interface

* Run `Control` from the Run dialog (`Windows + R`) or search **Windows Defender Firewall with Advanced Security**.

### 🔹 2. View Existing Firewall Rules

* Navigate to **Inbound Rules** to see all current rules for incoming traffic.

### 🔹 3. Block Inbound Telnet Traffic (Port 23)

1. Click **New Rule** in the right panel.
2. Select **Port** → **TCP** → Enter `23` → **Block the connection**.
3. Apply to all profiles: **Domain, Private, Public**.
4. Name the rule `Block Telnet (Port 23)` and finish.

### 🔹 4. Test the Rule

* Run in Command Prompt:

  ```cmd
  telnet localhost 23
  ```
* You should receive:

  ```
  Connecting To localhost...Could not open connection to the host, on port 23: Connect failed
  ```

### 🔹 5. (Optional) Allow SSH (Port 22)

* Repeat the above process, but **allow** port `22` instead of blocking.

### 🔹 6. Remove or Disable the Rule

* Go to **Inbound Rules**, locate `Block Telnet (Port 23)`, and delete or disable it to restore default behavior.

---

## ✅ Expected Results

* Port 23 traffic is blocked by the firewall while the rule is active.
* Telnet connection to localhost on port 23 fails.
* SSH (if enabled) is allowed through port 22.
* System returns to original state after cleanup.

---

## 📷 Deliverables

Include the following in your submission:

* Screenshot of the **created firewall rule**.
* Screenshot of **Telnet connection failure** after applying the rule.
* This `README.md` file.

*Refer "Report.docx" for the screenshots
---

## 📘 Summary

This task demonstrates the use of **Windows Firewall** for **basic network traffic filtering**. Creating rules to allow or block specific ports enables administrators to enforce security policies, reduce attack surfaces, and monitor access to services like Telnet or SSH.

By blocking Telnet (a known insecure protocol), we simulate a common firewall configuration used in production environments.

---
