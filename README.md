# Youtube-Video-Tracking
This will track if a user Plays, Pauses or Finished a video. It will also record progress of the video that has been watched in increments of 25. So it will track 25%, 50% and 75% on top of the initial 3.

## Origin
This is not my original work, I have just modified it a bit from another source to work in the case I need. Such as adding the title as an available attribute for Analytics sake.

Original Repo: https://github.com/lunametrics/youtube-google-analytics

## Usage
I have automated this the best I can so you can just import _gtm-import.json_ and just update the UA code. You can also update the category if you would like to customize how it will show up in Analytics.

To update your UA code after you have imported the json file go to **Tags** > **YouTube Video Interaction** and update the _Web Property ID_ to yours. This can be found in your Analytics Dashboard in the properties section of UA project you wish to track the data too.

# Manual Way
Make sure you are in your GTM container, then follow the steps :)

1. Custom HTML
	a. Go to **Tags** and add new
	b. Choose Custom HTML
	c. Copy and paste the script from _youtube-tracking-script.js_ into `<script>` tags inside the box.

 ```
 <script>
	// Contents from youtube-tracking-script.js here
 </script>
 ```
 ![Custom HTML](http://d.pr/i/3nSQ)