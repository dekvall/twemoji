# Twitter Emoji (Twemoji) - RuneLite compliant

This branch holds emojis that can be used in the [RuneLite client](https://github.com/runelite/runelite).

The images are in png format, 13x13, with a hard-edged transparency because the client cannot handle semitransparent pixels.

## Usage
 1. Find your desired emoji by its corresponding [codepoint](https://emojipedia.org/emoji/)
 2. Download the file, rename it, and place it in:

 	`runelite/runelite-client/src/main/resources/net/runelite/client/plugins/emojis`  
 3. Add an appropriate shortcode to:
 
 	`runelite-client/src/main/java/net/runelite/client/plugins/emojis/Emoji.java`
 4. Compile the client and use your fresh emoji in game

## Creation
```
mogrify -path <TARGET_FOLDER> -resize 13x13 -filter Box -colors 256 -channel A -threshold 50% <SOURCE_FOLDER>/*.png
optipng -o7 -strip all <TARGET_FOLDER>/*.png
```

Enjoy!
