---
layout: post
title: Theming
description: Theming
platform: wpf
control: PivotGrid
documentation: ug
---

## Theming

Theming is the process of applying particular settings to the visual elements of a product. This feature provides the following theming options:

*Office 2010 Blue

*Office 2010 Black

*Office 2010 Silver

*Transparent

*Office 2007 Blue

*Office 2007 Black

*Office 2007 Silver

*Blend

*Metro

*Office 2003

*Default

#### Use Case Scenarios

This feature enables users to develop a single application and apply different looks as necessary. 

#### Property

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }} </td><td>
{{ '**Description**' | markdownify }} </td><td>
{{ '**Type**' | markdownify }} </td><td>
{{ '**Data Type**' | markdownify }} </td></tr>
<tr>
<td>
VisualStyle </td><td>
Gets or Sets the VisualStyle of BI control </td><td>
Dependency Property</td><td>
PivotGridVisualStyle</td></tr>
</table>


#### Sample Link

A sample demo available in the following link,

{InstalledDrive} :\Users\sabapathyk\AppData\Local\Syncfusion\EssentialStudio\10.4.0.53\BI\WPF\PivotAnalysis.WPF\Samples\Appearance\Skin Customization Demo

### Adding Theming to an Application 

The following code sample demonstrates adding theming to the PivotGrid control.

{% highlight xml %} 

[XAML]

      <syncfusion:PivotGridControl  x:Name="pivotGrid" VisualStyle="Transparent"/>


{% endhighlight %} 

{% highlight C# %}  

[C#]

       this.pivotGrid.VisualStyle = PivotGridVisualStyle.Transparent;

{% endhighlight %} 



