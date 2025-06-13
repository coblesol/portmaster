🔧 Portmaster Privacy Firewall Configuration Guide
This configuration showcases how I securely deployed and configured Portmaster as a software firewall across user endpoints (including IoT devices), while maintaining functionality for essential tools like ProtonVPN.

✨ Project Goal
This setup demonstrates:

✅ Proficiency in configuring privacy/security tools

✅ Ability to troubleshoot DNS and firewall-related networking issues

✅ Balancing privacy with functionality — especially VPN compatibility

🛡️ Hardened Privacy Configuration (Copy and paste this into portmaster) 
You will go to settings then you will see import settings from there copy and pasye from tpye: settings all the way to # Ensures essential services work 

type: settings
config:
  dns:
    noAssignedNameservers: true         # Prevent fallback to insecure DNS
    noInsecureProtocols: true           # Use DNS-over-TLS/HTTPS only
  filter:
    lists:
      - TRAC                            # Ads & Trackers
      - MAL                             # Malware Domains
      - DECEP                           # Deceptive Sites
      - BAD                             # Mixed Threats
      - PORN                            # Adult Content
      - VIOL                            # Violent Content
      - NSFWM                           # NSFW Mixed
      - EXPERIMENTS                     # Optional/Experimental Filters
      - UNBREAK                         # Ensures essential services work

💡 Note: ForceBlockP2P and ForceBlockIncomingConnections are not enabled globally to avoid breaking VPN functionality. These settings can be applied per-app if needed (e.g., allow ProtonVPN-or any other VPN).

👨‍💻 Application-Specific Example
ProtonVPN(or any other VPN (Bypass Firewall Rules)
Use case: Block all direct/P2P traffic except for ProtonVPN

Action:

Enable ForceBlockP2P and ForceBlockIncomingConnections globally

Go to Connections → ProtonVPN

Allow all traffic for that app

This ensures:

Local/IoT attack vectors are blocked

Only trusted VPN traffic is permitted

🔐 Secure DNS GUI Settings (Portmaster Equivalent)
Setting	Value
No Assigned Nameservers	Enabled
No Insecure Protocols	Enabled
Use Secure Protocols Only	Enabled
Block Unofficial TLDs	Enabled

📚 Filter Lists Reference
Filter List	Description
TRAC	Blocks trackers and ads
MAL	Blocks known malware domains
DECEP	Deceptive/phishing-style domains
BAD	Mixed threats (ads, malware, deception)
PORN	Adult content
VIOL	Violent content
NSFWM	NSFW mixed types
EXPERIMENTS	Optional/experimental filters
UNBREAK	Whitelist for commonly broken essentials

🛠️ Troubleshooting VPN Issues
VPN Not Connecting?
✅ Double-check if P2P/Incoming connections are globally blocked

✅ Ensure VPN app isn’t being filtered under Connection > App

✅ Allow specific domains or ports (if needed)

✅ Try Resetting Portmaster:

sh
Copy
Edit
Rename:
C:\Users\<YourName>\AppData\Roaming\Portmaster
Restart the app.
📄 Portfolio / Resume Highlights
By maintaining this config and documentation, I show employers that I:

⚙️ Can deploy and manage Portmaster across devices

🔐 Understand endpoint-level privacy controls

🧠 Know how to avoid blocking mission-critical services like VPNs

🧰 Can troubleshoot and resolve firewall conflicts proactively

Maintained by: Zach Coble
GitHub: @coblesol
LinkedIn: Zach Coble

