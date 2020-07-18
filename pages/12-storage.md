---
title: Storage
layout: page
---

Nouse has a fair few different places it stores current and historical files.

# S3 Bucket

Our S3 Bucket is actually a DigitalOcean space as it was cheaper at the time of writing and suited our needs better. 
Directory structure as follows

- `archive`

	`public`
	
		`articles` A PDF generated of the 17k articles that existed before the site was migrated away from WordPress for posterity. They are linked to from the website in various places and form a core part of our archive

		`images` All the images from articles written in WordPress
		
- `db` Anything in here is managed by the CMS and SHOULD NOT BE EDITED MANUALLY - if you need to make a change here please try and make sure you tell the database correctly
	
	`webUploads`
	
			`public`
			
				`USER-THUMNAIL` Thumnail icons for users
				
				`ARTICLES` Images used in articles