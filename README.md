# Surf_aggregator

HTML and JavaScript to aggregate surfing resources (webcams, tide tables, etc.). Currently a simple webpage with (1) embedded links to surfcams, and (2) a table with tide and sunrise/set times. 

Normally, without a paid subscription to certain streaming services, a 15 second advertisement might play before every 30 seconds of live camera stream. This behavior may be avoided by embedding the camera URL into an iframe (effectively delinking from advertisment cycle). Further, this HTML file contains a short JavaScript function, which is used to reload an iframe every 30 seconds. This results in unlimited (free) live streaming with a brief reload twice a minute. 

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
