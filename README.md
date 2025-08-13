
Capturing Traffic in Wireshark (DNS and TCP Port 80 Filters)
📌 Overview
This project demonstrates how to use Wireshark to capture and analyze network traffic by applying specific capture and display filters for:

DNS (Domain Name System) traffic

TCP traffic on port 80 (HTTP)

The goal is to isolate relevant packets for easier inspection and troubleshooting.

🛠 Requirements
Wireshark installed on your system (Download here)

Administrative privileges to capture packets

An active network connection

📥 Capturing Traffic
1. Open Wireshark
Launch Wireshark with administrative privileges.

Select the network interface you want to capture from (e.g., Ethernet, Wi-Fi).

2. Applying Capture Filters
Capture filters limit what is captured before it’s stored in memory, reducing clutter and storage usage.

DNS only:

port 53
TCP port 80 only:

tcp port 80
DNS OR TCP port 80:

port 53 or tcp port 80
📌 Tip: Capture filters use Berkeley Packet Filter (BPF) syntax.

3. Applying Display Filters
Display filters let you see only the packets you’re interested in after capturing everything.

DNS only:

dns
TCP port 80 only:

tcp.port == 80
DNS OR TCP port 80:

dns || tcp.port == 80
🔍 Analysis Steps
Start the capture with the desired filter.

Perform activities that generate DNS and/or HTTP traffic:

Open a browser and visit a website (HTTP for port 80).

Perform a domain lookup (DNS query).

Stop the capture.

Use the packet list and packet details panes to inspect:

Source & destination IP addresses

Request/response details

Protocol behavior

📂 Output & Documentation
Save the capture file:

File → Save As → my_capture.pcapng
Include screenshots of:

Capture settings

Filter bar with applied filter

Example packet details

📝 Notes
HTTP traffic on port 80 is unencrypted, so full requests/responses can be inspected.

DNS requests may use UDP or TCP on port 53.

For HTTPS traffic (port 443), packet content will be encrypted, but DNS queries can still reveal the domains.

📚 References
Wireshark Capture Filters

Wireshark Display Filters
