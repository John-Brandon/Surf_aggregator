# Surf_aggregator

Code (and HTML) to aggregate surfing resources (webcams, tide tables, etc.). The first version contains a simple webpage with an embedded link to a surfcam. Normally, without a paid subscription to this particular streaming service, a 15 second advertisement would play before every 30 seconds of live camera stream. 

This behavior is avoided by embedding the link (which effectively bypasses the advertisments). Further, the HTML contains a short Java-script, which reloads the page every 30 seconds. This results in unlimited (free) live streaming with a brief reload twice a minute. 

'''html
<script> 
		function autoRefresh(){
			window.location = window.location.href;
		}
 
		setInterval('autoRefresh()', 30000); // this will reload page every 30 seconds
</script>

<!-- Ocean Beach cam -->
<iframe width="853" height="480" src="http://e.cdn-surfline.com/syndication/embed/v1/player.html?id=4127" frameborder="0" scrolling="no" allowfullscreen></iframe><div style="margin: 10px 0px;"></div>
'''