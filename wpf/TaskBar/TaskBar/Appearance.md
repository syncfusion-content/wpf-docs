---
layout: post
title: Appearance | TaskBar | wpf | Syncfusion
description: appearance
platform: wpf
control: TaskBar
 documentation: ug
---

# Appearance

This section deals with the appearance of TaskBar control and contains the following topic:

## Setting Visual Styles

The appearance of the TaskBar control is customized by using the VisualStyle property. The various built-in visual styles are listed below.





<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the TaskBar control. The options provided are as follows. 
* Blend <br/>
* Office2003 <br/>
* Office2007 <br/>
* BlueOffice2007 <br/>
* BlackOffice2007Silver <br/>
* ShinyBlue <br/>
* ShinyRed <br/>
* SyncOrange <br/>
* VS2010 <br/>
* Metro <br/>
* Transparent</td></tr>
</table>




To set the visual style for the TaskBar, use the below code.


{%tabs%}

{% highlight xaml %}



<!-- Adding TaskBar -->

<syncfusion:TaskBar Name="taskBar" >



    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1">



        <!-- Adding content to TaskBarItem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 										VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">

This TaskBar that have a TaskBarItem.

            </TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>

</syncfusion:TaskBar>

{% endhighlight %}



{% highlight c# %}



// Setting the visual style as Office2007Blue

SkinStorage.SetVisualStyle(taskBar, "Office2007Blue");

{% endhighlight %}

{%endtabs%}

![](Appearance_images/Appearance_img1.png)


TaskBar with "Office2007Blue" Visual Style
{:.caption}



![](Appearance_images/Appearance_img2.png)


TaskBar with "Office2007Black" Visual Style
{:.caption}


![](Appearance_images/Appearance_img3.png)

TaskBar with "Office2007Silver" Visual Style
{:.caption}



![](Appearance_images/Appearance_img4.png)


TaskBar with "Office2010Blue" Visual Style
{:.caption}



![](Appearance_images/Appearance_img5.png)


TaskBar with "Office2010Black" Visual Style
{:.caption}



![](Appearance_images/Appearance_img6.png)



TaskBar with "Office2010Silver" Visual Style
{:.caption}



![](Appearance_images/Appearance_img7.png)



TaskBar with "Blend" Visual Style
{:.caption}



![](Appearance_images/Appearance_img8.png)


TaskBar with "VS2010" Visual Style
{:.caption}



![](Appearance_images/Appearance_img9.png)



TaskBar with "Metro" Visual Style
{:.caption}



![](Appearance_images/Appearance_img10.png)


TaskBar with "Transparent" Visual Style
{:.caption}




