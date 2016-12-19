# Surf_aggregator

Code (and HTML) to aggregate surfing resources (webcams, tide tables, etc.). The first version contains a simple webpage with an embedded link to a surfcam. Normally, without a paid subscription to this particular streaming service, a 15 second advertisement would play before every 30 seconds of live camera stream. 

This behavior is avoided by embedding the link (which effectively bypasses the advertisments). Further, the HTML contains a short Java-script, which reloads the page every 30 seconds. This results in unlimited (free) live streaming with a brief reload twice a minute. 