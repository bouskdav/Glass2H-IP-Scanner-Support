# GlassScan Privacy Policy

**Effective date:** September 20, 2026  
**Developer:** David Bouška

This policy describes how GlassScan for macOS handles information when you use the app.

## Overview

GlassScan is a network utility that processes scan results locally on your Mac. It does not automatically send scan results or settings to the developer. The app has no advertising, analytics, tracking tools, or developer-operated cloud service. No account or registration is required.

## Information stored on your Mac

GlassScan stores the following information in its local application preferences:

- Saved device results, including IP addresses, available hostnames and MAC addresses, detected services, response times, and last-seen timestamps.
- Favorite devices and custom device names.
- Your most recently used scan range and preferences such as interface language and MAC address column visibility.

Saved results are restored when you reopen the app. Their availability is marked as unverified until a new scan checks the devices.

## Network activity

To perform the actions you request, GlassScan sends network traffic:

- Device discovery uses ICMP requests and, when enabled, checks common TCP ports on the selected addresses.
- Manual port scans connect to the TCP ports you select on a target device.
- Hostname lookups use your system's configured DNS resolver.
- Wake-on-LAN sends a wake packet containing the target device's MAC address to the network.

Target devices, network operators, and DNS providers may observe or log this traffic, including your Mac's source IP address. Their handling of that information is governed by their own practices.

You can change GlassScan's local network permission in **System Settings → Privacy & Security → Local Network**.

## Exports, clipboard, and external applications

CSV exports contain the device information in the current filtered and sorted results. Files are saved only to a location you choose. If you choose a cloud-synced folder, your storage provider may sync the file under its own settings and privacy policy.

When you use a copy action, the selected information is placed on the macOS clipboard.

Opening an SSH, web, SMB, RDP, VNC, or GlassSSH connection passes the destination address and relevant connection information to an external application. That application handles authentication and subsequent communication under its own privacy practices. GlassScan's GlassSSH integration passes the target IP address and port; it does not pass passwords or private keys.

You control any further sharing of exported or copied information.

## Retention and deletion

Saved results and preferences remain on your Mac between sessions. Later scans update saved results; some earlier entries, including favorites, may remain. GlassScan does not apply an automatic expiration period to this local data.

You can remove a device from favorites or clear its custom name within the app. To erase all saved results and settings, quit GlassScan and remove its local application preferences or sandbox data. The location depends on the installed build; contact support below if you need help identifying the correct files. The app currently has no dedicated “delete all data” control. Deleting only the application may leave its saved data on your Mac.

Delete exported CSV files separately from the locations where you saved them. Copies in backups or cloud storage are managed through those services. The developer cannot remotely access or delete data stored on your Mac.

## Support requests

If you choose to contact the developer through GitHub Issues, the developer can view the information you submit and use it to respond to your request. GitHub processes that information under its [Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement).

GitHub issues are public. Do not include passwords, private keys, or other sensitive information. Anonymize network addresses, hostnames, screenshots, and scan results before posting when appropriate. Support posts remain on GitHub unless edited or removed in accordance with GitHub's features and policies.

## Changes to this policy

This policy may be updated to reflect changes to GlassScan or its data handling. The effective date above will identify the latest revision.

## Contact

For privacy questions or help removing local app data, contact **David Bouška** through the [GlassScan support issue tracker](https://github.com/bouskdav/Glass2H-IP-Scanner/issues). Ask for guidance without posting private data.
