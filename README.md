# gloader

A macroquad/miniquad tweaked loader written in es6 and supporting multiple canvas on the same page.
While using macroquad framewroks, I saw that it was hard to display multiple projects on the same page so I decided to tweak the official gl.js to support that functionality.

# Usage

Basic gl.js (from miniquad README.md)

```html
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>TITLE</title>
    <style>
      html,
      body,
      canvas {
        margin: 0px;
        padding: 0px;
        width: 100%;
        height: 100%;
        overflow: hidden;
        position: absolute;
        background: black;
        z-index: 0;
      }
    </style>
  </head>

  <body>
    <canvas id="glcanvas" tabindex="1"></canvas>
    <!-- Minified and statically hosted version of https://github.com/not-fl3/miniquad/blob/master/native/sapp-wasm/js/gl.js -->
    <script src="https://not-fl3.github.io/miniquad-samples/gl.js"></script>
    <script>
      load("quad.wasm");
    </script>
    <!-- Your compiled wasm file -->
  </body>
</html>
```

Become this with tweaked gloader.js

```html
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>TITLE</title>
    <style>
      html,
      body,
      canvas {
        margin: 0px;
        padding: 0px;
        width: 100%;
        height: 100%;
        overflow: hidden;
        position: absolute;
        background: black;
        z-index: 0;
      }
    </style>
  </head>

  <body>
    <canvas id="glcanvas" tabindex="1"></canvas>
    <script src="https://raw.githubusercontent.com/Adi-df/gloader/master/dist/gl.min.js"></script>
    <script>
      const {load} = GLoader.init(document.querySelector("#glcanvas")):
      load("quad.wasm"); // Your compiled wasm file
    </script>
  </body>
</html>
```
