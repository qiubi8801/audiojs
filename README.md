# audio.js

A cross-browser `<audio>` player. It uses `<audio>` where available and provides
a flash fallback for other browsers. It provides a consistent html player to
all browsers, which can be styled used standard css.

It plays mp3s. **No ogg**. Because, lets be honest, in the real world, no one
really exports ogg files. Sadly, that means Opera and Firefox get flash audio.
Hopefully they add mp3 support soon.

## Usage

Put `audio.min.js`, `player-graphics.gif` & `audiojs.swf` in the same folder.

Include `audio.js`:
    <script src="/audiojs/audio.min.js"></script>

Initialise `audio.js`:
    <script>
      audiojs.events.ready(function() {
        var as = audiojs.createAll();
      });
    </script>

HTML:
    <audio src="/mp3/juicy.mp3" preload="auto" />


## Bugs / Contributions

- Report a bug
- To contribute or send an idea, github message me or fork the project

## Build

If you're on a mac, run rake compile — You'll need the
[google closure compiler](http://code.google.com/closure/compiler/) installed,
but it will package `audio.js` into `audio.min.js`.

## Compiling Flash from the command line

If you want to mess around with the flash-side of things, you will need to be
able to compile the `.as` file into a `.swf`.

Using the Flex SDK (which is free), flash movies can be compiled
directly from the command line. It makes life that little bit less painful.

### Installing mxmlc

1. Download and unzip the current 'Milestone Release' 'Open Source Flex SDK' from:
   <http://opensource.adobe.com/wiki/display/flexsdk/Download+Flex+4>

2. Copy the `bin` folder to `/usr/local/bin/flex/bin/`

3. Add `/usr/local/bin/flex/bin/` to your `PATH`

### Compiling the SWF

Run the following command from within the `audiojs` folder.

    mxmlc audiojs.as