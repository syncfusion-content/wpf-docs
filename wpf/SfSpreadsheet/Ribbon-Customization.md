---
layout: post
title: Ribbon Customization in SfSpreadsheet
description: How to customize the SfSpreadsheetRibbon
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Ribbon Customization

Ribbon Customization can be done in two ways,

## Using Control Template:

User can customize the ribbon items by overriding the template of [SfSpreadsheetRibbon](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheetRibbon.html).

## Using Event:

By invoking SfSpreadsheetRibbon Loaded Event, User can add/delete the ribbon menu items.

### Adding a Ribbon Item

To create a custom Ribbon tab with user defined menu options in SfSpreadsheet, 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

ribbon.Loaded += ribbon_Loaded;
RibbonBar CustomRibbonBar;
    
void ribbon_Loaded(object sender, RoutedEventArgs e)
{
    var sfribbon = GridUtil.GetVisualChild<Ribbon>(sender as FrameworkElement);

    if (sfribbon != null)
    {
      RibbonTab rb = new RibbonTab();
      rb.Caption = "OTHER";
      RibbonButton Button1 = new RibbonButton();
      Button1.Label = "PRINT";
      Button1.SmallIcon = new BitmapImage(new Uri("/../Icon/Icons_Print.png", UriKind.Relative));
      Button1.Click += Button1_Click;
      RibbonButton Button2 = new RibbonButton();
      Button2.Label = "PRINT PREVIEW";
      Button2.SmallIcon = new BitmapImage(new Uri("/../Icon/Icons_Print.png", UriKind.Relative));
      Button2.Click += Button2_Click;
      CustomRibbonBar = new RibbonBar();
      CustomRibbonBar.Header = "Printing Options";
      CustomRibbonBar.Items.Add(Button1);
      CustomRibbonBar.Items.Add(Button2);
      CustomRibbonBar.IsLauncherButtonVisible = false;
      rb.Items.Add(CustomRibbonBar);
      sfribbon.Items.Add(rb);
    }
}

{% endhighlight %}
{% endtabs %}

### Removing a Ribbon Item

To remove the ribbon menu items in the SfSpreadsheetRibbon,

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

ribbon.Loaded += ribbon_Loaded;
    
void ribbon_Loaded(object sender, RoutedEventArgs e)
{
    var sfribbon = GridUtil.GetVisualChild<Ribbon>(sender as FrameworkElement);

    if (sfribbon != null)
    {
      var item = sfribbon.Items[2];
      sfribbon.Items.Remove(item);
    }
}

{% endhighlight %}
{% endtabs %}


