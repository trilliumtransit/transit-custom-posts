# Transit Custom Posts Plugin

This Wordpress plugin is designed to make creating and maintaining transit websites as simple as possible. It supplies Route, Timetable, Alert, and Board Meeting custom post types, pulls in route and timetable information programmatically from GTFS data, and features and API with many convenience functions for common transit site problems.

[Read more about the API](https://trilliumtransit.github.io/transit-custom-posts/) and how to use the plugin.

## Installation

If you download a compatible theme such as [Transit Base Template](https://github.com/trilliumtransit/transit-base-template), it will direct you to automatically install this plugin. Otherwise, if you would like to use it on its own to develop your own theme or integrate it with an existing theme:

* [Download ZIP](https://github.com/trilliumtransit/transit-custom-posts/archive/master.zip)
* Install from WP Admin area in Plugins > Add New > Upload Plugin

Afterward, you can configure the plugin from the WP Admin screen in the Transit Custom Posts submenus. More documentation is available on [the Github site for this project](https://trilliumtransit.github.io/transit-custom-posts/).

## Hooks and Filters 

Transit Custom Posts has several hooks and filters which you can implement within a theme for customization when updating routes and timtables with new GTFS data. These include: 

- Route Title - add_filter('tcp_filter_route_title', function( $html ){}, 10, 1);
- Route Name - add_filter('tcp_route_name', function( $format ){}, 10, 1);
- Route Circle - add_filter('get_route_circle', function( $post_id ){}, 10, 1);
- Route URL - add_filter('tcp_filter_route_url', function( $post_id ){}, 10, 1);

- Timetable days of the week - add_filter('tcp_timetable_filter_days_of_week', function( $days_of_week ){}, 10, 1);
- Routes text file path - add_filter('tcp_filter_route_txt_path', function( $routes_txt ){}, 10, 1);
- Timetable text file path - add_filter('tcp_filter_timetables_txt_path', function( $timetables_txt ){}, 10, 1);
- GTFS download feed directory - add_filter('tcp_gtfs_download_feed_dir', function( $feed_dir ){}, 10, 1);
- GTFS update route pages - add_action( 'tcp_gtfs_update_routes’, function( $routes_txt ){}, 10, 1);
- GTFS update timetable pages - add_action( 'tcp_gtfs_update_timetables’, function( $timetables_txt ){}, 10, 1);

- After route update - add_action( 'after_tcp_route_update’, function( $post_to_update_id ){}, 10, 1);
- After timetable update - add_action( 'after_tcp_timetable_update’, function( $post_to_update_id ){}, 10, 1);


## How to Contribute

Issues/bugs, pull-requests, feedback, and documentation are always appreciated. Please see the issue log for currently open and unassigned tasks.

The Wordpress ecosystem could use more themes compatible with this plugin! Feel free to hack away at our [starter template](https://github.com/trilliumtransit/transit-base-template) as a working example and help us make public transit more accessible and easy-to-use with beautiful websites and quality software. It's all GPLv2, so take what you want to make your own awesome implementation.

## Credits

Created by Trillium Solutions, inc for the Northwest Oregon Transit Alliance

Author: NomeQ 2017