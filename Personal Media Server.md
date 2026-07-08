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
1) The Raspberry Pi 5 needs an external storage solution to keep terabytes of media.
2) The Raspberry Pi 5 OS, Raspbian OS, requires permissions to be set in order to read from a HDD/SSD that is by default formatted to Windows read/write formats (NTFS, exFAT, or FAT32).
3) The Raspberry Pi 5 runs every process through its CPU, resulting in bottlenecks without enough RAM or a GPU to aid its processing.
4) The Raspberry Pi 5 requires a static network for easier functionality when running Jellyfin as a Service rather than as a normal program.

# Executive Summary:
As a means to freshen up my tech-savvy nature and help my family at the same time, I decided to run a Jellyfin server with our personal media collection for a variety of devices, including desktops running Windows, an ROG Ally Z1E running a Bazzite distro, and an LG TV running WebOS.
What began as an interesting idea became a daunting task very quickly thanks to multiple technological hiccups, lengthy media conversion processes, Raspbian OS quirks, and network configuration hurdles, ending in a server that works astonishingly well with polish and technical compentency comparable to a name-brand streaming service.
