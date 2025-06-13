🔧 Portmaster Privacy Firewall Configuration Guide
This project showcases my ability to securely deploy and configure Portmaster, an open-source privacy firewall, across endpoints — including employee workstations and IoT devices.

It balances strong privacy protections with real-world usability, ensuring VPN compatibility (like ProtonVPN) while blocking telemetry, ads, and other unnecessary traffic.

🎯 Project Goals
This configuration demonstrates my:

✅ Proficiency in configuring privacy and security tools
✅ Ability to troubleshoot DNS and firewall-related networking issues
✅ Skill in balancing privacy with day-to-day usability (e.g. VPNs, company apps)
✅ Readiness to configure endpoint protection on Windows/Linux/IoT in a business environment

🛠️ Hardened Configuration (Copy & Paste)
This setup is ideal for an average user or company device. It prioritizes privacy without breaking essential functionality.

type: settings
config:
    dns:
        noAssignedNameservers: true
    filter:
        blockInbound: true
        blockP2P: true
        lists:
            - TRAC        # Ads & Trackers
            - MAL         # Malware
            - DECEP       # Deceptive Sites
            - BAD         # Mixed Threats
            - PORN        # Adult Content
            - VIOL        # Violence
            - NSFWM       # Not Safe for Work (Memes)
            - EXPERIMENTS # Experimental Lists
            - UNBREAK     # Allow List for Stability


✅ Note: I intentionally left ForceBlockP2P and ForceBlockIncomingConnections off to prevent breaking VPNs like ProtonVPN. These can be enabled on a per-device basis if needed.

📥 Installation Options
🔗 Option 1: Download from Official Website
👉 https://safing.io/portmaster/download

Select the version for your operating system (Linux, Windows, etc.)

🖥️ Option 2: Install via Terminal (Debian-based Linux)
Use these commands to install Portmaster with GUI support on Ubuntu, Linux Mint, or other Debian-based systems:
# Step 1: Download the Portmaster installer script

wget https://releases.safing.io/portmaster/installer/linux.sh -O portmaster-installer.sh
# Step 2: Make the script executable
chmod +x portmaster-installer.sh

# Step 3: Run the installer with sudo privileges
sudo ./portmaster-installer.sh


🧪 What This Does
Installs Portmaster to /opt/portmaster

Registers it as a system service

Adds it to your application launcher

Starts automatically on boot

💡 Why It Matters
This setup ensures that all apps, not just your browser, are protected by DNS filtering, firewall controls, and traffic blocking — while keeping essential services like VPNs functional.

It’s a practical solution for:

🔒 Companies that want endpoint-level privacy without enterprise firewall complexity
📡 Users who want to block trackers, telemetry, and bad connections
🧑‍💻 IT teams looking for lightweight, user-deployable security tools



