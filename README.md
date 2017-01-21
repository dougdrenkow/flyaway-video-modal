# flyaway-video-modal

VideoJS player plays HLS stream in responsive-sized modal (70% display width) with consistent high-def proportions. When modal is closed, it "flies away": scales to zero, as modal background clears.

**Notes**

* Because modal varies in width and height, even "on the fly" with window resized in real time, it cannot be centered in viewport, although it has position:fixed. Give top a modest value, to minimize minimum viewport height required to show entire modal.
* Setting width of modal to 70%, of viewport, allows for that modest-sized space atop plus a header (fixed in height, for minimum font-size), while also allowing the video control bar to also show within viewport on monitors as "squat" as my laptop (1366x768).
* #video-wrapper maintains high-def video proportions (a variation on the old "fluid width video" trick, https://css-tricks.com/NetMag/FluidWidthVideo/Article-FluidWidthVideo.php).
* Applying CSS transitions to #video-wrapper instead of to video itself allows them to work in Edge as well as other browsers.
* Using transform:scale(0,0) helps performance, vs. transition: all ...
