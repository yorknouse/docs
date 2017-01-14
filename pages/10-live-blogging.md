---
title: Live blogging
layout: page
---

We now use [Live Blog Pro](http://www.ocqur.com) (by Jonathan Frost and Andrew Fairbairn).
But here is some information about the old system, which should obviously be kept around in some form so that old live blogs can be enjoyed by future historians:

> The Nouse live blog system is powered by the Live Blogging for WordPress plugin, created by former technical director Chris Northwood. However, there are a lot of custom improvements on top of this (including tabbed streams and notifications, and individual comment updating) so – as with the several other plugins listed just above – it should not be upgraded except with extra care. The updating mechanism uses an installation of Meteor server (at data.nouse.co.uk) and is why our Linode account also has an extra IP address on it.
>
> It is connected to the @nouselive Twitter account, meaning that live blog posts are automatically tweeted out, and any tweets in reply to entries are automatically imported to WordPress as (unapproved) comments. If a live blog entry is deleted then the corresponding tweet also gets deleted, but if an entry is edited then the corresponding tweet does not change. The live blogging settings are managed though WordPress and this is where the Twitter settings can be changed if needed.  The Twitter settings on trunk should be automatically disabled to stop any test posts being tweeted out, but it is worth checking this.
>
> To create a new live blog, create a normal WordPress article but put the `[liveblog]` shortcode as the only text in the main body. Then find the Enable Live Blog box and tick the enable box.
>
> Also check [the Live Blogging Options page](http://www.nouse.co.uk/wp-admin/options-general.php?page=live-blogging-options) - when no live blogs are active, it's best to "Disable automatic updates", to stop an unnecessary javascript file being loaded.
>
> To disable a live blog, go to edit this main post again, untick the live blog enable box and click the Update button to save the change. **IT IS VERY IMPORTANT TO REMEMBER TO DISABLE LIVE BLOGS AFTER THEY ARE FINISHED**. If you do not then it causes an unnecessarily high load on the server, leading to detrimental performance.
>
> Live blog entries are added, edited and deleted in a similar way to normal articles, through the Live Blog Entries section of WordPress. When adding an entry, the current active live blog should be chosen in the Select Live Blog box. In the unlikely event that more than one live blog is active at once then you can choose which to add the entry to here. The author of an entry can also be changed but defaults to whoever is signed into WordPress.
>
> Several quick icons are available for live blogs, though currently the only ones available are sports related and a mixture of icons from Roses and Varsity. Because of this, they are powered by the Sports Scores plugin, and an up-to-date list of available icons can be seen in the code of that. The names of these icons and their corresponding images files should not be changed or deleted as that will break previous instances where they have been used. Icons are added in the format `[sport icon="icon-name"]` and should be placed at the beginning of live blog entries. Multiple icons or any text should be all separated by spaces (not line breaks).
>
> Here are the icons available at the time of writing...
>
>     [sport icon="red"]
>     [sport icon="yellow"]
>     [sport icon="york+1"]
>     [sport icon="york+2"]
>     [sport icon="york+3"]
>     [sport icon="york+4"]
>     [sport icon="hull+1"]
>     [sport icon="hull+2"]
>     [sport icon="hull+3"]
>     [sport icon="hull+4"]
>     [sport icon="ft"]
>     [sport icon="ht"]
>     [sport icon="york"]
>     [sport icon="hull"]
>     [sport icon="crowd"]
>     [sport icon="starplayer"]
>     [sport icon="weather"]
>     [sport icon="bnoc"]
>     [sport icon="streaker"]
>     [sport icon="crowdabuse"]
>     [sport icon="lanc1"]
>     [sport icon="lanc2"]
>     [sport icon="lanc3"]
>     [sport icon="lanc4"]
>     [sport icon="lanc-century"]
>     [sport icon="lanc-hcentury"]
>     [sport icon="lanc-wicket"]
>     [sport icon="lanc-goal"]
>     [sport icon="lanc-try"]
>     [sport icon="lanc-up"]
>     [sport icon="york-century"]
>     [sport icon="york-hcentury"]
>     [sport icon="york-wicket"]
>     [sport icon="york-goal"]
>     [sport icon="york-try"]
>     [sport icon="york-up"]
>     [sport icon="york1"]
>     [sport icon="york2"]
>     [sport icon="york3"]
>     [sport icon="york4"]


The Sports Scores and Live Blogging plugins should be kept active.
