# Tulip

Voice activated web navigation extension for the Chrome browser. 

The project is still under development and is not yet available on the Chrome Store.

- <a href="#Developing">Developing</a>
- <a href="#Future">Future Directions</a>
- <a href="#UserGuide">User Guide</a>

<a name="Developing"></a>
# Development Guide

The architecture was inspired heavily by the [firefox voice](https://github.com/mozilla/firefox-voice) project.
A detailed overview is available under the [docs]() directory. Each non-trivial file also has a comment section 
at the top with a brief overview of the purpose of the file.

The extension currently utilizes a few external dependencies:

- Speech recognition with [annyang](https://github.com/TalAter/annyang).

- Intent engine fuzzy search powered by [fuse](https://fusejs.io/).

To start up a development environment that runs the unloaded extension, clone the project and run:

* ``` npm install ``` 
* ``` npm run build ```

Then, load the project directory as an unpacked chrome extension by following the directions [here](https://developer.chrome.com/extensions/getstarted#manifest)

<a name="Future"></a>
# Improving Accessibility and Future Directions 

The following projects would increase accessibility of this tool:

- Sip and Puff Integration
- Wakeword detection i.e., "Hey Tulip"

The following improvements would decrease reliance on external third parties:

- Development of our own custom deep speech recognition server
- Development of our own voice activity detection algorithms

<a name="UserGuide"></a>
# User Guide

Currently, the extension can be triggered by clicking on the extension icon in the top right of the chrome toolbar
or by hitting "Command+Shift+O" on a Mac or "Ctrl+Shift+O" on Windows.

The following commands are supported.

- Open
    - Conducts a “I’m feeling lucky” google search on the phrases detected in the utterence and opens the
      top result.
    - Examples: "Open Spotify", "Open Youtube", "Open Netflix"
- Close Tab
    - Closes current tab. Useful if a mistake or unintended tab is opened.
- Back
    - Navigates to last visited page in the browser
- Click
    - Clicks an element based off a fuzzy search of the web page using [Fuse.js](https://fusejs.io/)
    - Example: "Click Sign-In", "Click the name of news article", "Click the title of a video"
- Scroll
    - Scrolls an element based off a fuzzy search of the web page [Fuse.js](https://fusejs.io/)
    - Example: "Scroll Page Down", "Scroll Page Up", "Scroll Playlist Section", "Scroll Liked Videos"
- Focus Input 
    - Focuses an input based off a fuzzy search of the web page using [Fuse.js](https://fusejs.io/)
    - Example: "Focus password field", "Focus search field"
- Dictate
    - Dictate into text fields and other input areas

- Play/Pause/Fast Forward Media
    - Supported services include Netflix, Youtube and Spotify.

Note that the interface currently handles *one command at a time*, therefore, each command will need to invoke the interface
again separately. Improvements to this coming shortly.
