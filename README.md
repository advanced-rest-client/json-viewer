[![Build Status](https://travis-ci.org/advanced-rest-client/json-viewer.svg?branch=master)](https://travis-ci.org/advanced-rest-client/json-viewer)  

# json-viewer

`<json-viewer>` A JSON payload viewer for the JSON response.

This element uses a web worker to process the JSON data.
To simplify our lives and app build process the worker script is embeded in the
imported template body. It will extract worker data from it and create the
worker. Otherwise build process would need to incude a worker script file
into set path which is not very programmer friendly.

### Example
```
<json-viewer json='{"json": "test"}'></json-viewer>
```

## Custom search
If the platform doesn't support native text search, this element implements
`ArcBehaviors.TextSearchBehavior` and exposes the `query` attribute.
Set any text to the `query` attribute and it will automatically highlight
occurance of the text.
See demo for example.

## Big numbers in JavaScript
This element marks all numbers that are above `Number.MAX_SAFE_INTEGER` value
and locates the numeric value in source json if passed json was a string or
when `raw` attribute was set. In this case it will display a warning and
explanation about use of big numbers in JavaScript.
See js-max-number-error element documentation for more information.

### Styling
`<json-viewer>` provides the following custom properties and mixins for styling:

Custom property | Description | Default
----------------|-------------|----------
`--json-viewer` | Mixin applied to the element | `{}`
`--json-viewer-null-value-color` | Color of the null value. | `#708`
`--json-viewer-boolean-value-color` | Color of the boolean value | `#708`
`--json-viewer-punctuation-color` | Punctuation color. | `black`
`--json-viewer-string-value-color` | Color of the string value. | `#48A`
`--json-viewer-property-name-color` | Color of the JSON property. | `rgb(206, 123, 0)`
`--json-viewer-array-key-color` | Color of the array counter. | `rgb(119, 119, 119)`
`--json-viewer-link-color` | Color of link inserted into the viewer. | `#1976d2`



### Events
| Name | Description | Params |
| --- | --- | --- |
| action-link-change | Event called when the user click on the anchor in display area. | url **String** - The URL handled by this event. |
# js-max-number-error


