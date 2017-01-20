# Surf\_aggregator

HTML and JavaScript to aggregate surfing resources (webcams, tide tables, etc.). Currently a simple webpage with (1) embedded links to surfcams, and (2) a table with tide and sunrise/set times. 

## Motivation

I've been surfing for 20 yrs. Not as long as some of my friends, but long enough to have seen some changes. I speak of
web cams pointed at the waves, streaming for the world to see. I understand that the persuit of such an enterprise,
however ultimately selfish, is well within other peoples' legal right. Heck some might say these things are our divine duty to
pursue. All I know is I couldn't stop the march of progress if I wanted. This leads us here, and to something of a recourse. To an arms race
between a middle-aged father of two and Surfline.com.

Normally, without a paid subscription, a 15 second advertisement plays before every 30s of live camera stream. After
30s, the 15s advertisement (often the same expensive BMX beach sock one) repeats. This loop was easy to bypass
for a long time using an AdBlock browser extension. There was about 10s of downtime between 30s live streams (with the ads
removed) and the stream would automatically refresh after the pause. Good enough. Until that is, Surfline updated
something and unceremoniously outflanked the AdBlock maneuver. 

This forced my retreat. Clearly, an unacceptable situation. New plans were drawn up, only to fail in the field.
Then a chink in the armor was found. I can't say for sure if Surfline inserted some JavaScript to kill AdBlocking in the
name of profit. I
also don't know if, or how much, Surfline might be trying to profit from including a link directly below each video
player that can be used 
to embed individual cam
streams on other websites. Regardless, every push by the oppenent is an invitation to pull in sumo. I would
take Surfline's generosity and embed the link they provided in my own webpage.

Et Voila, embedding the camera URL into an iframe decouples the stream from the advertisment cycle. All that was left was to add
a short JavaScript function to refresh the camera(s) iframe every 30s.  This approach
results in unlimited (free) live streaming with only a momentary pause to reload twice a minute.  

```html
<head>
	<script type="text/javascript">
			function refreshiframe() {
				var oElem = document.getElementById("OBSF");
				oElem.src = oElem.src;
			}
	</script>
</head>

<body onload="setInterval(refreshiframe, 31000);">  <!-- Units = ms -->

	<!-- Ocean Beach cam -->
	<h1>Ocean Beach, SF</h1>
	<iframe  id="OBSF" name="MiddleOB" width="853" height="480" src="http://e.cdn-surfline.com/syndication/embed/v1/player.html?id=4127" frameborder="0" scrolling="no" allowfullscreen></iframe><div style="margin: 10px 0px;"></div>

	<!-- insert additional cams, tides, etc. below -->
</body>
```

The `Surf\_aggregator.html` file can be edited easily to include any combination of cameras for which links are
publically available. Opening the file in a browser will connect to the streams. For the world to see.

