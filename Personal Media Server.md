# Scenario & Objective:
Develop and maintain a personal media server to play personal media across 4 devices for my local network utilizing legal open source software and methods.

# Tools Used:
- MakeMKV BETA
- BD-RE Matshita BD-MLT Disc Drive
- Jellyfin (Windows Server; Clients for WebOS, Windows, and Linux)
- Seagate 2TB Barracuda HDD (internal HDD originally used for storage, later swapped out)
- Inland 3.5" External SATA USB 3.0 HDD Enclosure (intended for Barracuda HDD) 
- Seagate Expansion 4TB HDD (external HDD for storage)
- Lenovo ideapad 5 laptop (battery removed, dedicated host of server)
- Raspberry Pi 5 4GB (original host of server, later swapped out)

# Process:
In order to run a Jellyfin server for a variety of devices - including desktops running Windows, an ROG Ally Z1E running a Bazzite distro, and an LG TV running WebOS, I originally planned to host the Jellyfin server on a dedicated Raspberry Pi 5.

This quickly resulted in multiple issues that had to be managed:
1) The Raspberry Pi 5 needs an external storage solution to keep terabytes of media. This was mediated by repurposing an internal Seagate 2TB Barracuda HDD within an external HDD enclosure.
2) The operating system flashed on this system, the Debian Linux-based distro Raspberry Pi OS, requires permissions to be set in order to read from a HDD/SSD that is by default formatted to Windows read/write formats (NTFS, exFAT, or FAT32).
3) The Raspberry Pi 5 runs every process through its CPU, resulting in bottlenecks without enough RAM or a GPU to aid its processing.
4) The Raspberry Pi 5 requires a static network for easier functionality when running Jellyfin as a Service rather than as a normal program.
5) The Raspberry Pi 5 cannot enable hardware acceleration.
Each of these issues made the utility of the Raspberry Pi 5 as a Jellyfin server largely unfeasible, as the single-board system can't consistently play lengthy high-definition media on multiple devices without bottlenecking or artificating the video playback. Though it could serve to play lower-resolution titles and shorter episodes for one device without buffering, the goal is for the server to play on multiple devices with high resolutions, which this single-board system cannot do.
---
Pivoting from the Raspberry Pi 5, I decided to repurpose a Lenovo ideapad 5 that I've used as a college laptop for 6+ years. As it had no real use once I graduated, it was time to give the system a new purpose in life.

Migrating from the Raspberry Pi 5 to the Lenovo ideapad 5 resulted in many upgrades:
1) To ensure that I don't cause a lithium-battery disaster in the longrun, I removed the battery from the laptop system and connected it to its charger, making it a permanent fixture.
2) Configuring the Jellyfin server within the Windows environment was much simpler in hindsight.
3) Organizing the media libraries required I migrate my media files previously housed in the internal Seagate 2TB Barracuda HDD housed in an external enclosure into a new 4TB Seagate Expansion HDD; Not only did this increase the storage space, but also ensured peace of mind due to the age of the 2TB HDD, which had migrated from multiple PC rigs over the years.
---
To ensure this media server is protected from compromise or intrusion, I did the following:
1) Ensured there would be no user list visible from the login screen, forcing each user to login with their respective usernames and passwords.
2) Enabled temporary account lockouts after 3 failed login attempts as a means to disrupt brute-force attempts.
3) Disabled most user permissions and kept administration permissions within my admin account.
4) Developed a reverse proxy specifically for the media server to ensure security and good performance.

# Executive Summary:
As a means to freshen up my tech-savvy nature and help my family at the same time, I decided to run a Jellyfin server with our personal media collection for a variety of devices, including desktops running Windows, an ROG Ally Z1E running a Bazzite distro, and an LG TV running WebOS. What began as an interesting idea very quickly became a daunting task thanks to multiple technological hiccups, from lengthy media conversion processes, Raspbian OS quirks, and network configuration hurdles. The result was a fully functional media server that works astonishingly well with polish and technical compentency comparable to a name-brand streaming service.
