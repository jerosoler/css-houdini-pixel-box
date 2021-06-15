[![GitHub license](https://img.shields.io/github/license/jerosoler/css-houdini-pixel-box)](https://github.com/jerosoler/css-houdini-pixel-box/blob/main/LICENSE)

# PixelBox

CSS Houdini library.

[PLAY DEMO](https://jerosoler.github.io/css-houdini-pixel-box/)

![Demo buttons](https://github.com/jerosoler/css-houdini-pixel-box/raw/main/docs/buttons.png)

![Demo combine](https://github.com/jerosoler/css-houdini-pixel-box/raw/main/docs/combine.png)

## CDN

```html
<script src="https://cdn.jsdelivr.net/gh/jerosoler/css-houdini-pixel-box/pixelbox.js"></script>
```

## NPM

```bash
npm install css-houdini-pixel-box
```

## How to use

Download `pixelbox.js` file.

### Polyfill

View support in [caniuse](https://caniuse.com/mdn-api_css_paintworklet)

```html
<script src="https://unpkg.com/css-paint-polyfill"></script>
```

### Javascript:

```javascript
if (
  "paintWorklet" in CSS &&
  "registerProperty" in CSS &&
  "CSSUnitValue" in window
) {
  CSS.registerProperty({
    name: "--pixelbox-border",
    syntax: "<length>",
    initialValue: "2px",
    inherits: false,
  });

  CSS.registerProperty({
    name: "--pixelbox-border-radius",
    syntax: "<length>",
    initialValue: "0px",
    inherits: false,
  });

  CSS.registerProperty({
    name: "--pixelbox-border-color",
    syntax: "<color>",
    initialValue: "#000000",
    inherits: false,
  });

  CSS.registerProperty({
    name: "--pixelbox-background-color",
    syntax: "<color>",
    initialValue: "#ffffff",
    inherits: false,
  });

  CSS.registerProperty({
    name: "--pixelbox-background-shadow-border",
    syntax: "<length>",
    initialValue: "0px",
    inherits: false,
  });

  CSS.registerProperty({
    name: "--pixelbox-background-shadow-color",
    syntax: "<color>",
    initialValue: "#adafbc",
    inherits: false,
  });

  /*CSS.registerProperty({
        name: '--pixelbox-background-shadow-position',
        syntax: '<string>',
        initialValue: 'bottom-right',
        inherits: false
    });
    */
} else {
  console.log("Not Supported");
}
CSS.paintWorklet.addModule("pixelbox.js");
```

### CSS

```css
div {
  display: inline-block;
  width: 200px;
  height: 200px;
  text-align: center;
  line-height: 200px;
  color: white;
  background-image: paint(pixelbox);
  --pixelbox-border: 10px;
  --pixelbox-border-radius: 5px;
  --pixelbox-border-color: #a0a0a0;
  --pixelbox-background-color: #000000;
  --pixelbox-background-shadow-border: 20px;
  --pixelbox-background-shadow-color: #494949;
  --pixelbox-background-shadow-position: bottom-right;
}
```
