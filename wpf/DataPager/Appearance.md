---
layout: post
title: Appearance in WPF DataPager control | Syncfusion
description: Learn here all about Appearance support in Syncfusion WPF DataPager (SfDataPager) control, its elements and more details.
platform: wpf
control: SfDataPager Control
documentation: ug
---

# Appearance in WPF DataPager (SfDataPager)

SfDataPager supports appearance styles by using the following properties.

* AutoEllipsisMode
* AccentBrush
* DisplayMode
* Orientation

## AutoEllipsisMode


The AutoEllipsis button is displayed when the page count is greater than numeric button count. The SfDataPager control allows you to define the AutoEllipsis button by using the AutoEllipsisMode property which is the Enum type. 

* AutoEllipsisMode – This Property is used to set the AutoEllipsisMode. By default, it is set to None.
* AutoEllipsisText– This property is used to change the AutoEllipsisButton Text.



The following table explains the different AutoEllipsisModes.

<table>
<tr>
<th>
 Enum Values</th><th>
Description</th></tr>
<tr>
<td>
 After</td><td>
Displays the ellipsis button after the numeric buttons.{{'![Features_images6](Features_images/Features_img6.png)'|markdownify}}

</td></tr>
<tr>
<td>
 Before</td><td>
Displays the ellipsis button before the numeric buttons.{{'![Features_images7](Features_images/Features_img7.png)'|markdownify}}

</td></tr>
<tr>
<td>
 Both</td><td>
Displays the ellipsis button before and after the numeric buttons.{{'![Features_images8](Features_images/Features_img8.png)'|markdownify}}

</td></tr>
<tr>
<td>
None</td><td>
It does not display the AutoEllipsisButton.</td></tr>
</table>


N> By Default AutoEllipsisMode is set to None.

The following code example explains how to change the AutoEllipsisText.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*" />
        <RowDefinition Height="Auto" />
    </Grid.RowDefinitions>
    <sfgrid:SfDataGrid AutoGenerateColumns="True" 
                       Grid.Row="0"
                       ItemsSource="{Binding ElementName=sfDataPager,Path=PagedSource}"/>
    <datapager:SfDataPager x:Name="sfDataPager"
                           Grid.Row="1"
                           AutoEllipsisMode="After"
                           NumericButtonCount="10"
                           AutoEllipsisText="...etc" 
                           PageSize="16" 
                           Source="{Binding OrdersDetails}" />
</Grid>
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output for AutoEllipsisText changed as …etc.

![Features_images9](Features_images/Features_img9.png)

## AccentBrush

AccentBrush properties are used to decorate the SfDataPager control with a solid color. There are two AccentBrush properties in the SfDataPager control:

* AccentBackground – Property that is applied to the background color for NavigationButtons and current selected numeric page button. By default, it set to DarkGray.
* AccentForeground – Property that is applied to the foreground color for the current selected numeric page button. By default, it set to White.
* NumericButtonStyle – Property that is applied to the Style of Numeric Button. This is the Style type property. By default, it set to Null.


The following code example explains how to apply the AccentBackground and AccentForeground properties for the SfDataPager control.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:Viewmodel/>
</Window.DataContext>
<Grid>
    <sfgrid:SfDataGrid AutoGenerateColumns="True" 
                       ItemsSource="{Binding ElementName=sfDataPager,Path =PagedSource}"/>
    <datapager:SfDataPager x:Name="sfDataPager"
                           AccentBackground="#FF8CBF26"
                           AccentForeground="White" 
                           NumericButtonCount="10"      
                           PageSize="16"
                           Source="{Binding OrdersDetails}"/>
</Grid>
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output for AccentBackground and AccentForeGround applied to the SfDataPager.

![Features_images10](Features_images/Features_img10.png)


The following code example explains how to use NumericButtonStyle in SfDataPager.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:Viewmodel/>
</Window.DataContext>
<Window.Resources>
    <Style TargetType="datapager:NumericButton">
        <Setter Property="BorderBrush" Value="Blue"/>
        <Setter Property="BorderThickness" Value="2"/>
    </Style>
</Window.Resources>
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*"/>
        <RowDefinition Height="50"/>
    </Grid.RowDefinitions>
    <sfgrid:SfDataGrid AutoGenerateColumns="True" 
                       Grid.Row="0"
                       ItemsSource="{Binding ElementName=sfDataPager,Path=PagedSource}"/>
    <datapager:SfDataPager x:Name="sfDataPager"
                           PageCount="16"
                           Grid.Row="1"
                           AutoEllipsisMode="Both"
                           AccentBackground="DodgerBlue"  
                           NumericButtonCount="10" 
                           Source="{Binding OrdersDetails}"/>
</Grid>
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output of NumericButtonStyle.

![Features_images11](Features_images/Features_img11.png)


## Display Modes

The SfDataPager control allows you to choose the elements that are visible in the control. This can be achieved by using the DisplayMode property.The following table explains the PageDisplayMode enum values.


<table>
<tr>
<th>
Enum Values</th><th>
Description</th></tr>
<tr>
<td>
FirstLastPreviousNextNumeric</td><td>
Displays all the navigation buttons and numeric page buttons.{{'![Features_images12](Features_images/Features_img12.png)'|markdownify}}

</td></tr>
<tr>
<td>
FirstLastNumeric</td><td>
Displays the first page, last page navigation button and numeric page buttons.{{'![Features_images13](Features_images/Features_img13.png)'|markdownify}}

</td></tr>
<tr>
<td>
PreviousNextNumeric</td><td>
Displays the previous, next page navigation buttons and numeric page buttons.{{'![Features_images14](Features_images/Features_img14.png)'|markdownify}}

</td></tr>
<tr>
<td>
FirstLastPreviousNext</td><td>
Displays only the page navigation buttons. Numeric page buttons are not displayed.{{'![Features_images15](Features_images/Features_img15.png)'|markdownify}}

</td></tr>
<tr>
<td>
FirstLast</td><td>
Displays only the first and last page navigation buttons.{{'![Features_images16](Features_images/Features_img16.png)'|markdownify}}

</td></tr>
<tr>
<td>
PreviousNext</td><td>
Displays only the previous and next page navigation buttons.{{'![Features_images17](Features_images/Features_img17.png)'|markdownify}}

</td></tr>
<tr>
<td>
Numeric</td><td>
Displays only the numeric page buttons.{{'![Features_images18](Features_images/Features_img18.png)'|markdownify}}

</td></tr>
<tr>
<td>
First</td><td>
Displays only the first page navigation button.{{'![Features_images19](Features_images/Features_img19.png)'|markdownify}}

</td></tr>
<tr>
<td>
Last</td><td>
Displays only the last page navigation button.{{'![Features_images20](Features_images/Features_img20.png)'|markdownify}}

</td></tr>
<tr>
<td>
Previous</td><td>
Displays only the previous page navigation button.{{'![Features_images21](Features_images/Features_img21.png)'|markdownify}}

</td></tr>
<tr>
<td>
Next</td><td>
Displays only the next page navigation button.{{'![Features_images22](Features_images/Features_img22.png)'|markdownify}}

</td></tr>
<tr>
<td>
None</td><td>
It does not display anything</td></tr>
</table>


N> By Default, DisplayMode is set to FirstLastPreviousNextNumeric.

## Orientation

SfDataPager allows you to arrange the child elements either horizontally or vertically.  This can be achieved by using the Orientation Property. Orientation is an Enum type.  The following table describes the Orientation enum values.



<table>
<tr>
<th>
Enum Value</th><th>
Description</th></tr>
<tr>
<td>
Horizontal</td><td>
This is the default enum value for Orientation.  Arranges all the Navigation Buttons and Numeric Buttons Horizontally.{{'![Features_images23](Features_images/Features_img23.png)'|markdownify}}

</td></tr>
<tr>
<td>
Vertical</td><td>
Arranges all the Navigation Buttons and Numeric Buttons Vertically.{{'![Features_images24](Features_images/Features_img24.png)'|markdownify}}

</td></tr>
</table>
