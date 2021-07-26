# Privacy aware Youtube embed

This is a simple web Component to embed a Youtube Video in more privacy-aware
way.

Using this component only a thumbnail is displayed first. Only after clicking on
the Play Button the original Youtube iframe is loaded using the
youtube-nocookie.com URL.

## How to use

1. include the javascript located at `public/build.js` in your website
2. Use the component like a regular HTML element

Example:

```html
<privacy-yt-embed videoid="G6jhKEqtLxM" width="300" heigth="200"></privacy-yt-embed>
```

Per default the component, still has to load the thumbnail image from Youtube. T
avoid this you can specify a custom image as thumbnail, that will be used
instead, using the `thumbnail` attribute.

## Exposed Attributes

TBD

## Examples

An example on how to use it with the static Site Generator `hugo` can be found
at `examples/hugo`
