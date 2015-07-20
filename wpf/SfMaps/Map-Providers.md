---
layout: post
title: Map-Providers
description: map providers
platform: wpf
control: SfMap
documentation: ug
---

# Map Providers

SfMap control supports map providers such as OpenStreetMap that can be added to any layers in maps.

## Open Street Map

OpenStreetMap is a map of the entire world. The OpenStreetMap allows you to view, edit and use geographical data in a collaborative way from any place on the Earth.

Enable OSM

You can enable this feature by setting the layerType property value as "OSM".

[XAML]



        &lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ImageryLayer LayerType="OSM" /&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;

{ ![](Map-Providers_images/Map-Providers_img1.png) | markdownify }
{:.image }


## Bing Map

Bing Map is a key feature in accessing the external geospatial imagery services for deep-zoom satellite view.

Enable Bing Map 

You can enable this feature by defining the LayerType as “bing”. 

Bing Map Key

The bing Map key is provided as input to this key property. The Bing Map key can be obtained from 

[http://www.microsoft.com/maps/create-a-bing-maps-key.aspx](http://www.microsoft.com/maps/create-a-bing-maps-key.aspx).

Aerial View

[XAML]



        &lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ImageryLayer LayerType="Bing" BingMapKey="Bing Map Key" BingMapStyle="Aerial" /&gt;     

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;





The following screenshot illustrates the Aerial View

{ ![](Map-Providers_images/Map-Providers_img2.png) | markdownify }
{:.image }


Road View

[XAML]



        &lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ImageryLayer LayerType="Bing" BingMapKey="Bing Map Key" BingMapStyle="Road" /&gt;     

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;





The following screenshot illustrates the Road view.

{ ![](Map-Providers_images/Map-Providers_img3.png) | markdownify }
{:.image }


AerialWithLabelView

[XAML]



        &lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ImageryLayer LayerType="Bing" BingMapKey="Bing Map Key" BingMapStyle="AerialWithLabels" /&gt;     

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;





The following screenshot illustrates the AerialWithLabel view.

{ ![](Map-Providers_images/Map-Providers_img4.png) | markdownify }
{:.image }


