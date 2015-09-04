# Conic Sections SVG renderer

Demonstrates the principle of conic sections in 3D for educational purposes. Works fully in the browser using SVG rendering, which makes it backwards compatible with some pretty old browser.

Multiple of these elements can be placed on a webpage, showing different sections. Controls are configurable.

Drag the mouse over the conic sections visualization to change the camera position.

# Usage

Requires jquery (tested with 1.7.1), jquery ui sliders (tested with 1.8.17) and raphael js (tested with 2.0.1). Make sure they are loaded on the page. 

Include conics3d.js on the page.

Add two html elements, one for the conics visualization and another for the controls. 
Then initialize the conic section UI with javascript by creating a new ConicsUI instance:

```
$(function() { // document ready event
  var opts = {};
  conics = new ConicsUI(${'#controls'), $('#visualization'}, opts); 
});
```

The first parameter of ConicsUI should be a JQuery dom element reference to the controls, the second a reference to the element where the visualization will be displayed.

Options properties of ConicsUI are (third constructor parameter): 

 - `pitch`:		sets the initial camera pitch
 - `yaw`:    	sets the initial camera yaw
 - `planeY`: 	plane Y offset
 - `planeX`: 	plane X offset
 - `planeZ`: 	plane Z offset
 - `planeRot`: plane rotation in radians
 - `maxConeRadius`: the radius of the cone at the top and bottom
 - `disableCameraDragging`: set to true to disable camera dragging
 - `updateRealtime` set to true to see every changes redrawn in realtime
 - `drawOptions`: see Conics.draw() @ options
 - `onPlaneUpdate`: event handler for plane updates (called on draw events)
 - `onDraw`: event handler to extend drawing

Sliders that control the camera position can be created using the following ConicsUI methods:

 -	`conics.createXSlider(sliderEl, valueEl, opts)`
 -	`conics.createYSlider(sliderEl, valueEl, opts)`
 -	`conics.createZSlider(sliderEl, valueEl, opts)`
 -	`conics.createRotSlider(sliderEl, valueEl, opts)`

Parameters:

 - `sliderEl` : jquery dom element = the slider will be placed in this element.
 - `valueEl`  : jquery dom element = the slider's value will be displayed in this element.

```
 - opts : object =  {
  invert   : boolean = the direction of the slider
  vertical : boolean = slider alignment
}
```

# Examples

 * Example features in this [repository](https://rawgit.com/lowdewijk/JsConicSections/master/example/index.html). 
 * Example featured on [intmath](http://www.intmath.com/plane-analytic-geometry/conic-sections-summary-interactive.php).

# License 

MIT licensed. Enjoy.
