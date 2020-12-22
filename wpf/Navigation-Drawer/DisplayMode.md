---
layout: post
title: DisplayMode | NavigationDrawer | WPF | Syncfusion
description: This section describes how to control layout shown with mode of the DisplayMode like default, compact or expanded in SfNavigationDrawer.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# DisplayMode with SfNavigationDrawer control 

The NavigationDrawer control provides top-level navigation for your app. It adapts to a variety of screen sizes and supports left navigation styles. There are three modes to change the layout.

### Compact

A drawer always shows as a narrow bar based on  property which can be opened to full width. When expanded the drawer appears as an overlay above the content.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfNavigationDrawer x:Name="navigationDrawer" DisplayMode="Compact">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }            
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}


### Expanded

A drawer stays open alongside of the content to the width of  property. When toggled the drawer switches to the narrow bar and the toggled back stays open alongside of the content.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer" DisplayMode="Expanded">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"
                    Fill="Black"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"
                    Fill="Black"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"
                    Fill="Black"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Expanded;
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }            
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}


### AutoChangeDisplayMode

When enabling the AutoChangeDisplayMode, the drawer will auto change the display modes depending on the size of the window.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfNavigationDrawer x:Name="navigationDrawer" DisplayMode="Expanded" AutoChangeDisplayMode="True" ExpandedModeThresholdWidth="600">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"
                    Fill="Black"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"
                    Fill="Black"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"
                    Fill="Black"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Expanded;
            navigationDrawer.AutoChangeDisplayMode = true;
            navigationDrawer.ExpandedModeThresholdWidth = 600;
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }            
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}
