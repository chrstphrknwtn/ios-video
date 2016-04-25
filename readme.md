# ios-video

> Play inline videos in iOS browsers. 

The purpose of this library is to autoplay inline video on iOS devices without doing anything except opt-in.

There are no options, and there is no requirement to add extra elements to your markup.

**What it does**  
A replacement canvas element that inherits all the video element CSS is injected as a
sibling of the video element, the video element is hidden, and media query CSS changes to the video element are applied to the canvas on window resize / device orientation change.

Supports video element attributes `autoplay` and `loop`. Audio is not supported.

## Install
````shell
npm install ios-video
````

## Usage
````javascript
var video = iOSVideo('#myVideo');

// Video will play if the video has the 'autoplay' attribute, otherwise:
video.play();

// You can also:
video.pause()
video.seek(2) // 2 seconds
video.restart() // Go back to the start
````

The above code will replace the video with a canvas on all browsers and devices, it is up to you do decide when it is appropriate to use, for example:

````javascript
var iOS = /iPad|iPhone|iPod/.test(navigator.platform);
var video;
if (iOS) {
  video = iOSVideo('#my-video');
}
````

MIT Licence