**The completely new vewsion, Filterous-2 for both JavaScript for browser and Node.js is available at https://github.com/girliemac/filterous-2!**

This repo is no longer maintained.

![Filterous](http://girliemac.com/assets/images/articles/2014/03/filtrous.jpg?raw=true)

Filterous
=========

Image manipulation library in JavaScript that applies filters to photos à la Instagram on browser.
This script take pixel data from a photo that you want to give filter effects, and maniplute its pixels using the `canvas` element.
The finished photo can be displayed as `canvas`, or as downloadable image formats such as `jpeg`, `png`, or `webp` for Chrome.

This works on modern mobile browsers as well.

> Created by [Tomomi Imura](https://github.com/girliemac)



## Simple Demo

[Filterous Demo](http://girliemac.github.io/Filterous/demo)

## Real-life Example App

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


## Using Presets (instead of defining filters manually)

- Import `filterousEffects.js`.
- Include the `effects` folder (contains the overlay image).

```html
<script src="filterousEffects.js"></script>
```
```javascript
ApplyEffects.nostalgia(imageObject, 'jpeg');
```

Take a look at the `filterousEffects.js` to see all available presets.

## License

[MIT License](http://opensource.org/licenses/MIT)


## Thank you

Thank you [html5rocks.com](http://www.html5rocks.com/en/tutorials/canvas/imagefilters/) for the tutorial on the pixel manpulating tutorials :-)
