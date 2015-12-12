---
layout: post
title: Ribbon Customization | SfSpreadsheet | WPF | Syncfusion
description: ribbon customization
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Ribbon Customization

Ribbon Customization can be done in two ways,

__Using__ __Control__ __Template__:

You can customize the Ribbon items by overriding the template of [SfSpreadsheetRibbon](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6348.html). 

__Using__ __Event__:

You can create a custom Ribbon tab with user defined meu options in SfSpreadsheet. To achieve this customization, invoke the SfSpreadsheetRibbon Loaded Event and create a custom tab with menu options. Add this custom tab to SfSpreadsheet Ribbon.

{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}

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

