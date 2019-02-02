---
title: The office
layout: page
---

The office is in Eric Milner Block A (next to James college but technically in Vanbrugh)

## Hardware

The office network is connected through a HP switch located on the floor by the window.  It is connected to the campus network through the port labelled _G/A/069-05_.  The switch is owned, managed and looked after by IT Services and shoudn't be tampered with. If you need to connect anything, you can use sockets 1 to 8 (the block of 8 on the left-side). Port 9 is the uplink port to the rest of the network and port 10 should be left empty. The two other sockets (gbic ones) should also remain unused.

One of the Macs is connected directly to 

There are three Intel Core 2 Duo iMacs which are 2008 aluminium models. There are two Mac Minis (from 2011 I believe).


There is a new Canon laser printer sat by the window - this was handled by the MD at the time so we don't know much about the setup beyond printer sharing having been configured on the Macs.

If a password is required, the password is ████████████████ for all except the editor’s machine `nousemac2` which at the time of writing is █████████.
This password is also needed to unlock that computer from sleep or the screensaver and it seems should not be given out to anyone.

These are the hostnames and MAC addresses for the 5 iMacs:

    nousemac1.york.ac.uk | 00:22:41:38:a8:97
    nousemac2.york.ac.uk | 00:22:41:36:03:21
    nousemac3.york.ac.uk | 00:22:41:35:f8:62
    nousemac6.york.ac.uk | 40:6c:8f:19:7f:4b
    nousemac7.york.ac.uk | 68:5b:35:ce:35:82

All 5 machines are registered in the IT Services landb (Mice and Men) and should be acquiring IP addresses through DHCP. In cases where machines are moved and fail to get leased a new IP this is often due to an issue with the multi-lan ports used by IT Services.  Often unplugging and replugging the switch is enough to get the problem machine working (even if it is not now connected to the switch due to how multi-ports are allocated and released).

They can all be accessed using SSH from within the campus network. (Username `nouse`; passwords [redacted] above.) Off campus, you can go via the VPN or the [Virtual Desktop Service](https://vds.york.ac.uk/html5).

## Software/Files

All machines have some common software installed on them.  All installers are either located at or linked from the Nouse Tech drive.  Some machines have special additional software installed on them also; nousemac3 has printer software and nousemac6 has video editing/broadcast software.

### Adobe Creative Cloud

This is installed from the YUSU installer linked from the Tech drive.  This is relatively convoluted install process as it required extracting three zip files (in order) and then running the installer located within the Build folder.  There is also an uninstaller located here, which should be run in the reverse order.  In all cases the install location needs to be changed manually to `/Applications/Adobe`.

The 5 licenses Nouse uses are funded by a YUSU media grant, and managed by IT Services.  These are the appropriate people to contact for support related issues (not Adobe).

### Microsoft Office/LibreOffice
Some machines are using very old versions of Microsoft Office on an old licence.  Machines otherwise run LibreOffice, which will replace Microsoft Office once the machines can no longer run it.

### McAfee Endpoint (for Endpoint Orchestrator)

This is the university provided security software.  It should only have the Threat Protection module installed.  We don't use Web Control/Protection or Firewall as the machines are not managed by IT Services.

### Browsers
mac OS ships with Safari.  We also install Firefox and Chrome to give people a choice of browser.

### Current and Archive (Network Volumes)

These are served by the Nouse Storage folder run by IT Services.  The folder itself if located at `smb://storage.its.york.ac.uk/yususocs/Nouse` with `current` and `archive` being sub-directories.  Storage can also be connected to on a Windows machine by a UNC path.  Any issues with the folder need to be directed to the YUSU IT Coordinator who is our DCO (Departmental Computing Officer).

The machines in the office map the folder using a non-personal IT account (which is "owned" by the Tech Director, remember to transfer ownership before leaving the university).  The password for this account is in the password database, and should be treated as a secret.

We also allow editors who own the correct version of InDesign to connect via their personal devices to the `current` folder only.  Access to this is handled by [permman](http://permman.york.ac.uk), and everyone's access (except that of the tech team and any `univ` or `admn` accounts) should be removed with the election of a new team.

## Building/Upgrading a machine

1. Install the latest version of OS X or mac OS (The minimum version we can use is OS X Yosemite 10.10.5)
2. Install any software updates from the App Store
3. Install McAfee Endpoint (or whatever endpoint protection the university uses; it has been Sophos in the past)
4. Restart the machine (McAfee say you don't have to, but you really should)
5. Install Adobe Creative Cloud
6. Open Adobe InDesign to make sure it is allocated a license
7. Install LibreOffice
8. Unmount the `tech` folder if it was used for installation
9. Mount `current` and `archive` from Storage, place the account (both with and without a domain on the user account) in KeyChain, and add them as Login items
10. Restart the machine and make sure the drives mount correctly
11. Enable SSH and VNC to allow remote administration
12. Install the fonts from Fonts.zip (Miller Text goes in to `/Applications/Adobe/Adobe InDesign CC 2015/Fonts` instead (Don't ask why, it just does))

If the machine has old versions of Adobe software, uninstall it once you are sure the new version is working correctly by using the uninstallers at `/Applications/Utilities/Adobe Installers` for the correct version.  Make sure you don't uninstall the new version otherwise it will require a wait whilst IT Services reset the license.

### Connect to Storage after mounting other Volumes

mac OS will always use the saved credentials to access files unless you explicitly specify otherwise by entering the server of the form `smb://username:*@storage.its.york.ac.uk/yususocs/Nouse`.  Please note you must enter your username and an asterisk after the colon to force the password prompt to appear.  Remember not to add any personal passwords to the KeyChain and to unmount drives when you've finished what you're doing.

## Ideas

The iMacs are, apparently, all <del>horribly</del> slow. Some things that would help:

* RAM. This was upgraded in the machines a while ago.  There's no more available capacity, and machines running older versions of OS X probably wouldn't benefit from it anyway.
* SSDs would be lovely, but apparently require dismantling quite a lot of the iMac and won't bring much benefit since all files are stored remotely.

Shared files used to live in a shared folder on the iMac in the corner, and still do for historic reasons. (This folder may be referred to as "Marconi", because it used to be on the server of that name.)
The IT Services storage service is now used to store files to ensure backups take place, make remote support easier and remove our reliance on a single machine (which is one of the less stable machines we have).
There are some drives in the office as well.  It is worth checking them to ensure their contents has been backed up elsewhere.

If we ever increase the video offering at Nouse (which has been tried on several occasions), nousemac6 has some additional software installed to aid in video editing and even live streaming.

Browsers are often accidentally left logged in to peoples accounts.  It may be worth installing some extensions which automatically clear cookies after a period of inactivity or on browser launch/exit.
