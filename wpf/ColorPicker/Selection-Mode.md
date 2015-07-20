---
layout: post
title: Selection-Mode
description: selection mode
platform: wpf
control: ColorPicker
documentation: ug
---

# Selection Mode

ColorPicker and ColorEdit controls can be displayed in two different modes. They are HSV and RGB modes. The VisualizationStyle property is used to switch between these modes.

To set the ColorSelection Mode as "HSV" for ColorEdit control, use the below code.

<table>
<tr>
<td>
[XAML]&lt;!-- Adding ColorEdit --&gt;&lt;syncfusion:ColorEdit  Margin="20" VisualizationStyle="HSV" Name="colorEdit"/&gt;</td></tr>
<tr>
<td>
[C#]//Creating an instance of color editColorEdit colorEdit = new ColorEdit();//Setting selection mode as HSVcolorEdit.VisualizationStyle = ColorSelectionMode.HSV;    //Adding control to the windowthis.Content = colorEdit;</td></tr>
</table>




{ ![](Selection-Mode_images/Selection-Mode_img1.jpeg) | markdownify }
{:.image }




To set the ColorSelection Mode as "HSV" for ColorPicker control, use the below code.



[C#]



//Creating an instance of color picker

ColorPicker colorPicker = new ColorPicker();



//Setting selection mode as HSV

colorPicker.VisualizationStyle = ColorSelectionMode.HSV;    



//Adding control to the window

this.Content = colorPicker;





{ ![](Selection-Mode_images/Selection-Mode_img2.jpeg) | markdownify }
{:.image }




To set the ColorSelection Mode as "RGB" for ColorEdit control, use the below code.

[C#]



//Creating an instance of color edit

ColorEdit colorEdit = new ColorEdit();



//Setting selection mode as RGB

colorEdit.VisualizationStyle = ColorSelectionMode.RGB; 



//Adding control to the window

this.Content = colorEdit;





{ ![](Selection-Mode_images/Selection-Mode_img3.jpeg) | markdownify }
{:.image }




To set the ColorSelection Mode as "RGB" for ColorPicker control, use the below code.

[C#]



//Creating an instance of color picker

ColorPicker colorPicker = new ColorPicker();



//Setting selection mode as RGB

colorPicker.VisualizationStyle = ColorSelectionMode.RGB;



//Adding control to the window

this.Content = colorPicker;





{ ![](Selection-Mode_images/Selection-Mode_img4.jpeg) | markdownify }
{:.image }


