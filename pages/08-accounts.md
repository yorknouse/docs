---
title: Accounts
layout: page
---

Editors are given Google Apps accounts and WordPress accounts.
Editors can also create unprivileged WordPress accounts for contributing writers, so that their names can appear on their articles on the website.

The process is a bit tedious.
We introduce more automation, but [haven't bothered yet](http://xkcd.com/1205/).
It helps if the workload is split between several people.

## Google Apps

We are grandfathered into a free Google Apps plan, which we use to provide elected members with prestigious `firstname.lastname@nouse.co.uk` email accounts and the sundry other Google services.
One day, this will probably end and we'll have to host our own email.
Meanwhile, we have a limit of 200 users, so should be gradually deleting the accounts of alumni who no longer use their accounts.

### Adding users

First, a current Super Administrator must give you an account and assign it Super Administrator status.

[The "admin console"](https://admin.google.com/nouse.co.uk/AdminHome) is where everything is done. (There are also official apps you can get on your mobile phone.)

You can create users one-by-one ("manually"). Google will generate random temporary password, and help you to send the details to the person's `@york.ac.uk` email address - if after account creation you click "more actions", then "email login info" in the modal that appears.

Alternatively, you can choose the "bulk" option, where you upload a CSV file (a sort of spreadsheet). This isn't quite as brilliant as it sounds: Google is a bit fussy about the formatting, and won't help you with generating passwords or emailing details.

### Groups

Most sections have "group" email addresses (e.g. `tech@nouse.co.uk`) of which the editors are all members.
Emails sent to `sport@nouse.co.uk` go to all the sports editors, for example.
After each election, be sure to add editors to [groups](https://admin.google.com/nouse.co.uk/AdminHome#GroupList:), and remove old editors from groups. Main editors are the owners of the respective group, and deputies are members except in the case of the deputy editor in chief - who is the owner of their group. 

Individuals can also have "aliases", but this is only used for common misspellings of people's names and for sections such as Film & Television where content can sometimes be presented as if they were two separate sections.
Even though `deputy-editor@nouse.co.uk` has only one recipient, it is a Group, because it's easier to manage like that.

Note that groups must all be explicitly configured to "Also allow anyone on the Internet to post messages" -- there's a box somewhere that needs to be ticked.

## WordPress

Some newly elected editors will already have WordPress accounts, if they have ever contributed articles before. Find these first, and change their roles from Contributor to Editor.

Create new accounts using [the Add New User form](https://www.nouse.co.uk/wordpress/wp-admin/user-new.php):

Username
: Firstname Lastname (e.g. “Joe Bloggs”) (yes, spaces are allowed)

Email
: The writer’s `@nouse.co.uk` address if they have one, otherwise maybe their university one

First Name
: Optional, but will affect the "... has written _n_ articles for Nouse" text, which is pretty cool

Password
: Don't worry about remembering it -- when the editors know their usernames, they can use the [Lost Password](https://www.nouse.co.uk/wordpress/wp-login.php?action=lostpassword)

Role
: Special trustworthy people can be _Administrators_. New editors are _Editors_.  Other writers, who will not be logging in themselves, are _Contributors_

The positions held by editors (e.g. _Deputy Food & Drink Editor_) go in the Biographical Info field (only available when you edit an existing user, apparently), and will appear automatically on the website. If someone changes position, replace (!) the text with their new position. If someone retires, append the years of their tenure in brackets (e.g. `(2010/11)` or `(2009–11)`).

## Who's Nouse

The [Who's Nouse](http://www.nouse.co.uk/about-nouse/whos-nouse/) page needs to be manually updated every year. But first, copy the old list to a page in the [Previous Editorial Teams](http://www.nouse.co.uk/archives/previous-editorial-teams/) section.

## The Nouse web server

See [SSH](08-accounts.html#).

## Ideas

* We could allow logging in to WordPress with people's Google accounts, or vice versa

* It is technically possible to have a WordPress user account without a password or unique email address (which would be very useful for the "contributor" accounts). We "just" need to create a custom form for registering these accounts

* See things about the accounts system mentioned elsewhere
