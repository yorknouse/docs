---
title: The office
layout: page
---

The office is in Grimston House in Vanbrugh College (vaguely near Nisa).

The office network is connected through a D-Link switch located on top of the cabinet to the left of the row of newer iMacs.
It is connected to the campus network (which also provides the whole office’s internet connection) through the port labelled _V/X/010/5_.
Apparently using our own switch contravenes all sorts of IT Services policies, though they seem to be prepared to turn a blind eye to that for the time being at least.

There are five Intel Core 2 Duo iMacs: three newer aluminium models and two older plastic models.
There are also two headless servers -- `marconi` (the Dell) and `hunter` (the Viglen) -- and a [Macintosh Classic II](http://support.apple.com/kb/sp204), none of which are currently operational.

There might be a printer/scanner somewhere. Some information about it:

> The printer/scanner is connected to the left most older iMac (as you are facing them) and should be shared across all the Macs. If there are any issues with it, it is normally to do with the actual menu system on the printer. I think it refuses to do anything if there is some kind of message displayed on there so play around with the buttons on it to try and get rid of it.

It’s good to keep the Mac software up to date: click the Apple logo in the top-left then choose “Software Update” to install them. I used to do this after each edition had been finished.
Some computers have Microsoft Office installed which should also be checked for updates, though a lot less frequently.
Those without Microsoft Office have OpenOffice installed which again should be checked for updates on the same less frequent schedule.

Some updates may need a password to be installed, the password is ████████████████ for all except the editor’s machine `nousemac2` which at the time of writing is █████████.
This password is also needed to unlock that computer from sleep or the screensaver and it seems should not be given out to anyone.

These are the hostnames and MAC addresses for the 5 iMacs. 


    nousemac1.york.ac.uk | 00:22:41:38:a8:97 
    nousemac2.york.ac.uk | 00:22:41:36:03:21 
    nousemac3.york.ac.uk | 00:22:41:35:f8:62 
    nousemac4.york.ac.uk | 00:19:e3:3b:49:56 
    nousemac5.york.ac.uk | 00:19:e3:3b:8b:9f

The numbering starts with the right-hand machine on the window-side of the room and works its way round to the left-hand machine on the opposite side. Each computer is also plugged into the corresponding numbered port on the switch.

All 5 machines are registered in the IT Services landb and should be acquiring IP addresses through DHCP.

They can all be accessed using SSH from within the campus network. (Username `nouse`; passwords above.) Off campus, you can maybe go via `csteach0.york.ac.uk`.

## Ideas

The iMacs are, apparently, all horribly slow. Some things that would help:

* Installing the maximum amount of RAM. Easy.
* SSDs would be lovely, but apparently require dismantling quite a lot of the iMac.
* We also should be running a more recent version of OS X. Annoyingly, we're not where the installation media and license keys for Photoshop and InDesign are -- and the oldest two don't support anything newer than Lion -- but an upgrade from Leopard to Snow Leopard (not doing a clean install) would be a start.

Shared files all live in a shared folder on the iMac in the corner.
(This folder may be referred to as "Marconi", because it used to be on the server of that name.) It's not a very good situation.
I don't think backups are happening; data has been lost in the past and more will surely be lost in the future.
