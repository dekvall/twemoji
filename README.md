# RuneLite friendly Twemoji

This repo contains emojis that can be used in the [RuneLite client](https://github.com/runelite/runelite).

The images are in png format, 13x13, with a hard-edged transparency. The client cannot handle semitransparent pixels.

## Usage
 1. Find your desired emoji on [emojipedia](https://emojipedia.org/emoji/)
 2. Scroll down to where it says **Codepoints**, the codepoint will look something like: `U+1F642`.
 3. Use GitHub's [find function](https://github.com/dekvall/twemoji/find/runelite-emoji) to search for the emoji in this repository, ex `runelite-emoji/1f642.png`. 
 4. Download the file, rename it to something appropriate, and place it in:
 ```
 runelite/runelite-client/src/main/resources/net/runelite/client/plugins/emojis
 ``` 
 5. Add an appropriate shortcode to:
 ```
 runelite-client/src/main/java/net/runelite/client/plugins/emojis/Emoji.java
 ```
 6. Compile the client and use your new emoji in game

## Creation
```
mogrify -path <TARGET_FOLDER> -resize 13x13 -filter Box -colors 256 -channel A -threshold 50% <SOURCE_FOLDER>/*.png
optipng -o7 -strip all <TARGET_FOLDER>/*.png
```

Enjoy!
