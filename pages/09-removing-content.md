---
title: Removing content
layout: page
---

Occasionally a request will come in for content to be removed from the website because it is a bit awkward and showing up in high ranking positions on search engines like Google when you type in someone’s name.  This does not, however, mean that the content has to be deleted from the site (unless requested so for legal reasons!).

## WordPress

There is an easy way to stop an individual article from appearing in search engines.
Simply go to the edit screen for that post in WordPress, find the *Exclude Search Engines* box and tick the box in there, then click the post’s big *Update* button to save the change.

This change can take a few days or even weeks to propagate through to the search engines but eventually will cause that page to disappear from their results.

If you need to go further in removing content, try and leave deleting something completely as a last resort.
Removing or changing occurrences of someone’s name in an article is often also an option.

If the complaint is from Google themselves then it can often be resolved by disabling advertising for a single page by ticking the box in WordPress.

## PDFs

Sometimes we get asked to edit old PDFs in the print edition archive.
The best tool is [Nuance PDF Coverter](http://www.york.ac.uk/it-services/it/software/a-z/pdf-converter/#tab-1), which is installed on all campus PCs _and_ there's a university-provided license code for home use.
It's a bit fiddly to use, but it does the job really well -- it _completely_ removes selected text and graphics (it doesn't just draw a box on top), while perfectly preserving everything else ([example](http://www.nouse.co.uk/wp-content/article_images/body/2007/12/08.pdf)).

**(needs more detailed hints about how to use the redaction feature)**

Old PDFs hosted on our website have to be downloaded, edited, re-uploaded using `scp` or `rsync`, and moved back to the right place in `/var/www/article_images/body/` (remember to give `www-data` ownership of them once they're there).

More recent print editions are hosted on Issuu, which is different and I don't know about.

## Encouraging Google to re-index pages

You can use the [Fetch as Google](https://www.google.com/webmasters/tools/googlebot-fetch?siteUrl=http://www.nouse.co.uk/) thing in Google Webmaster Tools (you should be given access) to prod Google about changes to old articles. Paste in the relevant part of the url (minus the `http://www.nouse.co.uk/`), click _Fetch_, and then wait and click _Submit to index_.

## Reports
People can report issues via a report button on each comment on the site.  These reports are delivered to the web team who can then act on them.  These requests are primarily handled by the Online Editor, but the tech team can also handle them.
