# SVG to PNG

A small, dependency-free browser tool for converting SVG files or SVG source code into PNG images.

Everything runs locally in the browser. No files are uploaded.

## Why

This tool exists because a simple SVG conversion should not require:

* Third-party websites filled with ads
* Desktop applications that need a separate security review
* Node.js, Python, or other packages with possible supply-chain risks
* PowerPoint or similar software that may render SVGs incorrectly when the SVG has no defined `viewBox`

It is just a standalone `index.html` file with no external dependencies.

## Features

* Load an SVG file or paste SVG source code
* Export to a custom PNG width and height
* Preserve, crop, or stretch the aspect ratio
* Detect the actual SVG content bounds
* Generate a missing `viewBox`
* Add configurable padding around the content
* Override responsive SVG styles such as `width: 100%` and `max-width: 100%`
* Optional white background
* Local preview and PNG download

## Useful for SVGs without a `viewBox`

Some SVGs use percentage-based dimensions such as:

```xml
<svg width="100%" height="100%">
```

Without a `viewBox`, the SVG may be clipped on a small canvas or fail to scale naturally on a large canvas.

This tool can measure the rendered content, generate an appropriate `viewBox`, and then scale the complete image into the requested PNG size.

One example is an SVG copied from the rendered Mermaid output in the Mermaid Live Editor page source.

## Usage

1. Open `index.html` in a modern browser.
2. Select an SVG file or paste SVG source code.
3. Adjust the output size and rendering options.
4. Click **Render preview**.
5. Click **Save PNG**.

## Notes

SVGs that depend on inaccessible external images, fonts, stylesheets, or other resources may not render correctly.

Filters, shadows, markers, and unusually large strokes may extend beyond the detected geometry. Increase **Bounds padding** when needed.

## License

Use, modify, and distribute as needed.
