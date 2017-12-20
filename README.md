# polymer2
In this code lab, installed the following elements
`iron-image`<link rel="import" href="../../bower_components/iron-image/iron-image.html">
`paper-button`<link rel="import" href="../../bower_components/paper-button/paper-button.html">
`polymer`<link rel="import" href="../../bower_components/polymer/polymer-element.html">
`app-layout`<link rel="import" href="../../bower_components/app-layout/app-layout.html">
`paper-styles`<link rel="import" href="../../bower_components/paper-styles/color.html">
`iron-ajax`<link rel="import" href="../../bower_components/iron-ajax/iron-ajax.html">
The `paper-styles` provides an easy implementation of material design
`bower install paper-styles --save`
`iron-ajax`
> `auto`: load automatically when its URL or parameters change
> `url`: where `<iron-ajax>` will load from.
> `handle-as`: treat the loaded file as json
> `on-response`: the function to be called when it's loaded the file as a event listener
`--paper-light-blue-500` is the custom CSS property imported with `paper-styles` can use it as a value of CSS property
`on-click="_selectAnswer"` to access the event listener
```
{
 "sources": [
   "data/*",
   "data/svg/*"
 ]
}
```
The above code in `polymer.json` file to specify the resources will be included together in the build
