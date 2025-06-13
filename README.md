🔧 Portmaster Privacy Firewall Configuration Guide
This project showcases my ability to deploy and configure Portmaster — a powerful open-source privacy firewall — for endpoint protection. It’s designed to balance strong privacy protections with usability, especially ensuring VPN functionality (e.g. ProtonVPN) stays intact while blocking unnecessary or unwanted traffic.

🎯 Project Goal
This setup demonstrates my:

✅ Proficiency in configuring privacy and security tools
✅ Ability to troubleshoot DNS and firewall-related networking issues
✅ Skill in balancing strong privacy with day-to-day usability (e.g. VPNs, system services)
✅ Readiness to configure endpoint protection across company devices (Windows/Linux/IoT)

🛠️ Portmaster Hardened Configuration
This config is designed for the "average user" — solid privacy, minimal breakage, and ready for deployment on employee devices.

yaml
Copy
Edit
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
            - NSFWM       # Not Safe for Work (Meme)
            - EXPERIMENTS # Experimental Lists
            - UNBREAK     # Allow List for Stability
✅ Note: I intentionally left ForceBlockP2P and ForceBlockIncomingConnections off to avoid breaking VPN connections. These can be re-enabled per device if needed — for example, ProtonVPN is explicitly allowed in my setup.

📥 Installation Options
You can install Portmaster on Linux in two ways:

🔗 Option 1: Download via Official Website
👉 [[https://safing.io/portmaster/download](https://safing.io/)](https://safing.io/)
Choose the installer for your OS (Linux, Windows, etc.)

🖥️ Option 2: Install via Command Line (Linux)
If you're using a Debian-based distro (like Ubuntu or Linux Mint), follow these steps to securely install the Portmaster GUI using your terminal:

bash
Copy
Edit
# Step 1: Download and run the official Portmaster installer
wget -qO - https://releases.safing.io/portmaster/installer/linux.sh | sudo bash
🔐 Note: sudo is required because the installer sets up Portmaster as a system service and installs it into /opt.

🧪 What This Does:
Downloads the latest Portmaster GUI app

Installs it under /opt/portmaster

Registers it as a system service so it auto-starts with your OS

Creates a desktop entry so it’s available in your application launcher

💡 Why It Matters
This makes sure Portmaster runs system-wide, protecting all apps — not just your browser. It's a smart way to block telemetry, trackers, and malicious connections on company devices while still allowing VPN connections like ProtonVPN to work properly.

💡 Why It Matters
This configuration is designed to block telemetry, ads, sketchy traffic, and unnecessary connections while keeping your VPN and core services functional. Ideal for companies wanting lightweight endpoint privacy without managing a full enterprise firewall stack.
