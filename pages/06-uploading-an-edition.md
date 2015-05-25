---
title: Uploading an edition
layout: page
---

The finished PDF files are located within the `PDFs to go` folder in the `Current Edition` folder on the iMac pretending to be Marconi. If it's switched on, [you can access it remotely](03-office.html).

## Uploading to the Print Edition Archive

The finished print editions seem to be split up into many PDFs (one file per page, with some double page spreads being a single "page").
It is useful to merge these files before uploading, preferably keeping Nouse, Muse and any other supplements separarate.

The editors have a way of doing this -- I don't know what it is.
I use `pdftk` [which is good, apparently](https://blog.dbrgn.ch/2013/8/14/merge-multiple-pdfs/).
This command will merge all the PDF files beginning with `CFL0` in the current directory, in alphabetical order, into a file called `2015-04-21-muse.pdf`:

   pdftk CFL0* cat output 2015-04-21-muse.pdf

Files containing double page spreads will need to be renamed to be placed in the correct order, and different .

It's also useful to then compress the combined PDF. Ghostscript is good at doing this without any terrible loss of quality or features:

    gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4  -dNOPAUSE -dQUIET -dBATCH -sOutputFile=2015-05-05-muse-compressed.pdf 2015-05-05-muse.pdf

For the interactive viewer section, just go to http://issuu.com/ and it's pretty straightforward from there, though I'm not sure who has the login details for the account yorknouse. Embed the document(s) in a post in the Print Edition Archive category, with the correct date and with Nouse as the author (oEmbed is supported, so you can just paste in the Issuu URL like a YouTube video).

PDFs can also, and probably should, be uploaded to `edtions.nouse.co.uk`. `scp` them to your home folder, move them to the appropriate folder within `/nouse/editions`, and link to them in the post -- see one of the older posts in the print edition archive for the wording to use.
The PDF should ideally be titled in the form `YYYY-MM-DD.pdf`.
(We've not been very dilligent about actually doing this...)

We used to have our own PDF viewer (see `wp-content/themes/nouse/js/nouse-pdf-viewer.js`) which no longer works.
It would be good to fix it and stop depending on the continued existence of Issuu.


## Extracting images

To extract the images from those files we use The Unarchiver.app, which should be installed on all of the office iMacs.
Just select all of the pdfs and then go to //Right-click// > //Open With// > //The Unarchiver.app//. This will then put all of the images from each pdf into a folder with the same name.

We can't upload tiff files to the website.


### Uploading articles

There are some Python scripts somewhere for getting text out of PDFs and creating WordPress posts using XML-RPC.
They could be resurrected. Meanwhile, editors manually copy and paste articles from InDesign on the morning (Tuesday) of publication (or earlier, in which case they are scheduled for Tuesday morning).

The 'expand linebreaks' button in the WordPress post editor is useful. 