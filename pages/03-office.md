---
title: The office
layout: page
---

The office is in [Grimston House](http://www.openstreetmap.org/way/60004913).

## Hardware

The office network is connected through a D-Link switch located on top of the cabinet to the right of the row of iMacs.  It is connected to the campus network (which also provides the whole office’s internet connection) through the port labelled _V/X/010/5_.  The switch [would ordinarily contravene some IT Services policies](http://www.york.ac.uk/it-services/connect/guidelines/) but allow it to exist as the alternative is to close the building for several weeks whilst asbestos contractors install additional ports.

There are three Intel Core 2 Duo iMacs which are newer (2008) aluminium models. There are also two older ([late 2006](http://support.apple.com/kb/Sp28)) plastic models which were recently decommissioned in favour of some newer Mac Minis.  There are also two headless servers -- `marconi` (the Dell) and `hunter` (the Viglen) -- and a [Macintosh Classic II](http://support.apple.com/kb/sp204), none of which are currently operational.

There is an old printer/scanner stored in the archive area. Some information about it:

> The printer/scanner is connected to the left most older iMac (as you are facing them) and should be shared across all the Macs. If there are any issues with it, it is normally to do with the actual menu system on the printer. I think it refuses to do anything if there is some kind of message displayed on there so play around with the buttons on it to try and get rid of it.

There is a new Canon laser printer sat in front of the switch which was recently purchased.  This was handled by the MD so we don't know much about the setup beyond printer sharing having been configured on some (but not all) of the Macs.

If a password is required, the password is ████████████████ for all except the editor’s machine `nousemac2` which at the time of writing is █████████.
This password is also needed to unlock that computer from sleep or the screensaver and it seems should not be given out to anyone.

These are the hostnames and MAC addresses for the 5 iMacs:

    nousemac1.york.ac.uk | 00:22:41:38:a8:97
    nousemac2.york.ac.uk | 00:22:41:36:03:21
    nousemac3.york.ac.uk | 00:22:41:35:f8:62
    nousemac4.york.ac.uk | 00:19:e3:3b:49:56 (retired)
    nousemac5.york.ac.uk | 00:19:e3:3b:8b:9f (retired)
    nousemac6.york.ac.uk | 40:6c:8f:19:7f:4b
    nousemac7.york.ac.uk | 68:5b:35:ce:35:82

The numbering starts with the right-hand machine on the window-side of the room and works its way round to the left-hand machine on the opposite side. Each computer is also plugged into the corresponding numbered port on the switch.

All 5 machines are registered in the IT Services landb (Mice and Men) and should be acquiring IP addresses through DHCP. In cases where machines are moved and fail to get leased a new IP this is often due to an issue with the multi-lan ports used by IT Services.  Often unplugging and replugging the switch is enough to get the problem machine working (even if it is not now connected to the switch).

They can all be accessed using SSH from within the campus network. (Username `nouse`; passwords [redacted] above.) Off campus, you can go via the VPN,  `csteach1.york.ac.uk`, or the [Virtual Desktop Service](https://vds.york.ac.uk/html5).

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

We also allow editors who own the correct version of InDesign to connect via their personal devices to the `current` folder only.  Access to this is handled by [permman](http://permman.york.ac.uk), and everyone's access (except that of the tech team and any `univ` or `adm` accounts) should be removed with the election of a new team.

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

mac OS will always use the saved credentials to access files unless you explicitly specify otherwise by entering the server of the form `smb://username:*@storage.its.york.ac.uk/yususocs/Nouse`.  Please note you must enter your username and an asterisk after the colon to force the password prompt to appear.  Remember not to add any personal passwords to the KeyChain.

## Ideas

The iMacs are, apparently, all <del>horribly</del> slow. Some things that would help:

* RAM. The older two support up to 3GB each (1GB + 2GB). The newer three support 4GB (2GB + 2GB).
  - [2GB DDR2 PC2-5300 Unbuffered NON-ECC 1.8V 256Meg x 64](http://uk.crucial.com/gbr/en/imac-%28late-2006---2*0ghz-or-2*16ghz%29/CT3331830) (£22.79). For the older two computers. We have room for up to two of these chips.
  - [2GB DDR2 PC2-6400 Unbuffered NON-ECC 1.8V 256Meg x 64](http://uk.crucial.com/gbr/en/imac-2*66ghz-intel-core-2-duo-%2820-inch%29-mb324ll-a/CT3331877) (£22.79). For the newer three computers. We have room for up to six of these chips.
* SSDs would be lovely, but apparently require dismantling quite a lot of the iMac and won't bring much benefit since all files are stored remotely.

Shared files used to live in a shared folder on the iMac in the corner, and still do for historic reasons. (This folder may be referred to as "Marconi", because it used to be on the server of that name.) It's not a very good situation.
The IT Services storage service is now used to store files to ensure backups take place, make remote support easier and remove our reliance on a single machine (which is one of the less stable machines we have).

If we ever increase the video offering at Nouse (which has been tried on several occasions), nousemac6 has some additional software installed to aid in video editing and even live streaming.

Browsers are often accidentally left logged in to peoples accounts.  It may be worth installing some extensions which automatically clear cookies after a period of inactivity or on browser launch/exit.
