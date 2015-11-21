# Leaflet.Legend

This is a simple legend plugin for Leaflet.  It can be used to add a small popup legend to a Leaflet map


### What is this?

This plugin allows you to add a simple popup legend to a Leaflet map.  It extends the Leaflet ```Control``` class: creating and positioning the necessary container elements. The actual legend content is defined separately as a legend element in the html and appended to the legend container (see Usage).  

### Demo

An example can be found here: [OpenTrails](http://michaelskaug.com/projects/OpenTrails/)

## Usage

### Dependencies

- Leaflet 0.7.7

optional:
- font-awesome 4.4.0
- jquery 1.11.3

### Install
Install with npm:
```
npm install leaflet-legend
```
or fork the [github project](https://github.com/mikeskaug/Leaflet.Legend).

### Example

After including ```leaflet-legend.js``` and ```leaflet-legend.css``` in your project, you can add a legend to your map with the following:

```js
var Legend =  new L.Control.Legend({
        position: 'topleft',
        collapsed: true,
        controlButton: {
            title: "Legend"
        });
map.addControl( Legend );

$(".legend-container").append( $("#legend") );
$(".legend-toggle").append( "<i class='legend-toggle-icon fa fa-info fa-2x' style='color: #000'></i>" );
```

The options listed above are the defaults.  The command ```map.addControl( Legend );``` adds the legend container to the map, but we still need to add the legend content.  The legend content should be specified separately in the html document with ```id="legend" ```.  For example (from the demo):

```
<div id="legend">
   <svg width="120" height="80">
      <line x1="10" y1="20" x2="40" y2="20" class="path" />
      <text x="40" y="20" transform="translate(8,4)">Trail</text>
      <line x1="10" y1="40" x2="40" y2="40" class="cycleway" />
      <text x="40" y="40"transform="translate(8,4)">Bike Path</text>
      <line x1="10" y1="60" x2="40" y2="60" class="track" />
      <text x="40" y="60" transform="translate(8,4)">Dirt Road</text>
   </svg>
</div>
```

We then use JQuery to append the legend div to our legend container:

```js
$(".legend-container").append( $("#legend") );
```

To add an icon to the toggle button, we can either specify an icon image in leaflet-legend.css or append a font-awesome icon:

```
$(".legend-toggle").append( "<i class='legend-toggle-icon fa fa-info fa-2x' style='color: #000'></i>" );
```

## License

[MIT License](http://opensource.org/licenses/MIT)


