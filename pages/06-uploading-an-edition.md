---
title: Uploading an edition
layout: page
---

The finished PDF files are located within the `PDFs to go` folder in the `Current Edition` folder on the `Current` file store.

## Uploading to the Print Edition Archive

The finished print editions seem to be split up into many PDFs (one file per page, with some double page spreads being a single "page").
It is useful to merge these files before uploading, preferably keeping Nouse, Muse and any other supplements separarate.

The editors have a way of doing this -- I don't know what it is.
I use `pdftk` [which is good, apparently](https://blog.dbrgn.ch/2013/8/14/merge-multiple-pdfs/).
This command will merge all the PDF files beginning with `CFL0` in the current directory, in alphabetical order, into a file called `2015-04-21-muse.pdf`:

   pdftk CFL0* cat output 2015-04-21-muse.pdf

Files containing double page spreads will need to be renamed to be placed in the correct order.

It's also useful to then compress the combined PDF. Ghostscript is good at doing this without any terrible loss of quality or features:

    gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4  -dNOPAUSE -dQUIET -dBATCH -sOutputFile=2015-05-05-muse-compressed.pdf 2015-05-05-muse.pdf

For the interactive viewer section, just go to http://issuu.com/ and it's pretty straightforward from there, the login being in the password database. Embed the document(s) in a post in the Print Edition Archive category, with the correct date and with Nouse as the author (oEmbed is supported, so you can just paste in the Issuu URL like a YouTube video).

PDFs must also be uploaded to the appropriate folder of https://github.com/yorknouse/editions. The PDF should ideally be titled in the form `YYYY-MM-DD.pdf`.

## Extracting images

To extract the images from those files we use The Unarchiver.app, which should be installed on all of the office iMacs.
Just select all of the pdfs and then go to //Right-click// > //Open With// > //The Unarchiver.app//. This will then put all of the images from each pdf into a folder with the same name.

We can't upload tiff files to the website.


### Uploading articles

There are some Python scripts somewhere for getting text out of PDFs and creating WordPress posts using XML-RPC.
They could (and ideally should) be resurrected. Meanwhile, editors manually copy and paste articles from InDesign on the morning (Tuesday) of publication (or earlier, in which case they are scheduled for Tuesday morning).

The 'expand linebreaks' button in the WordPress post editor is useful.
