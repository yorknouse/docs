---
title: Uploading an edition
layout: page
---

The finished PDF files are located within the `PDFs to go` folder in the `Current Edition` folder on the iMac pretending to be Marconi.

## Extracting images

To extract the images from those files we use The Unarchiver.app, which should be installed on all of the office iMacs.
Just select all of the pdfs and then go to //Right-click// > //Open With// > //The Unarchiver.app//. This will then put all of the images from each pdf into a folder with the same name.

We can't upload tiff files to the website.

## Uploading to the Print Edition Archive

For the interactive viewer section, just go to http://issuu.com/ and it's pretty straightforward from there, though I'm not sure who has the login details for the account yorknouse.

The web version of the PDF also needs uploading to the appropriate folder within `/nouse/editions` and linking into the post -- see one of the older posts in the print edition archive for the wording to use.
The PDF should ideally be titled in the form `YYYY-MM-DD.pdf`.
(We've not been very dilligent about actually doing this...)

We used to have our own PDF viewer (see `wp-content/themes/nouse/js/nouse-pdf-viewer.js`) which no longer works.
It would be good to fix it and stop depending on the continued existence of Issuu.

### Uploading articles

There are some Python scripts somewhere for getting text out of PDFs and creating WordPress posts using XML-RPC.
They could be resurrected. Meanwhile, editors manually copy and paste articles from InDesign on the morning (Tuesday) of publication (or earlier, in which case they are scheduled for Tuesday morning).

The 'expand linebreaks' button in the WordPress post editor is useful. 