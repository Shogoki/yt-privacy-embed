# Hugo Example

A simple example how to use this component in a [HUGO](https://gohugo.io)
Website.

## Important Files

`layouts/shortcodes/youtube.html`: This is overwriting the builtin youtube
shortcode using this component.

`static/js/privacy-yt-embed.js`: This is a copy of the latest `bundle.js` from
`/public/build`that need´s to be here for this to work.

## How to use

With these files in place inside of the content we can use the new youtube
shortcode like this:

```html
{{< youtube id=G6jhKEqtLxM  width=300 height=200 >}}
{{< youtube id=G6jhKEqtLxM thumbnail=https://link-to-alternate.image/image.png  width=300 height=200 >}}
```
