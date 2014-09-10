NOTE THAT:
=========

* This is my first ever Android app and it was developed with Eclipse with tight dependency on libraries. It's practically non-reusable on Android Studio therefore I did not share code on GitHub.
* This is prototype-oriented app, which was created to try out Android-MySQL server communication, so it is not fully-functional (most of buttons are not-resposive to clicks and so on...)
* I worked on the server-side of the project. UI-side was sketched and implemented by other colleague.

Functionalities based on screens:
=========

* Add a post (on plus sign click). Provides a handled 3 step post add mechanism.
* Posts (1-st deph). Displays a list of all added posts.
* Post information (2-nd deph). When clicked on post in list, provides a detail information about post.
* Specific action (i.e. "Profile" click in post information) (3-rd deph). Directs to fragment of specific action.

Technical features:
=========

* DB is designed on server-side, it is based on MySQL.
* App-server communication:
     * App->server. In app there is performed a HTTP POST action to specific URL on a server, each URL points to PHP script.
     * Server->DB->Server. For particular situations there are prepared PHP scripts on server side. They can require data to be passed on them, in order to commit actions. If they receive required data they commit a query on MySQL DB. Query result are handled via PHP and printed out as JSON Objects.
     * Server->App.  In app there is retrieved a HTTP response (string containing JSON Object) and it is converted to JSONObject.
* Adding a post is divided into 3 steps:
     * most of pickers were presented in DialogFragment;
     * combined a DatePicker, TimePicker and SeekBar to select leaving date and time;
     * used Spinners and DialogFragments to provide address.
* Created a 1-2 fragments layout for tablets and phones. It is a 3 clicks depth layout which is designed to work in desired way on screen rotations and back pressed events, rather than it would in standard conditions.
* Implemented Facebook login, which retrieves basic user information and list of user joined groups.
* Menu is displayed by side of visible fragments.
