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
👉 https://safing.io/portmaster/download
Choose the installer for your OS (Linux, Windows, etc.)

🖥️ Option 2: Install via Command Line (Linux)
bash
Copy
Edit
wget -qO - https://releases.safing.io/portmaster/installer/linux.sh | bash
🛡️ This downloads and installs the latest Portmaster release and enables it as a service.

💡 Why It Matters
This configuration is designed to block telemetry, ads, sketchy traffic, and unnecessary connections while keeping your VPN and core services functional. Ideal for companies wanting lightweight endpoint privacy without managing a full enterprise firewall stack.
