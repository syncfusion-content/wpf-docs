---
layout: post
title: Toolbar customization in syncfusion SfImageEditor WPF.
description: Toolbar customization.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Toolbar Customization

## Customization

### Visibility

Toolbar can be made visible or hidden using the `IsToolbarVisibility` property in the [`ToolbarSettings`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfImageEditor.WPF~Syncfusion.UI.Xaml.ImageEditor.SfImageEditor~ToolbarSettings.html).

{% tabs %} 

{% highlight xaml %} 

  <editor:SfImageEditor.ToolbarSettings>
        <editor:ToolbarSettings IsToolbarVisibility="True" />
  </editor:SfImageEditor.ToolbarSettings>

{% endhighlight %}

{% highlight C# %} 

editor.ToolbarSettings.IsToolbarVisibility = true;

{% endhighlight %}

{% endtabs %} 

### Add item

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

You can change the [`Background`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfImageEditor.WPF~Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings~Background.html) and [`BorderColor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfImageEditor.WPF~Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings~BorderColor.html) of the toolbar. Also, you can change the height of the main toolbar using the [`HeaderToolbarHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfImageEditor.WPF~Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings~HeaderToolbarHeight.html) property and the height of the sub toolbar can be changed using the [`SubItemToolbarHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfImageEditor.WPF~Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings~SubItemToolbarHeight.html) property and the footer toolbar height can be changed using the [`FooterToolbarHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfImageEditor.WPF~Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings~FooterToolbarHeight.html).

This can be done as in the below code snippet.

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

We can Browse images in a local folder and load them in the Image Editor using toolbar item browse icon. 

![Image picker support in WPF](Images/ImagePicker.png) 
