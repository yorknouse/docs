---
title: Annual events
layout: page
---

In hopefully chronological order (Guideline dates really need adding).

This page attempts to straddle the line between providing information you can figure out for yourself, and not providing enough information.
In reading it, it becomes clear that lots of our website and things are horrible messes of bad code, and WordPress is not especially helpful -- sorry about that.

These instructions describe how to keep thing ticking over in a sort of homoeostasis, but we hope you'll want to change things to make them actually better.

## JCRC Elections

Not very exciting, but one of the first things in every academic year. There will be some coverage of each college's hustings and elections results, normally across two articles (one for hustings and one for results).

There is a plugin that adds college tabs to the page with some shortcodes.  This needs improving as it can be a bit unstable at times, but it does serve it's purpose.

## YUSU Elections

These happen every February. [Our websites for this](http://www.nouse.co.uk/elections/) are quite good.
Archived versions from 2009 onwards are all accessible via the drop-down menu, and the 2013-2017 sites are "live", running the current version of the source code.

There is a "Candidate" custom post type, which should be used for the elections candidates' "profiles".
Each should be placed in the special category for the position they're standing for.
Editors can do this all themselves.

Live blogs, news articles and things should be put in the YUSU Elections category.

Relevant files:

`/nouse/wp-content/themes/skeleton/category-elections.php`
: You'll need to update the `$election_year` stuff at the top. Visible at [/elections/](http://www.nouse.co.uk/elections/)

`/nouse/wp-content/themes/skeleton/archive-candidate.php`
: There's an identical `$election_year` bit to update identically. Oh yes, we espouse the "write everything twice" or "we enjoy typing" principle of software development! (Please improve this situation). Visible at [/elections/candidates/](http://www.nouse.co.uk/elections/candidates/)

`/nouse/wp-content/themes/skeleton/single-candidate.php`
: Template for displaying a candidate profile

`/nouse/wp-content/themes/skeleton/page-candidate-ratings.php`
: Note that there is a dummy Page with the slug `elections` which exists purely to give this page a parent. It's impossible to access the parent page, because the category of the same name takes precedence

`/nouse/wp-content/themes/skeleton/sidebar-elections.php`
: Used on some -- but not all - pages, I think. And doesn't contain the whole sidebar

`/nouse/wp-content/themes/skeleton/functions.php`
: The `after_navigation()` function, which produces the drop-down list of archived sites from previous years, is defined somewhere here. There's another year value to increment

`/nouse/wp-content/themes/skeleton/functions-taxonomy.php`
: Sets up the Candidate custom post type, and the Position taxonomy. It's a misleading file name, and the code should probably be moved to a plugin

People can click on thumb icons to express their feelings for candidates.
This is enabled by the Nouse Comment Voting plugin.
Don't call the candidate ratings an "exit poll" because you will anger psephologists.

### Ideas

Everything discussed here to do with elections is dependent on the current template remaining active.  Some serious thought needs to go into this as when the new theme is launched all elections pages (past, present and future) will stop working.  In particular candidate entries as they will become inaccessible.

## College Varsity

Previously, a one-day White Rose Varsity event took place against Hull University. Now, in its place, there is a College Varsity played against Durham. This is useful rehearsal for the Roses sport tournament (see below), for athletes and the media alike.

## Roses

The event which needs no introduction (but here we go anyway), Roses is the biggest inter-university sports tournament in Europe.  ViddyPrinter is used to provide the sports scoreboard on the right hand side, and LiveBlogPro to provide rolling coverage updates.

There are some set-up and code changes needed every year to get things ready.

### Ideas

ViddyPrinter is discussed elsewhere.  It could one day either integrate better with LiveBlogPro or replace it altogether.

There should really be stronger coupling between Varsity and Roses sites as well.  There is currently a lot of code duplication and inconsistencies between them which has caused issues in the past.

## Fantasy Football

Fantasy Football runs every summer term alongside the college football cup.
It’s quite popular.
You can begin thinking about it during the Easter holidays.

You’ll need the MySQL username (`fantasy_football`) and password for the `fantasy_football` database.
You can use phpMyAdmin, but other tools exist too.

A good first step each year is to update the default value of each database table’s year field.
Remember to do it for each table.
In phpMyAdmin, paste in this bunch of queries (use the “SQL” tab) to do it all in one go:

    ALTER TABLE `appearances` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `best_team` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `colleges` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `events` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `matches` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `players` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `players_last_week` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `teams` ALTER COLUMN `year` SET DEFAULT 2014;
    ALTER TABLE `users` ALTER COLUMN `year` SET DEFAULT 2014;

(Replace `2014` with the correct year.)

Ask the sports editors for a list of college teams. Import them into the colleges database table. If you do this in order of ‘group’ (once the college cup draw has taken place) then updating the college cup mini-site (which uses FF database to generate league tables) might be slightly easier.

MySQL will automatically assign each team a new numerical id.

id | name | year
44 | Halifax 1st | 2014
45 | Halifax 2nd | 2014
46 | Halifax 3th | 2014

Note that the values of the name field should not have ‘s’ at the end.

The players list needs: name, position and "cost"; college team captains are involved, so it might take the sports team a while.

Historically, sports editors have hand-written CSV (comma separated values) files :(

There's a spreadsheet template which is useful for the sport editors collecting the data, and even attempts to generate a bunch of SQL queries for inserting the data into the proper database (although phpMyAdmin and similar tools can in fact handle CSV and full-blown spreadsheet files):

https://docs.google.com/a/nouse.co.uk/spreadsheet/ccc?key=0Ajk4BEosguSmdDJJTmNkYmZSSVJPSTFOWkF6N1JjMWc

I suggest choosing File > Make a copy... and replacing all the previous year's data with this year's.

When the time comes to import the data:

1. Add the college teams to the colleges MySQL table
2. And add the automatically-generated-by-MySQL id fields (from step 1) to the colleges tab of the spreadsheet
3. Add the players to the players MySQL table
    - The cost column is in thousands of pounds (an occasional cause of confusion, but it would be wrong to use floating point numbers)
    - Don’t worry about most of the columns (e.g. goals, points) - they will be automatically set to 0


### Crossover players

It’s not currently possible for a player to be associated with one team. But in reality, ‘crossover’ players are common (someone might play for both Goodricke 1sts and Goodricke 2nds, for example). Historically, we have only had players score points for the better team only (Goodricke 1sts in that example), which is not a brilliant solution.

From the How to Play page:

Crossover players will only score points for the higher team. For example if Connor Meckin is registered to play for Halifax 1sts and as a cross-over to Halifax 2nds, he will not score any points for the his performance in the 2nds. This is in the interest of fairness, giving all players the opportunity to play an equal number of games. Bear this in mind when selecting your picks.

But it’s not really just in the interest of fairness - it’s because our software isn’t flexible enough. There would be some benefit to allowing editors to select from a list of all players at `/input-appearances/`

### Passwords

It is possible to manually reset a user’s password. Change the user’s confirmed field in the database to ‘no’, and email them a link like this:

http://www.nouse.co.uk/fantasy-football/register-confirm/?yorkid=aw1067&confirm=d0232be7ea95cc832a22f93bc84edc9e687442e9&name=Alex+Wooley&teamname=Unreal+Madrid

Where the username is aw1067, the confirmhash (from the database) is d0232be7ea95cc832a22f93bc84edc9e687442e9, the name is Alex Wooley, and the name of their team is Unreal Madrid. This is the same kind of link sent when someone creates an account, but with the additional fields to prepopulate the username and team name fields (the user nevertheless has an opportunity here to change their name). The form

We could fairly straightforwardly build in a proper password reset thing, based on this principle.

## College Cup

Once Fantasy Football is in place (which will take ages, I will provide more help along the way) then there's also the College Cup mini-site to slightly update.

http://www.nouse.co.uk/sport/college-cup/

This looks promisingly simple to update. Just change the second line in /wp-content/themes/skeleton/category-college-cup.php from

    if ( !in_array( $cc_year, range( 2013, 2014 ) ) ) { $cc_year = 2014; }

to

    if ( !in_array( $cc_year, range( 2013, 2015 ) ) ) { $cc_year = 2015; }

and also update the `after_navigation()` function in `/wp-content/themes/skeleton/functions.php`:

    'college-cup' => range( 2011, 2014 ),

becomes

    'college-cup' => range( 2011, 2015 ),


OK, here’s the tedious bit: you need to define which college teams are in which groups, for the league table to work. From 2014:

        case 2014:
            $groups = [
                '1' => [ 140, 143, 153, 156, 163, 160 ],
                '2' => [ 141, 144, 146, 151, 157, 161 ],
                '3' => [ 148, 149, 154, 155, 162, 159 ],
                '4' => [ 142, 145, 147, 150, 152, 158 ]
                ];
        break;
For 2015, add a new case:

        case 2015:
            $groups = [
                '1' => array[    ],
                '2' => array[    ],
                '3' => array[    ],
                '4' => array[    ]
                ];
        break;
    }

Each element in $groups is an array of the ids (from the colleges table of the fantasy football database) of the college teams in that group.

Of course you might want to do some more exciting things, like http://www.theguardian.com/football/world-cup-2014/overview. One idea: the sidebar code used to be in a separate file, which allowed us to display it next to college cup match report articles etc… But those changes are the bare minimum if you’re short of time.

If you open up /fantasy-football/fantasy-football.php from your copy of trunk then there are a few instructions at the top of there to get it set up.

Point 1 is basically a case of changing the York IDs on line 58 to yours and the sports editors as these are the people that will have access to the fantasy football admin panel once they have created an account.
Point 2 is adding to line 66
Point 3 it seems I already did
Point 4, you will need to ask the sports editors to give you the transfer period dates (I think these are usually between the group stages and knock out rounds). The dates themselves need to be entered (line 477 onwards) in timestamp format, so you can use a site likehttp://www.timestampgenerator.com/ to convert them (don't forget that we're currently on GMT+1 for BST)
Point 5, once you're ready to go, change the year on line 29 - no need to change the enabled variable on line 30 as looks like I forgot to change it back at the end of last year anyway!

Once it's all underway there's a script that you can run which will generate the "team of the week" that is shown on the fantasy football homepage based on the best scoring players from the previous week, so I'll dig out what that is and let you know later on.

### Ideas
Some form of WordPress plugin and new code in Fantasy Football could make things so much more manageable and require a lot less code editing.

## Freshers

This is the last event of the year for us before team elections, but it is also the one where we have to make a big impression with new students.  There is a mini-site which will be updated pretty much constantly from A-Level results day through to the end of Welcome Week.

There are templates for the freshers site to update and develop from (but again with the new server and theme this will likely change).
