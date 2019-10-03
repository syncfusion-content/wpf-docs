---
layout: post
title: Toolbar customization in syncfusion SfImageEditor WPF.
description: Toolbar customization.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Toolbar customization

## Customization

### Visibility

Toolbar can be made visible or hidden using the `IsToolbarVisibility` property in the `ToolbarSettings`.

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

### Add Item

You can add additional item to the toolbar and can perform your own operation. To add additional item, specify the toolbar item and add it in the ToolbarItems collection as in below snippet. You can specify your own template using the `IconTemplate` property in the `ToolbarItem`.

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

## Events

### ToolbarItemSelected

Toolbar item selected event will be invoked when the item in the toolbar is  selected. `ToolbarItemSelectedEventArgs` will be the parameter. You can control the selected item operation by setting the Cancel property to true. Also you can get the information about the ToolbarItem.

{% tabs %} 

{% highlight C# %} 

  private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
        {          
           e.Cancel = true;
        }

{% endhighlight %}

{% endtabs %} 

![ImageEditor](Images/ToolbarCustomization.png) 