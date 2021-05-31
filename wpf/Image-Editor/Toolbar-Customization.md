---
layout: post
title: Toolbar customization in syncfusion SfImageEditor WPF.
description: This section describes how to customize the toolbar and toolbar item selected event in SfImageEditor control for WPF platform.
platform: wpf
control: SfImageEditor
 documentation: ug
---

# Toolbar Customization

## Customization

### Visibility

Toolbar can be made visible or hidden using the `IsToolbarVisiblity` property in the [`ToolbarSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_ToolbarSettings).

{% tabs %} 

{% highlight xaml %} 

  <editor:SfImageEditor.ToolbarSettings>
        <editor:ToolbarSettings IsToolbarVisiblity="True" />
  </editor:SfImageEditor.ToolbarSettings>

{% endhighlight %}

{% highlight C# %} 

editor.ToolbarSettings.IsToolbarVisibility = true;

{% endhighlight %}

{% endtabs %} 

### Add a item

You can add additional items to the toolbar and can perform your own operation. To add an additional item, specify the toolbar item, and add it in the ToolbarItems collection as demonstrated in following code snippet. You can specify your own template using the `IconTemplate` property in `ToolbarItem`.

{% tabs %} 

{% highlight xaml %} 

  <Grid.Resources>
            <DataTemplate x:Key="template">
                <TextBlock Text="New Item"></TextBlock>
            </DataTemplate>
  </Grid.Resources>

{% endhighlight %}

{% highlight C# %} 

editor.ToolbarSettings.ToolbarItems.Add(new ToolbarItem() { IconTemplate = grid.Resources["template"] as DataTemplate });

{% endhighlight %}

{% endtabs %} 

### Customization

You can change the [`Background`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html#Syncfusion_UI_Xaml_ImageEditor_ToolbarSettings_Background) and [`BorderColor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html#Syncfusion_UI_Xaml_ImageEditor_ToolbarSettings_BorderColor) of the toolbar. Also, you can change the height of the main toolbar using the [`HeaderToolbarHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html#Syncfusion_UI_Xaml_ImageEditor_ToolbarSettings_HeaderToolbarHeight) property, and the height of the sub toolbar can be changed using the [`SubItemToolbarHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html#Syncfusion_UI_Xaml_ImageEditor_ToolbarSettings_SubItemToolbarHeight) property, and the footer toolbar height can be changed using the [`FooterToolbarHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html#Syncfusion_UI_Xaml_ImageEditor_ToolbarSettings_FooterToolbarHeight).

This can be done as in the following code snippet.

{% tabs %} 

{% highlight xaml %} 

    <editor:SfImageEditor.ToolbarSettings>
                <editor:ToolbarSettings IsToolbarVisibility="True" HeaderToolbarHeight="36" 
                                        FooterToolbarHeight="36"  Background="#DEDEDE" BorderColor="Black"
                                        />
    </editor:SfImageEditor.ToolbarSettings>

{% endhighlight %}

{% highlight C# %} 

 editor.ToolbarSettings.Background= (SolidColorBrush)new BrushConverter().ConvertFromString("#DEDEDE");
            editor.ToolbarSettings.BorderColor = new SolidColorBrush(Colors.Black);
            editor.ToolbarSettings.HeaderToolbarHeight = 36;
            editor.ToolbarSettings.FooterToolbarHeight = 36;
            editor.ToolbarSettings.IsToolbarVisibility = true;
{% endhighlight %}

{% endtabs %} 

![Custom Item](Images/ToolbarCustomization.png) 

## Events

### ToolbarItemSelected

This event occurs when an item in the toolbar is selected. `ToolbarItemSelectedEventArgs` is the parameter. You can control the selected item operation by setting the Cancel property to true. You can also get the information about the ToolbarItem.

{% tabs %} 

{% highlight C# %} 

  private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
        {          
           e.Cancel = true;
        }

{% endhighlight %}

{% endtabs %} 

![Custom Item](Images/ToolbarCustomItem.png) 

## Image picker support

You can browse images in a local folder and load them in the Image Editor using the toolbar item browse icon. 

![Image picker support in WPF](Images/ImagePicker.png) 

## Commands

Invoke commands from the custom toolbar to customize toolbar items of the image editor. Must set the `CommandTarget` while using the Command.

<table>
<tr>
<td>
Command<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
BrowseImage<br/><br/></td><td>
Browses the local folder to pick and load the image  to an image editor.<br/><br/></td></tr>
<tr>
<td>
Save<br/><br/></td><td>
Saves the edited image.<br/><br/></td></tr>
<tr>
<td>
Undo<br/><br/></td><td>
Reverses the last performed action.<br/><br/></td></tr>
<tr>
<td>
Redo<br/><br/></td><td>
Restores the actions carried out by Undo.<br/><br/></td></tr>
<tr>
<td>
Reset<br/><br/></td><td>
Clears all the editing done on the image and brings to an initial state.<br/><br/></td></tr>
<tr>
<td>
ResetZoom<br/><br/></td><td>
Resets the zooming applied to the image.<br/><br/></td></tr>
<tr>
<td>
IncreaseZoom<br/><br/></td><td>
Zoom In the image by increasing the zoom level from its current state.<br/><br/></td></tr>
<tr>
<td>
DecreaseZoom<br/><br/></td><td>
Zoom Out the image by decreasing the zoom level from its current state.<br/><br/></td></tr>
<tr>
<td>
Select<br/><br/></td><td>
Used to select the items such as Shapes, Text, Custom view added on the image.<br/><br/></td></tr>
<tr>
<td>
Pan<br/><br/></td><td>
Used to Pan the image when it is in zoomed state.<br/><br/></td></tr>
</table>

This can be done as in the below code snippet.

{% tabs %} 

{% highlight xaml %} 

    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="200"/>
        </Grid.ColumnDefinitions>
        <editor:SfImageEditor Grid.Column="0" x:Name="imageEditor" ImageSource="Assets\RoadView.jpeg">
            <editor:SfImageEditor.ToolbarSettings>
                <editor:ToolbarSettings IsToolbarVisiblity="False"></editor:ToolbarSettings>
            </editor:SfImageEditor.ToolbarSettings>
        </editor:SfImageEditor>
		
          <Button  Grid.Column="1" HorizontalAlignment="Center" VerticalAlignment="Center" Background="White"
                    Width="Auto" CommandTarget="{Binding ElementName=imageEditor}"
                    Content="Save" Command="{x:Static editor:ImageEditorCommands.Save}"></Button>
    </Grid>
{% endhighlight %}

{% endtabs %}

![Custom Item](Images/ToolbarCustomization.png) 
