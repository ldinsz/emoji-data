This project provides easy-to-parse data about emoji, along with a spritesheet-style 
images for use on the web.

You can see a catalog of the emoji data here: http://unicodey.com/emoji-data/table.htm

Images are extracted from their sources and this library attempts to track the latest
available versions. If you're looking for older versions of Apple of Android images
(such as the Hairy Heart) then you'll need to look at previous revisions.

* Apple Emoji: Copyright &copy; Apple Inc. - OS X 10.11.1
* Android Emoji: Copyright &copy; [The Android Open Source Project](https://s3-eu-west-1.amazonaws.com/tw-font/android/NOTICE) - Lollipop
* Twitter Emoji Copyright &copy; Twitter, Inc. - The original release
* Emoji One Emoji: Copyright &copy; [Ranks.com Inc.](http://www.emojione.com/developers) - master as of 2015-03-05

## Libraries which use this data

* https://github.com/iamcal/js-emoji - JavaScript emoji library
* https://github.com/iamcal/php-emoji - PHP emoji library
* https://github.com/mroth/emoji-data-js - NodeJS emoji library
* https://github.com/mroth/emoji_data.rb - Ruby emoji library
* https://github.com/mroth/exmoji - Elixir/Erlang emoji library
* https://github.com/needim/wdt-emoji-bundle - a Slack-style JavaScript emoji picker
* https://github.com/mroth/emojistatic - emoji image CDN

## Using the data

The file you want is `emoji.json`. It contains an array of entries for emoji that 
look like this:

	[
		{
			"name": "WHITE UP POINTING INDEX",
			"unified": "261D",
			"variations": [
				"261D-FE0F"
			],
			"docomo": null,
			"au": "E4F6",
			"softbank": "E00F",
			"google": "FEB98",
			"image": "261d.png",
			"sheet_x": 1,
			"sheet_y": 2,
			"short_name": "point_up",
			"short_names": [
				"point_up"
			],
			"text": null,
			"texts": null,
			"category": "People",
			"sort_order": 116,
			"has_img_apple": true,
			"has_img_google": true,
			"has_img_twitter": true,
			"has_img_emojione": false,
			"skin_variations": {
				"261D-1F3FB": {
					"unified": "261D-1F3FB",
					"image": "261d-1f3fb.png",
					"sheet_x": 1,
					"sheet_y": 3,
					"has_img_apple": true,
					"has_img_google": false,
					"has_img_twitter": false,
					"has_img_emojione": false
				},
				...
			}
		},
		...
	]

An explanation of the various fields is in order:

* `name` - The offical Unicode name, in SHOUTY UPPERCASE.
* `unified` - The Unicode codepoint, as 4-5 hex digits. Where an emoji
   needs 2 or more codepoints, they are specified like `1F1EA-1F1F8`.
* `variations` - An array of commonly used codepoint variations.
* `docomo`, `au`, `softbank`, `google` - The Unicode codepoints used
   by various mobile vendors.
* `image` - The name of the image file.
* `sheet_x` & `sheet_y` - The position of the image in the spritesheets.
* `short_name` - The commonly-agreed upon short name for the image, as
   supported in campfire, github etc via the :colon-syntax:
* `short_names` - An array of all the known short names.
* `text` - An ASCII version of the emoji (e.g. `:)`), or null where
   none exists.
* `texts` - An array of ASCII emoji that should convert into this emoji.
   Each ASCII emoji will only appear against a single emoji entry.
* `has_img_*` - A flag for whether the given image set has an image (named by the `image` prop) available.
* `skin_variations` - For skin-varying emoji, a list of alternative glyphs.


## Version history

* 2015-05-28 : v2.0.0 - First tagged version, tracking new iOS 8 skin-tone emoji
* 2015-09-16 : v2.1.0 - Updated to OS X 10.11 beta, added new flags and spock emoji
* 2015-10-22 : v2.2.0 - Updated to OS X 10.11.1 final, with lots of new emoji
* 2015-11-04 : v2.2.1 - Fixed :scorpion: name and removed the duplicate family emoji
* 2015-11-05 : v2.2.2 - Fixed :lightning: names and added :man-woman-boy: back as an alias
* 2015-12-11 : v2.3.0 - Updated Google images to Android 6.0.1, Twitter images to include skin tones
* 2016-02-09 : v2.4.0 - Updated emojione images to the Q1 2016 release (v2.1.0)
* 2016-04-20 : v2.4.1 - Fixed the duplicate :satellite: short names
* 2016-05-12 : v2.4.2 - Changed :) to :slightly_smiling_face:, support for capitalized open_mouth emoticons, started processing the emoji 2.0 data files, added skin tones for U+1F575 (sluth/spy), fixed the duplicate :umbrella: short names, added U+23CF (eject symbol)
* 2016-06-01 : v2.4.3 - Fixed shortnames for snowman (U+2603 & U+26C4), added missing -FE0F variants for OS X/iOS, changed how we package for NPM
