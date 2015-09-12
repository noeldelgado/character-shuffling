# character-shuffling

[![npm-image](https://img.shields.io/npm/v/character-shuffling.svg?style=flat-square)](https://www.npmjs.com/package/character-shuffling)

Vanilla (and slightly modified) version of [Martin Angelov's][1] - [jquery.shuffleLetters.js][2]

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

## Example Using Options
```js
var CS = require('character-shuffling');
var el = document.getElementById('sample-element');
var text = new CS(el, {
	chars : ".?/\\(^)![]{}*&^%$#'\"",
	text : 'Hello World',
	callback : function() {
	   console.log('Hello World shuffling animation completed.');
	}
});
text.shuffle();

...
// later on
text.shuffle({
	chars : '0123456789',
	text : 'I like numbers...',
	times : 20,
	callback : function() {
	   console.log(this.get('text'));
	   => 'I like numbers...'
	}
});
```

## License
MIT © [Noel Delgado][0]

[0]: http://pixelia.me/
[1]: http://martinangelov.com/
[2]: http://tutorialzine.com/2011/09/shuffle-letters-effect-jquery/