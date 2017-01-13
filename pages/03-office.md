---
title: The office
layout: page
---

The office is in [Grimston House](http://www.openstreetmap.org/way/60004913).

The office network is connected through a D-Link switch located on top of the cabinet to the right of the row of iMacs.
It is connected to the campus network (which also provides the whole office’s internet connection) through the port labelled _V/X/010/5_.
The switch [would ordinarily contravene some IT Services policies](http://www.york.ac.uk/it-services/connect/guidelines/) but allow it to exist as the alternative is to close the building for several weeks whilst asbestos contractors install additional ports.

There are three Intel Core 2 Duo iMacs which are newer (2008) aluminium models. There are also two older ([late 2006](http://support.apple.com/kb/Sp28)) plastic models which were recently decommissioned in favour of some newer Mac Minis.
There are also two headless servers -- `marconi` (the Dell) and `hunter` (the Viglen) -- and a [Macintosh Classic II](http://support.apple.com/kb/sp204), none of which are currently operational.

There is an old printer/scanner. Some information about it:

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
    nousemac6.york.ac.uk | XX:XX:XX:XX:XX:XX
    nousemac7.york.ac.uk | XX:XX:XX:XX:XX:XX

The numbering starts with the right-hand machine on the window-side of the room and works its way round to the left-hand machine on the opposite side. Each computer is also plugged into the corresponding numbered port on the switch.

All 5 machines are registered in the IT Services landb (Mice and Men) and should be acquiring IP addresses through DHCP. In cases where machines are moved and fail to get leased a new IP this is often due to an issue with the multi-lan ports used by IT Services.  Often unplugging and replugging the switch is enough to get the problem machine working (even if it is not now connected to the switch).

They can all be accessed using SSH from within the campus network. (Username `nouse`; passwords [redacted] above.) Off campus, you can go via the VPN or `csteach1.york.ac.uk`.

## Ideas

The iMacs are, apparently, all <del>horribly</del> slow. Some things that would help:

* RAM. The older two support up to 3GB each (1GB + 2GB). The newer three support 4GB (2GB + 2GB).
  - 1GB DDR2 PC2-5300 Unbuffered NON-ECC 1.8V 128Meg x 64. For the older two computers. I've bought two.
  - [2GB DDR2 PC2-5300 Unbuffered NON-ECC 1.8V 256Meg x 64](http://uk.crucial.com/gbr/en/imac-%28late-2006---2*0ghz-or-2*16ghz%29/CT3331830) (£22.79). For the older two computers. We have room for up to two of these chips.
  - [2GB DDR2 PC2-6400 Unbuffered NON-ECC 1.8V 256Meg x 64](http://uk.crucial.com/gbr/en/imac-2*66ghz-intel-core-2-duo-%2820-inch%29-mb324ll-a/CT3331877) (£22.79). For the newer three computers. We have room for up to six of these chips.
* SSDs would be lovely, but apparently require dismantling quite a lot of the iMac.

Shared files used to live in a shared folder on the iMac in the corner, and still do for historic reasons. (This folder may be referred to as "Marconi", because it used to be on the server of that name.) It's not a very good situation.
The IT Services storage service is now used to store files to ensure backups take place, make remote support easier and remove our reliance on a single machine (which is one of the less stable machines we have).

If we ever increase the video offering at Nouse (which has been tried on several occasions), nousemac6 has some additional software installed to aid in video editing and even live streaming.
