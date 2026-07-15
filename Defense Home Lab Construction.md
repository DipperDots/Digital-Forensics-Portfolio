# Scenario & Objective:
Develop and maintain a personal cybersecurity homelab for to hone cybersecurity skills in Security Information and Event Management (SIEM), Security Operations Center (SOC), Endpoint Detection and Response (EDR), and Vulnerability Management.

# Tools Used:
- Oracle VirtualBox
- Kali Linux (Attacker)
- Ubuntu 26.04 Live Server (Defense)
  - Wazuh & Splunk (Free Enterprise) SIEM
- Windows 11 Enterprise (Target 1)
  - Wazuh & Sysmon 
- Ubuntu Desktop (Target 2)

# Process:
In order to run a home lab to exercise cybersecurity practices, I needed to develop an isolated sandbox to perform actions that mimic various cyberattacks and exploits without harming my devices or network. This sandbox will allow me to hone my skills in SIEM, SOC, EDR, and Vulnerability Management.

This sandbox is composed of the following:
1) The Raspberry Pi 5 needs an external storage solution to keep terabytes of media. This was mediated by repurposing an internal Seagate 2TB Barracuda HDD within an external HDD enclosure.
2) The operating system flashed on this system, the Debian Linux-based distro Raspberry Pi OS, requires permissions to be set in order to read from a HDD/SSD that is by default formatted to Windows read/write formats (NTFS, exFAT, or FAT32).
3) The Raspberry Pi 5 runs every process through its CPU, resulting in bottlenecks without enough RAM or a GPU to aid its processing.
4) The Raspberry Pi 5 requires a static network for easier functionality when running Jellyfin as a Service rather than as a normal program.
5) The Raspberry Pi 5 cannot enable hardware acceleration.
Each of these issues made the utility of the Raspberry Pi 5 as a Jellyfin server largely unfeasible, as the single-board system can't consistently play lengthy high-definition media on multiple devices without bottlenecking or artificating the video playback. Though it could serve to play lower-resolution titles and shorter episodes for one device without buffering, the goal is for the server to play on multiple devices with high resolutions, which this single-board system cannot do.

<!-- Pivoting from the Raspberry Pi 5, I decided to repurpose a Lenovo ideapad 5 that I've used as a college laptop for 6+ years. As it had no real use once I graduated, it was time to give the system a new purpose in life.

Migrating from the Raspberry Pi 5 to the Lenovo ideapad 5 resulted in many upgrades:
1) To ensure that I don't cause a lithium-battery disaster in the longrun, I removed the battery from the laptop system and connected it to its charger, making it a permanent fixture.
2) Configuring the Jellyfin server within the Windows environment was much simpler in hindsight.
3) Organizing the media libraries required I migrate my media files previously housed in the internal Seagate 2TB Barracuda HDD housed in an external enclosure into a new 4TB Seagate Expansion HDD; Not only did this increase the storage space, but also ensured peace of mind due to the age of the 2TB HDD, which had migrated from multiple PC rigs over the years.
-->
# Executive Summary:
<!-- As a means to freshen up my tech-savvy nature and help my family at the same time, I decided to run a Jellyfin server with our personal media collection for a variety of devices, including desktops running Windows, an ROG Ally Z1E running a Bazzite distro, and an LG TV running WebOS. What began as an interesting idea very quickly became a daunting task thanks to multiple technological hiccups, from lengthy media conversion processes, Raspbian OS quirks, and network configuration hurdles. The result was a fully functional media server that works astonishingly well with polish and technical compentency comparable to a name-brand streaming service.
-->
