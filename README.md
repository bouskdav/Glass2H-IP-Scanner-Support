# GlassScan Support

GlassScan is a native IPv4 network scanner for **macOS 26 or later**, with a Liquid Glass interface and support for English and Czech. Discover devices on your network, inspect TCP ports, and open connections in your preferred clients.

This repository provides support information, troubleshooting guidance, and a place to report bugs or suggest improvements.

[Report a bug or request a feature](https://github.com/bouskdav/Glass2H-IP-Scanner/issues/new) · [Browse existing issues](https://github.com/bouskdav/Glass2H-IP-Scanner/issues)

## Features

- Scan local networks, individual IPv4 addresses, and custom ranges of up to 4,096 addresses.
- Check device availability and response time, with optional detection of common TCP services such as SSH, HTTP, HTTPS, SMB, RDP, and VNC.
- Explore selected TCP ports on an individual device.
- View DNS names and MAC addresses when available.
- Save favorites, assign custom device names, and search or sort results.
- Export the current filtered and sorted device list to CSV.
- Send Wake-on-LAN packets to supported devices.
- Open connections using installed clients, including optional GlassSSH integration.

## Getting started

1. Open GlassScan and allow **Local Network** access if macOS prompts you.
2. Select a network interface in the sidebar, or enter an IPv4 address or range.
3. Click **Scan network**. Results appear as the scan progresses; you can stop it at any time.
4. Select a device to view its details, or right-click it for connection and other actions.

Scan only networks you own or have permission to manage.

### Supported address formats

| Format | Example |
| --- | --- |
| Single IPv4 address | `192.168.1.1` |
| CIDR subnet | `192.168.1.0/24` |
| Short address range | `192.168.1.1-254` |
| Full address range | `192.168.1.10-192.168.2.20` |
| Ranges within address octets | `10.0-10.0.0-255` |

A scan can include up to **4,096 addresses**. For CIDR subnets, network and broadcast addresses are excluded except for `/31` and `/32`.

### Inspect TCP ports

Right-click a device and choose **Explore ports…**. Enter a range such as `1-1024` or a list such as `22,80,443,8000-9000`, then start the scan. Closing the dialog cancels the scan.

Port inspection runs only when you start it. Service names are inferred from port numbers; they do not identify the actual software or its version. UDP port scanning is not supported.

### Language and shortcuts

Open **Scan settings → Language** to select **English** or **Čeština**. English is the default. The interface updates immediately; native system menus may require an app restart.

| Action | Shortcut |
| --- | --- |
| Scan network | `⌘R` |
| Stop scanning | `⌘.` |
| Export CSV | `⌘E` |

## Troubleshooting

### A device does not appear

- Check that GlassScan has access under **System Settings → Privacy & Security → Local Network**.
- Confirm that you selected the correct network interface and IPv4 range.
- Make sure the device is powered on and reachable from your Mac.
- Check whether a VPN, firewall, or network isolation setting restricts access.

Devices that block both ICMP and the TCP ports checked during discovery may not be detected. GlassScan supports IPv4; IPv6 discovery is not available.

### A MAC address or hostname is missing

MAC addresses are generally available only for devices on the same local network segment. They may be unavailable across routers or VPNs. Hostnames depend on reverse DNS information provided by your network.

### Wake-on-LAN does not work

The target device needs a known MAC address, Wake-on-LAN support, and the appropriate power and network settings. GlassScan sends a UDP broadcast on port 9. Routers, VPNs, and network policies may prevent the packet from reaching the device.

### Opening a connection does not work

Install a client that supports the selected protocol and its URL links. For **Connect with GlassSSH**, install a compatible version of GlassSSH and launch it at least once so macOS can register its connection links. GlassSSH is a separate application and is optional for using GlassScan.

### Saved devices are marked “Unverified”

GlassScan restores the previous results when it opens. These saved entries do not confirm that a device is currently online. Run a new scan to refresh availability.

## Get support

[Open a GitHub issue](https://github.com/bouskdav/Glass2H-IP-Scanner/issues/new) to report a problem or ask for help. Please search [existing issues](https://github.com/bouskdav/Glass2H-IP-Scanner/issues) first in case the same topic has already been discussed.

For bug reports, include:

- GlassScan version and macOS version.
- A short description of the problem.
- Steps to reproduce it.
- What you expected and what happened instead.
- Relevant network context, such as Wi-Fi or Ethernet and whether a VPN is active.
- A screenshot or error message, if useful.

GitHub issues are public. Remove passwords, private keys, and other sensitive information. Anonymize IP addresses, MAC addresses, hostnames, and screenshots as needed while preserving enough detail to explain the issue.

For feature requests, describe what you want to accomplish and how the proposed feature would help.

## Privacy

GlassScan does not require an account and contains no advertising, analytics, or proprietary cloud service. Scan results, favorites, custom names, and settings are stored locally on your Mac and are not automatically sent to the developer. CSV exports are saved to a location you choose.

Scanning sends network requests to the selected devices and your configured DNS resolver. Wake-on-LAN sends a packet to the network. Opening a connection passes the target address to the relevant external application, which handles the connection under its own privacy practices.

**Developer:** David Bouška
