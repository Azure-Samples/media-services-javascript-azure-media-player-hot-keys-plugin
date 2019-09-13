---
page_type: sample
languages:
- javascript
- html
products:
- azure
description: "This project is out of date as this plugin has been integrated directly into the release of Azure Media Player as of version 1.6.0.  This repository is kept active for reference purposes."
urlFragment: media-services-javascript-azure-media-player-hot-keys-plugin
---

# Media Services: Hot Keys Plugin for Azure Media Player

Hot keys plugin for Azure Media Player

*This project is out of date as this plugin has been integrated directly into the release of Azure Media Player as of version 1.6.0.  This repository is kept active for reference purposes.* 

##Information
This project is originally forked from [Video.js Hotkeys](https://github.com/ctd1500/videojs-hotkeys) by Chris Dougherty, a plugin for video.js and modified for use with Azure Media Player 

## Introduction

A plugin enables keyboard hotkeys when the player has focus.

- Space bar toggles play/pause.
- Right and Left Arrow keys seek the video forwards and back.
- Up and Down Arrow keys increase and decrease the volume.
- M key toggles mute/unmute.
- F key toggles fullscreen off and on. (Does not work in Internet Explorer, it seems to be a limitation where scripts cannot request fullscreen without a mouse click)
- Double-clicking with the mouse toggles fullscreen off and on.
- Number keys from 0-9 skip to a percentage of the video. 0 is 0% and 9 is 90%.

Note: clicking any of the control buttons such as Play/Pause, Fullscreen, or Mute, can remove focus on the player
which appears to "break" the hotkeys.  This is for accessibility reasons so that people who do not use or know about
the hotkeys can still properly use the `Tab` key to highlight the control buttons and press `space` to toggle them.

**To restore focus, just click on the video, or an empty part of the control bar at the bottom of the video player.**

## Getting Started
Include the plugin *after* the AMP script in the `<head>` of your html page:

```html
<script src="hotkeys.js"></script>
```

See example.html for how to enable the plugin and add [Options](#options)

## Options

- `volumeStep` (decimal): The percentage to increase/decrease the volume level when using the Up and Down Arrow keys (default: `0.1`)
- `seekStep` (integer): The number of seconds to seek forward and backwards when using the Right and Left Arrow keys (default: `5`)
- `enableMute` (boolean): Enables the volume mute to be toggle by pressing the **M** key (default: `true`)
- `enableVolumeScroll` (boolean): Enables increasing/decreasing the volume by scrolling the mouse wheel (default: `true`)
- `enableFullscreen` (boolean): Enables toggling the video fullscreen by pressing the **F** key (default: `true`)
- `enableNumbers` (boolean): Enables seeking the video by pressing the number keys (default `true`)
- `enableJogStyle` (boolean): Enables seeking the video in a broadcast-style jog by pressing the Up and Down Arrow keys.
`seekStep` will also need to be changed to get a proper broadcast-style jog.
This feature and the changes for seekStep are explained a bit more in [PR #12](https://github.com/ctd1500/videojs-hotkeys/pull/12) (default `false`)
(**Note:** This isn't a feature for everyone, and enabling JogStyle will disable the volume hotkeys)
