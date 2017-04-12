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

1. Creating DataLayers
	* Go to **Variables**
	* Under _User-Defined Variables_ choose **New**
	* Choose variable type **Data Layer Variable**
	* **Data Layer Variable Name**
		* attributes.videoUrl
		* attributes.videoTitle
		* attributes.videoAction
	* Repeat **b - d** until you have 3 with the above variables.
 ![Custom HTML](http://d.pr/i/i6A5+)
 
2. Triggers
	* Go to **Triggers**
	* Create a new Trigger with **type** _Custom Event_
	* **Event name** == `youTubeTrack`
	* Triggers on _Some Custom Events_
	* Dropdown 1, 2, 3
		* Video Interaction
		* Matches RegEx (ignore case)
		* Play|Pause|Watch to End|25%|50%|75%
 ![Custom HTML](http://d.pr/i/FqiK+)

 ### Tags
 Go to **Tags** and do the following 2 steps

3. Send Data to Analytics   
	* Create a New Tag
	* Choose **Universal Analytics**
	* Enter your Analytics **ID** from your Analytics _Property_
	* _Track Type_: **Event**
	* _Category_: **YouTube Video Tracking** (you can make this whatever you want)
	* _Action_: `{{Video Interaction}}`
		* This will report, PLay, Pause, 25% Watched, etc
		* This can be adjusted in the JS file if you need and know what you are doing.
	* _Label_: `{{Video Title}}`
		* This could also be sorted by the URL using `{{Video URL}}`
	* Add a trigger and choose **YouTube Video Interaction**
		* This can be named whatever you called it, its the trigger we created in step 2
 ![Custom HTML](http://d.pr/i/4lYh+)

4. Custom HTML
	* Create a New Tag
	* Choose Custom HTML
	* Copy and paste the script from _youtube-tracking-script.js_ into `<script>` tags inside the box.
	* Add trigger and choose **All Pages**
 ```
 <script>
	// Contents from youtube-tracking-script.js here
 </script>
 ```
 ![Custom HTML](http://d.pr/i/3nSQ+)
 
