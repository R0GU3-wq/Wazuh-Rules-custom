# 🛡️ Wazuh Rules - Custom Repository
This repository provides custom Wazuh rules for enhanced detection and monitoring of Windows, Linux, and security-related events. It is based on SOCFortress rules but customized and maintained in this repository.

# 📥 Installation
You can install the rules either manually or by using the provided script.
# 🔹 Manual Installation
Clone the repository and copy the rules to your Wazuh Manager:
# Navigate to a temporary directory
cd /tmp

# Clone this repository
git clone https://github.com/R0GU3-wq/Wazuh-Rules-custom.git /tmp/Wazuh-Rules

# Copy rules to Wazuh rules directory
sudo cp -r /tmp/Wazuh-Rules/* /var/ossec/etc/rules/

# Restart Wazuh Manager
sudo systemctl restart wazuh-manager

# 🔹 Install Using Script (wazuh_socfortress_rules.sh)
The repository includes a script to automatically download and install all rules.
# Download the script
wget https://raw.githubusercontent.com/R0GU3-wq/Wazuh-Rules-custom/main/wazuh_socfortress_rules.sh -O /tmp/wazuh_socfortress_rules.sh

# Make it executable
chmod +x /tmp/wazuh_socfortress_rules.sh

# Run the script
sudo bash /tmp/wazuh_socfortress_rules.sh

# ✅ The script will:

Download all rule files from this repository.
Place them in /var/ossec/etc/rules/.
Restart the Wazuh Manager to apply changes.


# 🔄 Updating Rules
To update your Wazuh rules to the latest version:
cd /tmp
rm -rf /tmp/Wazuh-Rules
git clone https://github.com/R0GU3-wq/Wazuh-Rules-custom.git /tmp/Wazuh-Rules
sudo cp -r /tmp/Wazuh-Rules/* /var/ossec/etc/rules/
sudo systemctl restart wazuh-manager

Alternatively, rerun the script:
sudo bash /tmp/wazuh_socfortress_rules.sh

Windows/: Rules for Windows environments (Sysmon, PowerShell, Event Logs).
Linux/: Rules for Linux systems (auth logs, SSH, sudo, kernel).
wazuh_socfortress_rules.sh: Script to automatically fetch and install rules.
README.md: Documentation.


# 📌 Notes

These rules are custom and may require testing before use in production.
Always back up your existing /var/ossec/etc/rules/ directory before applying updates.
If a rule conflicts with existing Wazuh built-in rules, edit the XML accordingly.


# 👨‍💻 Maintainer
R0GU3-wqCustom Wazuh Rule Development & Security Research
