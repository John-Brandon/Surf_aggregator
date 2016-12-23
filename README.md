# Surf_aggregator

HTML and JavaScript to aggregate surfing resources (webcams, tide tables, etc.). Currently a simple webpage with an embedded link to a surfcam(s). Normally, without a paid subscription to certain streaming services, a 15 second advertisement might play before every 30 seconds of live camera stream. 

This behavior may be avoided by embedding the camera URL into an iframe (which effectively bypasses the advertisments). Further, this HTML contains a short Java-script, which reloads an iframe every 30 seconds. This results in unlimited (free) live streaming with a brief reload twice a minute. 

```html
<head>
	<script type="text/javascript">
			function refreshiframe() {
				var oElem = document.getElementById("OBSF");
				oElem.src = oElem.src;
			}
	</script>
</head>

<body onload="setInterval(refreshiframe, 31000);">

	<!-- Ocean Beach cam -->
	<h1>Ocean Beach, SF</h1>
	<iframe  id="OBSF" name="MiddleOB" width="853" height="480" src="http://e.cdn-surfline.com/syndication/embed/v1/player.html?id=4127" frameborder="0" scrolling="no" allowfullscreen></iframe><div style="margin: 10px 0px;"></div>

	// additional cams, tides, etc.
</body>
```
