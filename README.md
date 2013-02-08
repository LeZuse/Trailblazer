A location tracking service for Android, using [Firebase](http://www.firebase.com)
==================================================================================

Use this library in your android application to track the device's location.

The service will report the location and the timestamp that the location was updated to firebase.

You can start and stop the service with an intent, and the parameters are controlled via extras packaged with that intent.

Using [Firebase](http://www.firebase.com), you can get a realtime feed of location updates as they are broadcast.

For an example app using this service, and a simple google maps page displaying the information, see [here](https://github.com/firebase/FindLizzy)

Settings
--------

Constants are provided on the LocationService class for use as keys in the extras that you pass to the service.

The following options are supported:

* FIREBASE_REF - *REQUIRED* A string that points to a location in your firebase. Must end with .json. Get more info at [www.firebase.com](http://www.firebase.com)
* FIREBASE_APPEND - a boolean, defaults to false. If true, the service will append location data into your firebase, rather than replacing it.
* LOCATION_POLL_INTERVAL - a long that determines how frequently the service checks for a new location
* LOCATION\_ACCURACY - Criteria.ACCURACY\_{COURSE, FINE}. See the android Criteria documentation for details. Default is course.
* LOCATION\_POWER - Criteria.POWER\_{LOW, MEDIUM, HIGH}. See the android Criteria documentation for details. Default is medium.

Notification options:

You can configure Trailblazer to put an icon in the user's notification bar, as well as display some text.

* NOTIFICATION_ICON - an int corresponding to the drawable resource to use as the icon. This should look like R.drawable.<resource_name>
* NOTIFICATION_ACTIVITY - a string. This should be the canonical name of the activity class to launch when the user selects the notification. Typically the name of your main activity.
* NOTIFICATION_STARTUP - a string. The text to be displayed on the notification bar when the service starts.
* NOTIFICATION_TEXT - a string. The text to be displayed next to the icon in the notification dropdown menu.