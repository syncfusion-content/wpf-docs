---
layout: post
title: Layout Related Features | CheckListBox | wpf | Syncfusion
description: Layout related features in Syncfusion Essential Studio WPF CheckListBox control, its elements and more.
platform: wpf
control: CheckListBox
documentation: ug
---

# Layout Related Features

This section illustrates the Layout-related features of CheckListBox control. The following features are discussed:

## Alignment for CheckListBox

The check box in the CheckListBox Item can be aligned to the left or right side of the control using the CheckBoxAlignment property. This dependency property sets the alignment of the check box of the items. Following are the alignment options.

* Left: Check box in the CheckListBox Item is aligned to the left
* Right: Check box in the CheckListBox Item is aligned to the right

To set the CheckBoxAlignment to Right, use the following code.

{% tabs %}
{%highlight xaml%}

<!-- Adding CheckListBox with CheckBoxAlignment -->
<syncfusion:CheckListBox Name="checkListBox" CheckBoxAlignment="Right"> 
<!-- Adding CheckListBox items -->   
<syncfusion:CheckListBoxItem Content="Mexico"/> 
<syncfusion:CheckListBoxItem Content="Canada" />
<syncfusion:CheckListBoxItem Content="Bermuda" />
<syncfusion:CheckListBoxItem Content="Belize" /> 
<syncfusion:CheckListBoxItem Content="Panama" />
</syncfusion:CheckListBox></td></tr>
   
{%endhighlight%}

{% highlight c#%}

// Align the Check Box.
checkListBox.CheckBoxAlignment = CheckBoxAlignment.Right;

{%endhighlight%}
{% endtabs %}

![CheckBoxAlignment](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg)

CheckBoxAlignment = "Right"
{:.caption}

## Flow direction

The flow direction for the CheckListBox control is set through the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.flowdirection?view=netframework-4.7.2) property.

To set the FlowDirection to RightToLeft, use the below code:

{% tabs %}
{%highlight xaml%}

<!-- Adding CheckListBox with FlowDirection as right  -->
<syncfusion:CheckListBox Name="checkListBox" FlowDirection="RightToLeft"> 
<!-- Adding CheckListBox items --> 
<syncfusion:CheckListBoxItem Content="Mexico"/>  
<syncfusion:CheckListBoxItem Content="Canada" />  
<syncfusion:CheckListBoxItem Content="Bermuda" />  
<syncfusion:CheckListBoxItem Content="Belize" />  
<syncfusion:CheckListBoxItem Content="Panama" />
</syncfusion:CheckListBox>
   
{% endhighlight %}

{%highlight c# %}

// Set FlowDirection property as RightToLeft.
checkListBox.FlowDirection = FlowDirection.RightToLeft;

{%endhighlight%}
{% endtabs %}

![Flow direction](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg)

FlowDirection = "RightToLeft"
{:.caption}

## Set VisualStyle for CheckListBox

The appearance of the CheckListBox control is customized by applying a suitable style using the VisualStyle property.

Property table

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the CheckListBox control. The options provided are as follows.
<ul>
<li>BlendOffice2003</li>
<li>Office2007Blue</li>
<li>Office2007Black</li>
<li>Office2007Silver</li>
<li>ShinyBlue</li>
<li>ShinyRed</li>
<li>SyncOrange</li>
<li>VS2010</li>
<li>Metro</li>
<li>Transparent</li>
</ul>
</td></tr>
</table>

For setting Blend style, refer the below code snippet.

{% tabs %}
{%highlight xaml%}

<!-- Adding CheckListBox with Visual Style as Blend -->
<syncfusion:CheckListBox Name="checkListBox" syncfusion:SkinStorage.VisualStyle="Blend">   
<!-- Adding CheckListBox items -->    
<syncfusion:CheckListBoxItem Content="Mexico"/> 
<syncfusion:CheckListBoxItem Content="Canada" />  
<syncfusion:CheckListBoxItem Content="Bermuda" />  
<syncfusion:CheckListBoxItem Content="Belize" />  
<syncfusion:CheckListBoxItem Content="Panama" />
</syncfusion:CheckListBox>
 
{%endhighlight%}

{%highlight c#%}

// Setting the visual style as Blend.
SkinStorage.SetVisualStyle(checkListBox, "Blend"); 

{%endhighlight%}
{% endtabs %}

![Blend visual style](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg)

CheckListBox with "Blend" Visual Style

![Default visual style](Layout-Related-Features_images/Layout-Related-Features_img4.jpeg)

CheckListBox with "Default" Visual Style
{:.caption}

![Office2007Black visual style](Layout-Related-Features_images/Layout-Related-Features_img5.jpeg)

CheckListBox with "Office2007Black" Visual Style
{:.caption}

![Office2003 visual style](Layout-Related-Features_images/Layout-Related-Features_img6.jpeg)

CheckListBox with "Office2003" Visual Style
{:.caption}

![Metro visual style](Layout-Related-Features_images/Layout-Related-Features_img7.png)

CheckListBox with "Metro" Visual Style
{:.caption}

![Transparent visual style](Layout-Related-Features_images/Layout-Related-Features_img8.png)

CheckListBox with "Transparent" Visual Style
{:.caption}