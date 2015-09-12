# character-shuffling

[![npm-image](https://img.shields.io/npm/v/character-shuffling.svg?style=flat-square)](https://www.npmjs.com/package/character-shuffling)

## Install

**NPM**

```sh
npm install character-shuffling --save
```

## Basic Usage
```js
var CS = require('character-shuffling');

var element = document.getElementById('sample-text');
var text = new CS(element, /* options */);

// shuffle its current character data
text.shuffle();

// shuffle to a new string specified by the `text` option
text.shuffle({text : 'Some new text to animate...'});
```

## Default Options

You can extend this options during instantiation (second param) or when calling the `shuffle` method.

```js
{
	/* The characters to use when selecting characters randomly. 
	 * [String]
	 */
	chars : "abcdefghijklmnopqrstuvwxyz" +
			"ABCDEFGHIJKLMNOPQRSTUVWXYZ" +
			"0123456789" +
			",.?/\\(^)![]{}*&^%$#'\"",
			
	/* How many times should the letters be changed. 
	 * [Number]
	 */
	times : 10,
	
	/* String to shuffle to 
	 * [String]
	 */
	text : this.element.textContent,
	
	/* Function to be call once the shuffling is complete. 
	 * [Function]
	 */
	callback : null
}
```

## License
MIT © [Noel Delgado][0]

[0]: http://pixelia.me/