---
layout: post
title: Exporting
description: exporting
platform: wpf
control: SfChart
documentation: ug
---

# Exporting

You can export the SfChart as image that is useful for many applications. The image can be saved in different supported file formats. The following image formats are supported by the SfChart.

* .jpeg or .jpg
* .jpg-XR
* .gif
* .png
* .bmp
* .tiff



The Save method is used for exporting the chart as Image. The following are the overloading methods.

_Overloading Methods_

<table>
<tr>
<td>
Prototype</td><td>
Description</td></tr>
<tr>
<td>
Save()</td><td>
Export the chart image to the particular location using FileSaverPicker.</td></tr>
<tr>
<td>
Save(string filename, storage folder location)</td><td>
Export the chart image to the given folder location. When the folder location is null it then exports the image to the app installed location.</td></tr>
<tr>
<td>
Save(IRandomAccessStream stream, Guid bitmapencoderID)</td><td>
Export the chart image using the stream and its corresponding encoder.</td></tr>
</table>


The following code example illustrates the chart exporting feature.

[XAML]



&lt;syncfusion:SfChart x:Name="Chart"&gt;

            &lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:CategoryAxis  Header="Company Name"/&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis  Header="Gross Revenue (cr.)"/&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;



            &lt;syncfusion:LineSeries  Palette="Metro"   XBindingPath="CompanyName" YBindingPath="CompanyTurnOver" ItemsSource="{Binding CompanyDetails}"/&gt;



        &lt;/syncfusion:SfChart&gt;





[C#]



private void Button_Click(object sender, RoutedEventArgs e)

{

    chart.Save("SfChart.jpg",Libraries\Pictures);



}



