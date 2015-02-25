#Leaflet-ConditionalLayer

A layer that does not show any more than a certain amount of markers visible in the viewport. To be used when encountering performance probleme due to an important quantity of markers in the map.

Check out the [Demo](http://eclipse1979.github.io/Leaflet.ConditionalLayer/example/leaflet-conditionalLayer2.html). Note that on this page, there are more than 40 000 circles.

## Using Leaflet-ConditionalLayer :

To use Leaflet-ConditionalLayer you have to create the control. **The slider's id (in the options) must be the same as the variable name used by the slider.** For instance in the following code, options should have `id: "newSlider"`. The function fn should only take the value of the input as a parameter and will be called when the input value is changed.

    L.conditionalMarkers(<ILayer[]> Layers, <Leaflet.COnitionalLayer options> options).addTo(map);
    
Layers must be an array of [ILayers](http://leafletjs.com/reference.html#ilayer).
The preference order of an ILayer shown depends its id in Layers. The layer will choose the first ILayers in the viewport in the array, thus the lower an ILayer's id, the more it will to be shown.

## Simple usage example :

    var markerArray = [
    	L.circle(pos, radius, options),
    	L.marker(pos, options),
    	…
    ];
    var conditionalLayer = L.conditionalMarkers(markerArray, {maxMarkers: 40}).addTo(map);

## Methods :

Methods are the same as those of [FeatureGroup](http://leafletjs.com/reference.html#featuregroup).

## Options :
* `maxMarkers:` maximal number of markers

