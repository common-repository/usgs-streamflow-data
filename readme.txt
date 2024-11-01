=== Plugin Name ===
Contributors: manifestcreative
Donate link: http://philipdowner.com/
Tags: usgs, river conditions, streamflow, fishing, rafting, kayaking
Requires at least: 2.9
Tested up to: 3.3
Stable tag: trunk

This plugin fetches streamflow and river data from the USGS.

== Description ==

This is a WordPress plugin that fetches streamflow and river data from the USGS. It's intended use is for river guides and fishing outfitters to report conditions. It may also be useful for rafting companies and others who offer services related to rivers and streams.

* [Documentation on USGS API](http://waterservices.usgs.gov/rest/IV-Service.html)
* [Data Source](http://waterservices.usgs.gov/nwis/iv?format=json,1.1&stateCd=mt&parameterCd=00060,00065,00010&siteType=ST)
* [How to Locate USGS sites](http://wdr.water.usgs.gov/nwisgmap/index.html)

== Installation ==

1. Upload `plugin-name.php` to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress
1. Begin by specifying the rivers you'd like to display. Identified as an array within the function. `<?php $rivers = usgs_fetch_sites(array('jefferson','madison','bighole','beaverhead','ruby'));` ?>
1. Choose which data parameters to include (stream discharge, temperature, etc), or leave blank to include all. `<?php $data_params = usgs_fetch_dataParameters();` ?>
1. Place a call to fetch the JSON from USGS `<?php $riverData = usgs_fetch_riverData($rivers,$data_params); ?>`
1. Display the river data as an unordered list `<?php usgs_display_RiverData($riverData,$showMap=false); ?>`
1. Show a static Google map identifying the locations `<?php usgs_display_map($riverData,'riverDataMap','riverMap',650,450,$maptype='terrain',$echo=true); ?>`

== Frequently Asked Questions ==

= Will I be able to use this plugin without modifying my theme? =

No. You'll need to have basic familiarity with PHP, HTML and CSS for this plugin to work as intended. Future releases will attempt to address this and make it more user friendly.

= Do you offer support =

Generally no. If you wish to request support you may do it [through my personal site](http://philipdowner.com/2012/01/usgs-streamflow-data/). Since this is my first publicly release plugin, if support requests become overwhelming, I'll likely disable support all together.

== Screenshots ==

1. River data is output as an unordered list. It's up to you to style it.
2. A static Google map can be included that identifies the precise location the USGS took the measurement.

== Changelog ==

= 1.0 =
* Public release