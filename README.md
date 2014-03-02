Filterous
=========


Image manipulation library in JavaScript that applies filters to photos à la Instagram on browser.
This script take pixel data from a photo that you want to give filter effects, and maniplute its pixels using the `canvas` element.
The finished photo can be displayed as `canvas`, or as downloadable image formats such as `jpeg`, `png`, or `webp` for Chrome.

This works on modern mobile browsers as well.

> Created by [Tomomi Imura](https://github.com/girliemac)



## Sample Demo

[Filterous Demo](http://girliemac.github.io/Filterous/demo)

## Real-life Example

[W3C CoreMob camera - Mobile Web App](http://coremob.github.io/camera/vanilla/index.html)


## Installation

Just include `filterous.js` in your HTML file.

```html
<script src="filterous.js"></script>
```

Filterous does not require any other depencies.

## Basic Usage

Create a new instance.

```javascript
var f = new Filterous(imageObject);
```

Leaving the second param results a finished photo as a canvas, otherwise in a specified images format.

```javascript
var f = new Filterous(imageObject, 'jpeg');
```

Apply a filter (or multiple filters) then render.

```javascript
f.filterImage('brightness', 50);
f.render();
```

### Examples of using other filters

```javascript
f.filterImage('grayscale');
f.filterImage('rgbAdjust', [1.4, 1.2, 1]);
f.filterImage('convolute', [ 0, 0, 0,
                             0, 1, 0,
                             0, 0, 0 ]
);
```
or add an image layer:

```javascript
var starryLayer = new Image();
starryLayer.src = 'effects/stars.png';

var f = new PhotoFilter(Filterous, 'jpeg');
f.applyLayer(starryLayer);
f.render();
```

Reset:

```javascript
f.reset();
```


## Using Presets (instead of adding manual filters)

Import `filterousEffects.js`

```html
<script src="filterousEffects.js"></script>
```
```javascript
ApplyEffects.nostalgia(imageObject, 'jpeg');
```

Take a look at the `filterousEffects.js` to see all available presets.

## License

[MIT License](http://opensource.org/licenses/MIT)
