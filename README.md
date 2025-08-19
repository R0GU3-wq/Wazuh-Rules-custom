Got it 👍 — here’s the **full `README.md` in proper Markdown format** (with all headings, subheadings, and content included):

````markdown
# 🛡️ Wazuh Rules - Custom Repository

This repository provides **custom Wazuh rules** for enhanced detection and monitoring of Windows, Linux, and security-related events.  
It is based on SOCFortress rules but customized and maintained under this repository.  

---

## 📥 Installation

You can install the rules **manually** or by using the provided **script**.

---

### 🔹 Manual Installation

Clone the repo and copy rules into your Wazuh Manager:

```bash
# Navigate to a temporary directory
cd /tmp

# Clone this repository
git clone https://github.com/R0GU3-wq/Wazuh-Rules-custom.git /tmp/Wazuh-Rules

# Copy rules to Wazuh rules directory
sudo cp -r /tmp/Wazuh-Rules/* /var/ossec/etc/rules/

# Restart Wazuh Manager
sudo systemctl restart wazuh-manager
````

---

### 🔹 Install Using Script (`wazuh_socfortress_rules.sh`)

The repository includes a script to **automatically download and install all rules**.

```bash
# Download the script
wget https://raw.githubusercontent.com/R0GU3-wq/Wazuh-Rules-custom/main/wazuh_socfortress_rules.sh -O /tmp/wazuh_socfortress_rules.sh

# Make it executable
chmod +x /tmp/wazuh_socfortress_rules.sh

# Run the script
sudo bash /tmp/wazuh_socfortress_rules.sh
```

✅ The script will:

* Download all rule files from this repository.
* Place them in `/var/ossec/etc/rules/`.
* Restart the Wazuh Manager to apply changes.

---

## 🔄 Updating Rules

To update your Wazuh rules to the latest version:

```bash
cd /tmp
rm -rf /tmp/Wazuh-Rules
git clone https://github.com/R0GU3-wq/Wazuh-Rules-custom.git /tmp/Wazuh-Rules
sudo cp -r /tmp/Wazuh-Rules/* /var/ossec/etc/rules/
sudo systemctl restart wazuh-manager
```

Or, simply **rerun the script**:

```bash
sudo bash /tmp/wazuh_socfortress_rules.sh
```

---

## 📂 Repository Structure

```
Wazuh-Rules-custom/
├── Windows/
│   ├── powershell_rules.xml
│   ├── sysmon_rules.xml
│   └── ...
├── Linux/
│   ├── auth_rules.xml
│   └── ...
├── Cloud/
│   ├── aws_rules.xml
│   ├── azure_rules.xml
│   └── ...
├── wazuh_socfortress_rules.sh
└── README.md
```

* **Windows/** → Rules for Windows environments (Sysmon, PowerShell, Event Logs).
* **Linux/** → Rules for Linux systems (auth logs, SSH, sudo, kernel).
* **Cloud/** → Rules for cloud providers (AWS, Azure, GCP).
* **wazuh\_socfortress\_rules.sh** → Script to automatically fetch and install rules.
* **README.md** → Documentation.

---

## 📌 Notes

* These rules are **custom** and may require testing before use in production.
* Always back up your existing `/var/ossec/etc/rules/` directory before applying updates.
* If a rule conflicts with existing Wazuh built-in rules, edit the XML accordingly.

---

## 👨‍💻 Maintainer

**R0GU3-wq**
Custom Wazuh Rule Development & Security Research

---

```

Do you want me to also create the **final version of `wazuh_socfortress_rules.sh`** in `.sh` format so that anyone following this `README.md` can run it without editing?
```
