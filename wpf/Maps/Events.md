---
layout: post
title: Legend | SfMap | wpf | Syncfusion
description: events
platform: wpf
control: SfMap
documentation: ug
---

# Events in WPF Maps (SfMap)

• [`ZoomedIn`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.SfMap~ZoomedIn_EV.html) - Occurs whenever zooming the map.  
• [`ZoomedOut`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.SfMap~ZoomedOut_EV.html) - Occurs when zoomed out the map.
• [`Panning`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.SfMap~Panning_EV.html) - Occurs while panning the map.
• [`Panned`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.SfMap~Panned_EV.html) - Occurs after panned the map.
• [`MapToolTipOpening`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.SfMap~MapToolTipOpening_EV.html) - Occurs when any tooltip on the SfMap control is opened.

### Tooltip opening event

[`MapToolTipOpening`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.SfMap~MapToolTipOpening_EV.html) event occurs whenever you select a shape, bubble, or marker. You will get the `Data` and `TooltipType` properties as arguments from `TooltipOpeningEventArgs` handler, and you can cancel the event for a particular shape using the `Cancel` property.

{% tabs %}

{% highlight xaml %}

      <maps:SfMap MapToolTipOpening="Map_MapToolTipOpening" >
            <maps:SfMap.Layers>               
                <maps:ShapeFileLayer Uri="MapsZoom.ShapeFiles.usa_state.shp" ItemsSource="{Binding Data}" 
                                     ShapeIDPath="State" ShapeIDTableField="STATE_NAME" 
                                     EnableSelection="False" LabelPath="State">
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting   ShapeStrokeThickness="1" ></maps:ShapeSetting>
                    </maps:ShapeFileLayer.ShapeSettings>
                    <maps:ShapeFileLayer.ToolTipSettings>
                        <maps:ToolTipSetting ValuePath="Candidate" x:Name="shapeTooltipSettings" >
                        </maps:ToolTipSetting>
                    </maps:ShapeFileLayer.ToolTipSettings>
                </maps:ShapeFileLayer>
	       </maps:SfMap.Layers>
        </maps:SfMap>

{% endhighlight %}

{% highlight c# %}

         private void SfMaps_TooltipOpening(object sender, TooltipOpeningEventArgs e)
         {
            if ((e.Data is MapsZoom.ElectionData) && (e.Data as MapsZoom.ElectionData).State == "North Dakota")
            {
                e.Cancel = true;
            }
	}

{% endhighlight %}

{% endtabs %}