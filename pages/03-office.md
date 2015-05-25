---
title: The office
layout: page
---

The office is in [Grimston House](http://www.openstreetmap.org/way/60004913).

The office network is connected through a D-Link switch located on top of the cabinet to the left of the row of newer iMacs.
It is connected to the campus network (which also provides the whole office’s internet connection) through the port labelled _V/X/010/5_.
The switch [possibly contravenes some IT Services policies](http://www.york.ac.uk/it-services/connect/guidelines/).

There are five Intel Core 2 Duo iMacs: three newer aluminium models and two older ([late 2006](http://support.apple.com/kb/Sp28)) plastic models.
There are also two headless servers -- `marconi` (the Dell) and `hunter` (the Viglen) -- and a [Macintosh Classic II](http://support.apple.com/kb/sp204), none of which are currently operational.

There might be a printer/scanner somewhere. Some information about it:

> The printer/scanner is connected to the left most older iMac (as you are facing them) and should be shared across all the Macs. If there are any issues with it, it is normally to do with the actual menu system on the printer. I think it refuses to do anything if there is some kind of message displayed on there so play around with the buttons on it to try and get rid of it.

It’s good to keep the Mac software up to date: click the Apple logo in the top-left then choose “Software Update” to install them. I used to do this after each edition had been finished.
Some computers have Microsoft Office installed which should also be checked for updates, though a lot less frequently.
Those without Microsoft Office have OpenOffice installed which again should be checked for updates on the same less frequent schedule.

Some updates may need a password to be installed, the password is ████████████████ for all except the editor’s machine `nousemac2` which at the time of writing is █████████.
This password is also needed to unlock that computer from sleep or the screensaver and it seems should not be given out to anyone.

These are the hostnames and MAC addresses for the 5 iMacs:

    nousemac1.york.ac.uk | 00:22:41:38:a8:97 
    nousemac2.york.ac.uk | 00:22:41:36:03:21 
    nousemac3.york.ac.uk | 00:22:41:35:f8:62 
    nousemac4.york.ac.uk | 00:19:e3:3b:49:56 
    nousemac5.york.ac.uk | 00:19:e3:3b:8b:9f

The numbering starts with the right-hand machine on the window-side of the room and works its way round to the left-hand machine on the opposite side. Each computer is also plugged into the corresponding numbered port on the switch.

All 5 machines are registered in the IT Services landb and should be acquiring IP addresses through DHCP. There are 

They can all be accessed using SSH from within the campus network. (Username `nouse`; passwords [redacted] above.) Off campus, you can go via the VPN or simply [port forwarding](https://twitter.com/louismrose/status/585367906957033472) (with `csteach0.york.ac.uk`, `teaching0.york.ac.uk` or similar).

## Ideas

The iMacs are, apparently, all horribly slow. Some things that would help:

* RAM. The older two support up to 3GB each (1GB + 2GB). The newer three support 4GB (2GB + 2GB).
  - 1GB DDR2 PC2-5300 Unbuffered NON-ECC 1.8V 128Meg x 64. For the older two computers. I've bought (but not yet installed) two.
  - [2GB DDR2 PC2-5300 Unbuffered NON-ECC 1.8V 256Meg x 64](http://uk.crucial.com/gbr/en/imac-%28late-2006---2*0ghz-or-2*16ghz%29/CT3331830) (£22.79). For the older two computers. We have room for up to two of these chips.
  - [2GB DDR2 PC2-6400 Unbuffered NON-ECC 1.8V 256Meg x 64](http://uk.crucial.com/gbr/en/imac-2*66ghz-intel-core-2-duo-%2820-inch%29-mb324ll-a/CT3331877) (£22.79). For the newer three computers. We have room for up to six of these chips.
* SSDs would be lovely, but apparently require dismantling quite a lot of the iMac.
* We also should be running a more recent version of OS X. Annoyingly, we're not where the installation media and license keys for Photoshop and InDesign are -- and the oldest two don't support anything newer than Lion -- but an upgrade from Leopard to Snow Leopard (not doing a clean install) would be a start.

Shared files all live in a shared folder on the iMac in the corner.
(This folder may be referred to as "Marconi", because it used to be on the server of that name.) It's not a very good situation.
I don't think backups are happening; data has been lost in the past and more will surely be lost in the future.
