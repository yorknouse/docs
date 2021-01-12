---
title: Storage
layout: page
---

Nouse has a fair few different places it stores current and historical files.

# S3 Bucket

Our S3 Bucket is actually a Backblaze B2 bucket as it was cheaper at the time of writing and suited our needs better.

Files are tracked in the database, under `s3files` table.

## Uploads

- User uploads a file in the browser directly to Backblaze
- Once this is successful the upload is added to the database
- Eventually the compressor script will come along and compress it if it's an image

**Please avoid hardcoding paths to the s3 bucket - it's much easier to use environment variables as it allows us to change provider painlessly**


# NAS

The NAS for the office are served by the Nouse Storage folder run by IT Services.  The folder itself if located at `smb://storage.its.york.ac.uk/yususocs/Nouse` with `current` and `archive` being sub-directories.  Storage can also be connected to on a Windows machine by a UNC path.  Any issues with the folder need to be directed to the YUSU IT Coordinator who is our DCO (Departmental Computing Officer).

The machines in the office map the folder using a non-personal IT account - univ (which is "owned" by the Tech Director, remember to transfer ownership before leaving the university).  The password for this account should be treated as a secret.

We also allow editors who own the correct version of InDesign to connect via their personal devices to the `current` folder only.  Access to this is handled by [permman](http://permman.york.ac.uk), and everyone's access (except that of the tech team and any `univ` or `admn` accounts) should be removed with the election of a new team.