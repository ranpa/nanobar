Slightly modified version that has been built in order to work with ionic1/angularjs (the original 'bar' class name causes conflicts with the framework default stylesheet)

Updated `var css` to use `.progressbar` instead of `.bar`

Original repo: https://github.com/jacoborus/nanobar/

---

## Usage

### Load

Link `nanobar.js` from your html file

```html
<script src="path/to/nanobar.min.js"></script>
```

or require it:

```js
var Nanobar = require('path/to/nanobar');
```

### Generate progressbar

```js
var nanobar = new Nanobar( options );
```

**options**

- `id` `<String>`: (optional) id for **nanobar** div
- `classname` `<String>`: (optional) class for **nanobar** div
- `target` `<DOM Element>`: (optional) Where to put the progress bar, **nanobar** will be fixed to top of document if no `target` is passed


### Move bar

Resize the bar with `nanobar.go(percentage)`

**arguments**

- `percentage` `<Number>` : percentage width of nanobar


## Example

Create bar

```js
var options = {
	classname: 'my-class',
  id: 'my-id',
	target: document.getElementById('myDivId')
};

var nanobar = new Nanobar( options );

//move bar
nanobar.go( 30 ); // size bar 30%
nanobar.go( 76 ); // size bar 76%

// size bar 100% and and finish
nanobar.go(100);
```

### Customize bars

Nanobar injects a style tag in your HTML head. Bar divs has class `.bar`, and its containers `.nanobar`, so you can overwrite its values.

Default css:

```css
.nanobar {
  width: 100%;
  height: 4px;
  z-index: 9999;
  top: 0;
}
.progressbar {
  width: 0;
  height: 100%;
  transition: height .3s;
  background: #000;
}
```

---

© 2016 [jacoborus](https://github.com/jacoborus) - Released under [MIT License](https://raw.github.com/jacoborus/nanobar/master/LICENSE)
