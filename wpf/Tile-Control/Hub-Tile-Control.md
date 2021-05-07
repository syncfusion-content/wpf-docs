---
layout: post
title: Hub Tile in WPF Tile Control control | Syncfusion
description: Learn about Hub Tile support in Syncfusion WPF Tile Control control and more.
platform: WPF
control: SfHubTile
documentation: ug
---

# Hub Tile in WPF Tile Control

The Hub Tile control supports the tile feature similar to the live tile feature of Windows Desktop and Windows Phone. This section explains about the supporting features of Hub Tile control.

## Setting header content

Header can act as the name of the tile, that is placed at the bottom explaining its purpose. The content of the header can be an image, a text or a control, etc. The header can be set to the tile by using the [Header](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Primitives.HeaderedContentControl.html#Syncfusion_Windows_Primitives_HeaderedContentControl_Header) property.

{% tabs %}
{% highlight XAML %}
<Grid x:Name="grid">
<!--For setting header as text use this code. -->
<syncfusion:SfHubTile x:Name="hubtile" Header="Mail" Foreground="White"/>

<!--For setting header as an image use this code.-->
<syncfusion:SfHubTile x:Name="hubtile">
    <syncfusion:SfHubTile.Header>
        <Image Source="/Assets/syncfusion.png" Stretch="None"/>
    </syncfusion:SfHubTile.Header>
</syncfusion:SfHubTile> 

<!--For setting header as a control use this code.-->
<syncfusion:SfHubTile x:Name="hubtile">
   <syncfusion:SfHubTile.Header>
       <TextBlock Text="SYNCFUSION" Foreground="White" FontSize="13"/>
   </syncfusion:SfHubTile.Header>
</syncfusion:SfHubTile> 
</Grid>     
{% endhighlight %}
{% highlight C# %}

// For setting header as text use this code.
SfHubTile hubTile = new SfHubTile();
hubTile.Header = "Mail";
hubTile.Foreground = Brushes.White;
    
//For setting header as image use this code.
SfHubTile hubTile = new SfHubTile();
Image image = new Image(){Source = new BitmapImage(new Uri(@"/Assets/syncfusion.png",UriKind.RelativeOrAbsolute)),Stretch = Stretch.None };
hubTile.Header = image;
    
//For setting header as control use this code.
SfHubTile hubTile = new SfHubTile();
TextBlock textblock = new TextBlock(){Text = "SYNCFUSION", Foreground = Brushes.White, FontSize = 13} ; 
hubTile.Header = textblock;
grid.Children.Add(hubTile);

{% endhighlight %}
{% endtabs %}

![wpf tile header](Getting-Started_images/wpf-hubtile-header.png)

![wpf hubtile header as image](Getting-Started_images/wpf-hubtile-header-image.png)

![wpf hubtile header as control](Getting-Started_images/wpf-hubtile-header-control.png)

## Setting title content 

Title can be used to display updates and notifications in a tile. The content of the title can be an image, a text or a control, etc. The title can be set to the tile by using the [Title](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_Title) property.

{% tabs %}
{% highlight XAML %}

<Grid x:Name="grid">
<!--For setting title as text use this code.-->
<syncfusion:SfHubTile x:Name="hubTile" Title="You have 10 unread mails." Foreground="White"/>

<!--For setting title as an image use this code.-->
<syncfusion:SfHubTile x:Name="hubTile">
   <syncfusion:SfHubTile.Title>
        <Image Source="/Assets/syncfusion.png" Stretch="None" HorizontalAlignment="Left"/>
    </syncfusion:SfHubTile.Title>
</syncfusion:SfHubTile> 

<!--For setting title as a control use this code.-->
<syncfusion:SfHubTile x:Name="hubTile">
   <syncfusion:SfHubTile.Title>
        <TextBlock Text="SYNCFUSION" Foreground="White" FontSize="13"/>
    </syncfusion:SfHubTile.Title>
</syncfusion:SfHubTile>   
</Grid>   

{% endhighlight %}
{% highlight C# %}

//Setting title on Hub Tile.
SfHubTile hubTile = new SfHubTile();
hubTile.Title = "You have 10 unread mails.";
hubTile.Foreground = Brushes.White;
   
//For setting title as image use this code.
SfHubTile hubTile = new SfHubTile();
Image image = new Image(){Source = new BitmapImage(new Uri(@"/Assets/syncfusion.png",UriKind.RelativeOrAbsolute)), Stretch =Stretch.None,HorizontalAlignment = HorizontalAlignment.Left };
hubTile.Title = image;
   
// For setting title as control use this code.
SfHubTile hubTile = new SfHubTile();
TextBlock textblock = new TextBlock(){Text = "SYNCFUSION", Foreground = Brushes.White, FontSize = 13} ; 
hubTile.Title = textblock;
grid.Children.Add(hubTile);

{% endhighlight %}
{% endtabs %}

![wpf hubtile title](Getting-Started_images/wpf-hubtile-title.png)

![wpf hubtile title as image](Getting-Started_images/wpf-hubtile-image.png)

![wpf hubtile title as control](Getting-Started_images/wpf-hubtile-title-control.png)

## Setting image 

The image acts as a pictorial representation of the purpose of tile control. The image can be set to the tile by setting image path to the [ImageSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_ImageSource) property.

{% tabs %}
{% highlight XAML %}

<Grid x:Name="grid">
<!--SfHubTile--> 
<syncfusion:SfHubTile x:Name="hubTile" ImageSource="/Assets/New Mail.png"/>
</Grid>

{% endhighlight %}
{% highlight C# %}

//Setting image for hub tile
SfHubTile hubTile = new SfHubTile();
hubTile.ImageSource = new BitmapImage(new Uri(@"/Assets/New Mail.png",UriKind.RelativeOrAbsolute));
grid.Children.Add(hubTile);
        
{% endhighlight %}
{% endtabs %}

![wpf hubtile image](Getting-Started_images/wpf-tile-setting-image-HubTile.png)

## Setting secondary content

The [secondary content](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfHubTile.html#Syncfusion_Windows_Controls_Notification_SfHubTile_SecondaryContent) specifies the content to be displayed when the tile content of the tile changes during each transition, that is, from primary view. Secondary content can be an image, a text or a control.
{% tabs %}
{% highlight XAML %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
		xmlns:shared="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfShared.Wpf"
        x:Class="WpfApplication1.MainWindow"
        Title="MainWindow" Height="350" Width="525">
<Grid x:Name="grid">
<!--For setting secondary content as image use this code.-->
<syncfusion:SfHubTile x:Name="hubTile" ImageSource="/Assets/New Mail.png" Title="This is title area." Header="Mail" Foreground="White" Interval="00:00:03">
	<syncfusion:SfHubTile.HubTileTransitions>
		<shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
	<!-- For setting secondary content  -->
	<syncfusion:SfHubTile.SecondaryContent>
		<Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
</syncfusion:SfHubTile>

<!--For setting secondary content as text use this code.-->
<syncfusion:SfHubTile x:Name="hubTile" ImageSource="/Assets/New Mail.png" Title="This is title area." Width="200" Height="200" Header="Mail" Foreground="White" Interval="00:00:03" SecondaryContent="This is the secondary content.">
	<syncfusion:SfHubTile.HubTileTransitions>
		<shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
<!--For setting secondary content as control use this code.-->
<syncfusion:SfHubTile x:Name="hubTile" ImageSource="/Assets/New Mail.png" Title="This is title area." Header="Mail" Foreground="White" Interval="00:00:03">
	<syncfusion:SfHubTile.HubTileTransitions>
		<shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
    <syncfusion:SfHubTile.SecondaryContent>
        <TextBlock Text="This is the secondary content of the tile displayed at each transition." TextWrapping="Wrap" FontSize="15" Foreground="White"/>
    </syncfusion:SfHubTile.SecondaryContent>
</syncfusion:SfHubTile>
</Grid>
</Window>

{% endhighlight %}
{% highlight C# %}

SfHubTile hubTile= new SfHubTile();
hubTile.Header = "Mail";
hubTile.Title  = "This is title area.";
hubTile.Foreground = Brushes.White;
hubTile.ImageSource = new BitmapImage(new Uri(@"/Assets/New Mail.png", UriKind.RelativeOrAbsolute));
hubTile.HubTileTransitions.Add(new SlideTransition());
  
//For setting secondary content as an image use this code.
Image image = new Image() { Source = new BitmapImage(new Uri(@"/Assets/HubTile.png", UriKind.RelativeOrAbsolute)) };
hubTile.SecondaryContent = image;
hubTile.Interval = TimeSpan.FromSeconds(3.0);
   
//For setting secondary content as a control use this code.
SfHubTile hubTile= new SfHubTile();
hubTile.Header = "Mail";
hubTile.Title  = "This is title area.";
hubTile.Foreground = Brushes.White;
hubTile.ImageSource = new BitmapImage(new Uri(@"/Assets/New Mail.png", UriKind.RelativeOrAbsolute));
hubTile.HubTileTransitions.Add(new SlideTransition());
TextBlock textblock = new TextBlock() { Text = "This is the secondary content of the tile displayed at each transition.", TextWrapping = TextWrapping.Wrap, FontSize = 15, Foreground = Brushes.White };
hubTile.SecondaryContent = textblock;
hubTile.Interval = TimeSpan.FromSeconds(3.0);   
   
//For setting secondary content as text use this code.
SfHubTile hubTile= new SfHubTile();
hubTile.Header = "Mail";
hubTile.Title  = "This is title area.";
hubTile.Foreground = Brushes.White; 
hubTile.ImageSource = new BitmapImage(new Uri(@"/Assets/New Mail.png", UriKind.RelativeOrAbsolute));
hubTile.HubTileTransitions.Add(new SlideTransition());
hubTile.SecondaryContent = "This is the secondary content.";
hubTile.Interval = TimeSpan.FromSeconds(3.0);
grid.Children.Add(hubTile);
        
{% endhighlight %}
{% endtabs %}    

![wpf hubtile secondarycontent as text](Getting-Started_images/wpf-hubtile-secondarycontent-text.png)

![wpf hubtile secondarycontent as image](Getting-Started_images/wpf-hubtile-slide-transition.png)

![wpf hubtile secondarycontent as control](Getting-Started_images/wpf-hubtile-secondary-control.gif)

## Animation

The tile press animation takes place when the center of the tile is pressed. The tile press animation causes the entire tile to be zoomed in/out at specified interval. The tile press animation can be set by using properties such as [ScaleDepth](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_ScaleDepth) and [TilePressDuration](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_TilePressDuration) in the Hub Tile. The [ScaleDepth](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_ScaleDepth) is used to customize the depth of scaling effect while pressing the center of the tile. The [TilePressDuration](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_TilePressDuration) is used to determine the time taken for the single tile press animation.

{% tabs %}
{% highlight XAML %}

<Grid x:Name="grid">
<syncfusion:SfHubTile x:Name="hubtile" TilePressDuration="00:00:02" ScaleDepth="2" Interval="00:00:03" Title="This is title area" Header="Mail" Foreground="White" ImageSource="/Assets/New Mail.png">  
    <syncfusion:SfHubTile.HubTileTransitions>
        <shared1:SlideTransition/>
    </syncfusion:SfHubTile.HubTileTransitions>
    <syncfusion:SfHubTile.SecondaryContent>
        <Image Source="/Assets/HubTile.png" Stretch="UniformToFill"/>
    </syncfusion:SfHubTile.SecondaryContent>
</syncfusion:SfHubTile>
</Grid>

{% endhighlight %}
{% highlight C# %}

SfHubTile hubTile = new SfHubTile();
hubTile.Header = "Mail";
hubTile.Title = "This is title area";
hubTile.Foreground = Brushes.White;   
hubTile.Interval = TimeSpan.FromSeconds(3.0);
hubTile.ImageSource = new BitmapImage(new Uri(@"/Assets/New Mail.png",UriKind.RelativeOrAbsolute)); 
hubTile.HubTileTransitions.Add(new SlideTransition());
Image image = new Image(){Source = new BitmapImage(new Uri(@"/Assets/HubTile.png",UriKind.RelativeOrAbsolute)) };
hubTile.SecondaryContent = image;
  
//Setting tile press duration and scale depth
hubTile.TilePressDuration = TimeSpan.FromSeconds(2.0);
hubTile.ScaleDepth = 2;
grid.Children.Add(hubTile);

{% endhighlight %}
{% endtabs %}

N> The tile press animation occurs only if the [OverrideDefaultStates](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_OverrideDefaultStates) property is said to be **false**. 

## Transitions

The Hub Tile control supports various transitions which causes the tile to change from primary tile content to secondary tile content. The transitions can be set to the Hub Tile by using the [HubTileTransitions](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfHubTile.html#Syncfusion_Windows_Controls_Notification_SfHubTile_HubTileTransitions) property. These transitions happens based on the specified interval set via [Interval](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfHubTile.html#Syncfusion_Windows_Controls_Notification_SfHubTile_Interval) property of the Hub Tile. The control provides the following built-in transitions:
1. Slide transition
2. Fade transition

{% tabs %}
{% highlight XAML %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
		xmlns:shared="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfShared.Wpf"
        x:Class="WpfApplication1.MainWindow"
        Title="MainWindow" Height="350" Width="525">
<Grid>
<!-- SfHubTile -->
<syncfusion:SfHubTile x:Name="hubTile" ImageSource="/Assets/New Mail.png" Title="This is title area." Header="Mail" Foreground="White" Interval="00:00:03">
	<syncfusion:SfHubTile.HubTileTransitions>
	    <!--For SlideTransition use this code.-->
		<shared:SlideTransition/>
		<!--For FadeTransition use this code.-->
	    <shared:FadeTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
	<!-- For setting secondary content -->
	<syncfusion:SfHubTile.SecondaryContent>
		<Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
</syncfusion:SfHubTile>
</Grid>
</Window>

{% endhighlight %}
{% highlight C# %}

SfHubTile hubTile = new SfHubTile();
//Setting header
hubTile.Header ="HubTile";
hubTile.Foreground = Brushes.White; 
//Setting title    
hubTile.Title  = "This is title area.";  
//Setting image
hubTile.ImageSource = new BitmapImage(new Uri(@"/Assets/New Mail.png",UriKind.RelativeOrAbsolute)); 
//For setting secondary content
Image image = new Image() { Source = new BitmapImage(new Uri(@"/Assets/HubTile.png", UriKind.RelativeOrAbsolute)) };
hubTile.SecondaryContent = image;
   
//For Slide transition use this code.
hubTile.HubTileTransitions.Add(new SlideTransition());
 
//For Fade transition use this code.
hubTile.HubTileTransitions.Add(new FadeTransition());
   
//Setting transition interval
hubTile.Interval = TimeSpan.FromSeconds(3.0);
grid.Children.Add(hubTile);
        
{% endhighlight %}
{% endtabs %}

![wpf hubtile  slide transition](Getting-Started_images/wpf-hubtile-slide-transition.png)

![wpf hubtile fade transition](Getting-Started_images/wpf-hubtile-fade-transition.png)

N> **Syncfusion.SfShared.Wpf** assembly should be included in XAML or import **using Syncfusion.Windows.Controls;** namespace at code behind to support built-in transitions.

### Notifications on transitions

Hub Tile transitions occurs repeatedly at each specified interval. [HubTileTransitionCompleted](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfHubTile.html) event rises on each transition completion. Below example demonstrates the working of the event in the Hub Tile.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfHubTile x:Name="hubTile" Header="Mail" Foreground="White" Title="This is title area." ImageSource="/Assets/New mail.png" Interval="00:00:03" >
	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<i:Interaction.Triggers>
        <i:EventTrigger EventName="HubTileTransitionCompleted">
            <local:HubTileTransitionCompleted />
        </i:EventTrigger>
    </i:Interaction.Triggers>
</syncfusion:SfHubTile>

{% endhighlight %}
{% highlight C# %}
      
public class HubTileTransitionCompleted : TargetedTriggerAction<SfHubTile>
{
    protected override void Invoke(object parameter)
    {
        var hubTile = this.AssociatedObject as SfHubTile;
        MainWindow window = VisualUtils.FindAncestor(hubTile, typeof(MainWindow)) as MainWindow;
        if ((window != null) && (hubTile != null))
        {
          window.hubTile.Background=Brushes.Green;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![wpf hubtile transition completed](Getting-Started_images/wpf-hubtile-transitioncompleted.png)

N> View [sample](https://github.com/SyncfusionExamples/wpf-tile-control-examples/tree/master/Hub%20Tile/Getting%20Started) in GitHub. The sample covers topics such as setting header, image, title, secondary content and transitions in Hub Tile control. 

## Grouping

Several tiles can be grouped using the [GroupName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_GroupName) property of hub tile control. The group name will be used when the entire group of tiles needs to be freeze/unfreeze.

{% tabs %}
{% highlight XAML %}

<Grid x:Name="grid">
<WrapPanel Orientation="Horizontal">
<!-- SfHubTile 1-->
<syncfusion:SfHubTile x:Name="hubTileOne" GroupName="Applications" ImageSource="/Assets/New Mail.png" Title="This is title area." Foreground="White" Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	   <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
 	<syncfusion:SfHubTile.HubTileTransitions>
	  <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
<!-- SfHubTile 2-->
<syncfusion:SfHubTile x:Name="hubTileTwo" Margin="10" GroupName="Applications" ImageSource="/Assets/New Mail.png" Title="This is title area." Foreground="White"  Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
<!-- SfHubTile 3-->
<syncfusion:SfHubTile x:Name="hubTileThree" GroupName="Applications" ImageSource="/Assets/New Mail.png" Title="This is title area." Foreground="White"  Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
 	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
</WrapPanel>
</Grid>

{% endhighlight %}
{% highlight C# %}
    
WrapPanel wrapPanel = new WrapPanel();    wrapPanel.Orientation = Orientation.Horizontal;
grid.Children.Add(wrapPanel);
   
//SfHubTile 1
SfHubTile hubTileOne= new SfHubTile();
hubTileOne.Header = "Mail";
hubTileOne.Title  = "This is title area.";
hubTileOne.Foreground = Brushes.White;       hubTileOne.HubTileTransitions.Add(new SlideTransition());
hubTileOne.Interval = TimeSpan.FromSeconds(3.0);
Image image = new Image() { Source = new BitmapImage(new Uri(@"/Assets/HubTile.png", UriKind.RelativeOrAbsolute)) };
hubTileOne.SecondaryContent = image;       
  
//SfHubTile 2
SfHubTile hubTileTwo= new SfHubTile();
hubTileTwo.Header = "Mail";
hubTileTwo.Title  = "This is title area.";
hubTileTwo.Foreground = Brushes.White; 
hubTileTwo.HubTileTransitions.Add(new SlideTransition());
hubTileTwo.Interval = TimeSpan.FromSeconds(3.0);
Image image = new Image() { Source = new BitmapImage(new Uri(@"/Assets/HubTile.png", UriKind.RelativeOrAbsolute)) };
hubTileTwo.SecondaryContent = image;
Thickness margin = hubTileTwo.Margin;
margin.Left = 10;
hubTileTwo.Margin = margin;
    
//SfHubTile 3
SfHubTile hubTileThree= new SfHubTile();
hubTileThree.Header = "Mail";
hubTileThree.Title  = "This is title area.";
hubTileThree.Foreground = Brushes.White; 
hubTileThree.HubTileTransitions.Add(new SlideTransition());
hubTileThree.Interval = TimeSpan.FromSeconds(3.0);
Image image = new Image() { Source = new BitmapImage(new Uri(@"/Assets/HubTile.png", UriKind.RelativeOrAbsolute)) };
hubTileThree.SecondaryContent = image;   

//Setting group name
hubTileOne.GroupName = "Applications";
hubTileTwo.GroupName = "Applications";
hubTileThree.GroupName = "Applications";
wrapPanel.Children.Add(hubTileOne);
wrapPanel.Children.Add(hubTileTwo);
wrapPanel.Children.Add(hubTileThree);
        
{% endhighlight %}
{% endtabs %}

![wpf hubtile grouping](Getting-Started_images/wpf-hubtile-groupingtiles.jpg)

### Grouping via DataBinding

Grouping several hub tiles can also be done by populating hub tile into a collection by providing proper binding to the collection. Below example demonstrates how to populate a group of hub tiles inside a listview in MVVM pattern.

* Create a new WPF project and add a **Model** class specifying the elements of the Hub Tile. 

{% tabs %}
{% highlight C# %}

public class Model
{
    private string header;
    private string imageSource;
    private TimeSpan interval;
    public string Header
    {
        get { return header; }
        set { header = value; }
    }
    public string ImageSource
    {
        get { return imageSource; }
        set { imageSource = value; }
    }
    public TimeSpan Interval
    {
        get { return interval; }
        set { interval = value; }
    }
}

{% endhighlight %}
{% endtabs %}

* Create a **ViewModel** class where the collection has been declared and populate the items into it.

{% tabs %}
{% highlight C# %}

public class ViewModel
{
    private ObservableCollection<Model> items;
    public ViewModel()
    {
        Items = new ObservableCollection<Model>();
        PopulateItems();
    }      
    public ObservableCollection<Model> Items
    {
        get { return items; }
        set { items = value; }
    }
    private void PopulateItems()
    {
        Model hub1 = new Model { Header = "Mail", ImageSource = @"/Assets/New Mail.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub2 = new Model { Header = "Word", ImageSource = @"/Assets/Word.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub3 = new Model { Header = "Paint",ImageSource = @"/Assets/Painting Brush.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub4 = new Model { Header = "NotePad",ImageSource = @"/Assets/Note.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub5 = new Model { Header = "Microsoft Store ", ImageSource = @"/Assets/Store.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub6 = new Model { Header = "Clock", ImageSource = @"/Assets/Clock.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub7 = new Model { Header = "Calculator", ImageSource = @"/Assets/Calculator.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub8 = new Model { Header = "Excel", ImageSource = @"/Assets/Excel.png", Interval = TimeSpan.FromSeconds(3.0) };
        Model hub9 = new Model { Header = "Microsoft Edge", ImageSource = @"/Assets/MicroSoft Edge.png", Interval = TimeSpan.FromSeconds(3.0) };
        Items.Add(hub1);
        Items.Add(hub2);
        Items.Add(hub3);
        Items.Add(hub4);
        Items.Add(hub5);
        Items.Add(hub6);
        Items.Add(hub7);
        Items.Add(hub8);
        Items.Add(hub9);
    }
}

{% endhighlight %}
{% endtabs %}

* In XAML, bind the collection to the ListView control and use ItemTemplate to populate Hub Tile control into it.

{% tabs %}
{% highlight XAML %}

<Window x:Class="HubTile_Data_Binding.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    xmlns:local="clr-namespace:HubTile_Data_Binding"
    xmlns:shared="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfShared.Wpf"
    Title="Hub Tile Data Binding Demo"    
    ResizeMode="NoResize"
    Width="700"
    Height="600"
    Icon="App.ico"
    WindowStartupLocation="CenterScreen">
    <Window.Resources>
        <local:ImageConverter x:Key="Image" />
    </Window.Resources>
    <Window.DataContext>
        <local:ViewModel />
    </Window.DataContext>
    <Grid HorizontalAlignment="Center">
        <ListView
            x:Name="List" 
            ItemsSource="{Binding Items}"
            ScrollViewer.VerticalScrollBarVisibility="Disabled" Margin="10" BorderBrush="White" >
            <ListView.ItemTemplate>
                <DataTemplate>
                    <syncfusion:SfHubTile
                        Title="{Binding Title}"
                        Foreground="White"
                        Header="{Binding Header}"
                        ImageSource="{Binding ImageSource, Converter={StaticResource Image}}"
                        Interval="{Binding Interval}">
                    </syncfusion:SfHubTile>
                </DataTemplate>
            </ListView.ItemTemplate>
            <ListBox.ItemsPanel>
                <ItemsPanelTemplate>
                    <WrapPanel Margin="10"  Orientation="Vertical" />
                </ItemsPanelTemplate>
            </ListBox.ItemsPanel>
        </ListView>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

![wpf hub tile grouping via databinding](Getting-Started_images/wpf-hubtile-grouping-binding.png)

N> View [sample](https://github.com/SyncfusionExamples/wpf-tile-control-examples/tree/master/Hub%20Tile/Windows-10-like-tiles) in GitHub.

## Freezing/Unfreezing 

Freezing provides support to stop animating the tile contents. Unfreezing provides support to keep the tile content animated. By the following two ways freezing/unfreezing can be set to the Hub Tile:

### Freezing/unfreezing via property

The tile can be frozen by setting [IsFrozen](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_IsFrozen) property to be **true**.

{% tabs %}
{% highlight XAML %}

<Grid x:Name="grid">
<!-- SfHubTile -->
<syncfusion:SfHubTile x:Name="hubTile" Header="Mail" Foreground="White" IsFrozen="True" Title="This is title area." ImageSource="/Assets/New Mail.png" Interval="00:00:03" HorizontalAlignment="Center" VerticalAlignment="Center"  >
    <!-- For setting secondary content -->
	<syncfusion:SfHubTile.SecondaryContent>
		<Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
	<!--For SlideTransition-->
        <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
</Grid>

{% endhighlight %}
{% highlight C# %}
    
SfHubTile hubTile= new SfHubTile();
hubTile.Header = "Mail";
hubTile.Title = "Title area.";
hubTile.Foreground = Brushes.White; 
hubTile.HubTileTransitions.Add(new SlideTransition());
Image image = new Image() { Source = new BitmapImage(new Uri(@"/Assets/HubTile.png", UriKind.RelativeOrAbsolute)) };
hubTile.SecondaryContent = image;
hubTile.Interval=TimeSpan.FromSeconds(3.0);

//Setting freeze property
hubTile.IsFrozen = true;
gird.Children.Add(hubTile);

{% endhighlight %}
{% endtabs %}
 
![wpf hubtile freeze a single tile](Getting-Started_images/wpf-hubtile-single-tile-freezing.png)

The tile can be unfrozen by setting [IsFrozen](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_IsFrozen) property to **false**.

{% tabs %}
{% highlight XAML %}

<Grid x:Name="grid">
<!-- SfHubTile -->
<syncfusion:SfHubTile x:Name="hubTile" Header="Mail" Foreground="White" IsFrozen="False" Title="This is title area." ImageSource="Assests/New Mail.png" HorizontalAlignment="Center" VerticalAlignment="Center" >
    <!-- For setting secondary content -->
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
        <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
</Grid>

{% endhighlight %}
{% highlight C# %}

SfHubTile hubTile= new SfHubTile();
hubTile.Header = "Mail";
hubTile.Title  = "This is title area.";
hubTile.Foreground = Brushes.White; 
hubTile.HubTileTransitions.Add(new SlideTransition());
Image image = new Image() { Source = new BitmapImage(new Uri(@"/Assets/HubTile.png", UriKind.RelativeOrAbsolute)) };
hubTile.SecondaryContent = image;
hubTile.Interval = TimeSpan.FromSeconds(3.0);

//Setting Unfreeze property
hubTile.IsFrozen = false;
grid.Children.Add(hubTile);
        
{% endhighlight %}
{% endtabs %}

![wpf hubtile unfreeze a tile](Getting-Started_images/wpf-hubtile-slide-transition.png)

### Freezing/unfreezing via methods

The [HubTileService](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileService.html) class provides helper methods such as [Freeze](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileService.html#Syncfusion_Windows_Controls_Notification_HubTileService_Freeze_Syncfusion_Windows_Controls_Notification_HubTileBase_) and [UnFreeze](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileService.html#Syncfusion_Windows_Controls_Notification_HubTileService_UnFreeze_Syncfusion_Windows_Controls_Notification_SfHubTile_) to freeze and unfreeze the animation by passing a Hub Tile instance or [GroupName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_GroupName) as an argument. 
* Add required **System.Windows.Interactivity** assembly reference in application. 
* Import schema for interactivity **http://schemas.microsoft.com/expression/2010/interactivity** in XAML or **using System.Windows.Interactivity** namespace in C#.

N> The [HubTileService](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileService.html) class allows to set the freeze/unfreeze state of the tile after the tiles are loaded.

A single tile or a group of tiles can be frozen by using [Freeze](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileService.html#Syncfusion_Windows_Controls_Notification_HubTileService_Freeze_Syncfusion_Windows_Controls_Notification_HubTileBase_) method.

{% tabs %}
{% highlight XAML %}

<Window x:Class="HubTile_Grouping.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:HubTile_Grouping"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:shared="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfShared.Wpf"
        xmlns:i="http://schemas.microsoft.com/expression/2010/interactivity"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
<Grid>
<WrapPanel>
<!-- SfHubTile 1-->
<syncfusion:SfHubTile x:Name="hubTileOne" Foreground="White" GroupName="Applications" ImageSource="/Assets/New Mail.png" Title="This is title area." Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
<!-- SfHubTile 2-->
<syncfusion:SfHubTile x:Name="hubTileTwo" Foreground="White" GroupName="Application" Margin="10" ImageSource="/Assets/New Mail.png" Title="This is title area." Interval="00:00:03"  Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
<!--SfHubTile 3-->
<syncfusion:SfHubTile x:Name="hubTileThree" Foreground="White"GroupName="Applications" ImageSource="/Assets/New Mail.png" Title="This is title area." Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
		<Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
 	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
    <i:Interaction.Triggers>
	    <i:EventTrigger EventName="Loaded">
	        <local:FreezeTiles/>
	    </i:EventTrigger>
	</i:Interaction.Triggers>
</syncfusion:SfHubTile>
</WrapPanel>   
</Grid>
</Window>

{% endhighlight %}
{% highlight C# %}
  
using Syncfusion.Windows.Controls.Notification;
using Syncfusion.Windows.Shared;
using System.Windows.Interactivity;
namespace HubTile_Grouping
{
    public class FreezeTiles : TargetedTriggerAction<SfHubTile>
    {
        protected override void Invoke(object parameter)
        {
            var hubTile = this.AssociatedObject as SfHubTile;
            MainWindow window = VisualUtils.FindAncestor(hubTile, typeof(MainWindow)) as MainWindow;
            if (window != null && hubTile != null)
            {
                //For a single tile
                HubTileService.Freeze(window.hubTileOne); 
                //For  group of tiles
                HubTileService.Freeze("Applications");
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

![wpf hubtile freeze a single tile](Getting-Started_images/wpf-hubtile-single-tile-freezing.png)

Single tile
{:.caption}

![wpf hubtile freeze a group of tiles](Getting-Started_images/wpf-hubtile-freezebygroupname.png)

Group of tiles
{:.caption}

A single tile or a group of tiles can be unfrozen by using [UnFreeze](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileService.html#Syncfusion_Windows_Controls_Notification_HubTileService_UnFreeze_Syncfusion_Windows_Controls_Notification_SfHubTile_) method.
 
{% tabs %}
{% highlight XAML %}

<Window x:Class="HubTile_Grouping.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:HubTile_Grouping"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:shared="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfShared.Wpf"
        xmlns:i="http://schemas.microsoft.com/expression/2010/interactivity"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
<Grid>
<WrapPanel>
<!-- SfHubTile 1-->
<syncfusion:SfHubTile x:Name="hubTileOne" Foreground="White" GroupName="Applications" ImageSource="/Assets/New Mail.png" Title="This is title area." Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
<!-- SfHubTile 2-->
<syncfusion:SfHubTile x:Name="hubTileTwo" Foreground="White" GroupName="Applications" Margin="10" ImageSource="/Assets/New Mail.png" Title="This is title area." Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
</syncfusion:SfHubTile>
<!--SfHubTile 3-->
<syncfusion:SfHubTile x:Name="hubTileThree" Foreground="White" GroupName="Applications" ImageSource="/Assets/New Mail.png" Title="This is title area." Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="UniformToFill" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
	<syncfusion:SfHubTile.HubTileTransitions>
	    <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
	<i:Interaction.Triggers>
	    <i:EventTrigger EventName="Loaded">
	        <local:UnfreezeTiles/>
        </i:EventTrigger>   
	</i:Interaction.Triggers>
</syncfusion:SfHubTile>
</WrapPanel>
</Grid>
</Window>

{% endhighlight %}
{% highlight C# %}
    
using Syncfusion.Windows.Controls.Notification;
using Syncfusion.Windows.Shared;
using System.Windows.Interactivity;  
namespace HubTile_Grouping
{ 
	public class UnfreezeTiles : TargetedTriggerAction<SfHubTile>
    {
        protected override void Invoke(object parameter)
        {
            var hubTile = this.AssociatedObject as SfHubTile;
            MainWindow window = VisualUtils.FindAncestor(hubTile, typeof(MainWindow)) as MainWindow;
            if (window != null && hubTile != null)
            {
	            //For a single tile use this code
	            HubTileService.UnFreeze(window.hubTileOne);
	            //For group of tiles use this code
	            HubTileService.UnFreeze("Applications");
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

![wpf hubtile unfreeze a single tile](Getting-Started_images/wpf-hubtile-slide-transition.png)

Single tile
{:.caption}

![wpf hubtile unfreeze a group of tiles](Getting-Started_images/wpf-hubtile-groupingtiles.jpg)

Group of tiles
{:.caption}
 
## Notifications

Once the tile is pressed, it is notified by the click event and the command property of the Hub Tile.

### Event
  
The [Click](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html) event rises whenever the tile is pressed.

{% tabs %}
{% highlight XAML %} 

<syncfusion:SfHubTile x:Name="hubTile" Interval="00:00:03"  Header="Mail" Foreground="White" Title="This is title area." ImageSource="/Assets/New Mail.png">
	<i:Interaction.Triggers>
        <i:EventTrigger EventName="Click">
            <local:ClickEvent/>
        </i:EventTrigger>
    </i:Interaction.Triggers>
</syncfusion:SfHubTile>

{% endhighlight %}
{% highlight C# %}
      
public class ClickEvent : TargetedTriggerAction<SfHubTile>
{
    protected override void Invoke(object parameter)
    {
        var hubTile = this.AssociatedObject as SfHubTile;
        MainWindow window = VisualUtils.FindAncestor(hubTile, typeof(MainWindow)) as MainWindow;
        if ((window != null) && (hubTile != null))
        {
            MessageBox.Show("Hub Tile has been clicked");
        }
    }
}

{% endhighlight %}
{% endtabs %} 


### Command binding

Command specifies the operation to be performed when the tile is pressed. [Command](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_Command) and [CommandParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_CommandParameter) are used instead of click event in MVVM pattern. 

{% tabs %}
{% highlight XAML%} 
<Window x:Class="Hub.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Hub"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:shared="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfShared.Wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
<Window.DataContext>
   <local:Viewmodel/>
</Window.DataContext>
<Grid x:Name="grid">
<syncfusion:SfHubTile x:Name="hubtile" Command="{Binding HubTileCommand}" CommandParameter="{Binding ElementName=hubtile}"  Interval="00:00:03" Header="Mail" Foreground="White" Title="This is title area." ImageSource="/Assets/New Mail.png"/>
</Grid>
</Window>

{% endhighlight %}
{% highlight C# %}
           
public class Viewmodel
{
    private ICommand hubTileCommand;
    public ICommand HubTileCommand
    {
        get 
        { 
          return hubTileCommand ?? (hubTileCommand = new Command(true, ()=>MyAction("HubTileCommand")));
        }
    }
    private void MyAction(string parameter)
    {
        if (parameter.Equals("HubTileCommand"))
        {
            string message = string.Format("Hub Tile Command executed");
            MessageBox.Show(message);
        }
    }
}
public class Command : ICommand
{
    private bool _canExecute;
    private Action _execute;
    public Command(bool CanExecute, Action Execute)
    {
        _canExecute = CanExecute;
        _execute = Execute;
    }
    public event EventHandler CanExecuteChanged;  
    public bool CanExecute(object parameter)
    {
        return _canExecute;
    }
    public void Execute(object parameter)
    {
        _execute();
    }
}

{% endhighlight %}   
{% endtabs %}

## Appearance and styling

### Customizing header

Header of the tile can be customized either through [HeaderStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Primitives.HeaderedContentControl.html#Syncfusion_Windows_Primitives_HeaderedContentControl_HeaderStyle) or [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Primitives.HeaderedContentControl.html#Syncfusion_Windows_Primitives_HeaderedContentControl_HeaderTemplate) as shown below. [HeaderStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Primitives.HeaderedContentControl.html#Syncfusion_Windows_Primitives_HeaderedContentControl_HeaderStyle) is used to customize the header of the tile by setting its appropriate properties. [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Primitives.HeaderedContentControl.html#Syncfusion_Windows_Primitives_HeaderedContentControl_HeaderTemplate) is used to customize the visual appearance of header by adding user-defined template.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfHubTile x:Name="hubtile" ImageSource="/Assets/New Mail.png"  Title="This is title area." Foreground="White" Header="Mail">

    <!--For setting header style-->
    <syncfusion:SfHubTile.HeaderStyle>
        <Style TargetType="ContentControl">
        <Setter Property="VerticalAlignment" Value="Bottom"/>
        <Setter Property="FontSize" Value="18"/>
        <Setter Property="FontFamily" Value="ALGERIAN"/>
        </Style>
    </syncfusion:SfHubTile.HeaderStyle>
</syncfusion:SfHubTile>  
{% endhighlight %}
{% endtabs %}

![wpf hubtile headerstyle](Getting-Started_images/wpf-hubtile-header-style.png)

{% tabs %}
{% highlight XAML %}
   
<syncfusion:SfHubTile x:Name="hubTile" ImageSource="/Assets/New Mail.png"  Title="This is a title area." Foreground="White" Header="Mail">

    <!--For setting header template-->
    <syncfusion:SfHubTile.HeaderTemplate>
        <DataTemplate>
        <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto"/>
            <ColumnDefinition Width="Auto"/>
        </Grid.ColumnDefinitions>
            <Image Source="/Assets/syncfusion.png" HorizontalAlignment="Left" Stretch="None"/>    
            <TextBlock Text="SYNCFUSION" Foreground="White" Grid.Column="1" FontSize="17"  />
        </Grid>
        </DataTemplate>
    </syncfusion:SfHubTile.HeaderTemplate>
</syncfusion:SfHubTile>
{% endhighlight %}
{% endtabs %}

![wpf hubtile header template](Getting-Started_images/wpf-hubtile-header-template.png)

### Customizing title

The [TitleStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_TitleStyle) property is used to customize the title of the tile by setting its appropriate properties.

{% tabs %}
{% highlight XAML %}
<!-- SfHubTile -->
<syncfusion:SfHubTile x:Name="hubTile" ImageSource="/Assets/New Mail.png"  Title="This is a title area." Header="Mail" Foreground="White">

    <!-- For setting title style -->
    <syncfusion:SfHubTile.TitleStyle>
        <Style TargetType="ContentControl">
        <Setter Property="Foreground" Value="White"/>
        <Setter Property="FontSize" Value="15"/>
        <Setter Property="ContentTemplate">
        <Setter.Value>
        <DataTemplate>
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="Auto"/>
                <ColumnDefinition Width="Auto"/>
            </Grid.ColumnDefinitions>
            <Image Source="/Assets/syncfusion.png" HorizontalAlignment="Left" VerticalAlignment="Top" Stretch="None"/>
            <TextBlock Text="SYNCFUSION" FontSize="17" Grid.Column="1" /> 
        </Grid>
        </DataTemplate>
        </Setter.Value>
        </Setter>
        </Style>
    </syncfusion:SfHubTile.TitleStyle>
</syncfusion:SfHubTile>
{% endhighlight %}
{% endtabs %}

![wpf hub tile title customization](Appearance-Styling_images/wpf-hubtile-title-customization.png)

### Customizing secondary content

By the following two ways the secondary content of the Hub Tile can be customized:

#### Customizing secondary content via property
 
The secondary content of the tile can be customized by using the appropriate [SecondaryContent](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfHubTile.html#Syncfusion_Windows_Controls_Notification_SfHubTile_SecondaryContent) property like below.
{% tabs %}
{% highlight XAML %}
<!-- SfHubTile -->
<syncfusion:SfHubTile x:Name="hubTile" Foreground="White"  ImageSource="/Assets/New Mail.png" Title="This is title area." Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.HubTileTransitions>
        <shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>
   	<syncfusion:SfHubTile.SecondaryContent>
	    <Image Source="/Assets/HubTile.png" Stretch="Fill" ToolTip="Secondary Content" Margin="-1"/>
	</syncfusion:SfHubTile.SecondaryContent>
</syncfusion:SfHubTile>
{% endhighlight %}
{% endtabs %}

![wpf hubtile secondary content customization](Appearance-Styling_images/wpf-hubtile-secondarycontent.png)

#### Customizing secondary content via template
 
The secondary content of the tile can be customized by using the [SecondaryContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfHubTile.html#Syncfusion_Windows_Controls_Notification_SfHubTile_SecondaryContentTemplate) property like below.

{% tabs %}
{% highlight XAML %}
<!-- SfHubTile -->
<syncfusion:SfHubTile x:Name="hubTile"  ImageSource="/Assets/New Mail.png" Title="This is title area." Foreground="White" Height="200" Interval="00:00:03" Header="Mail">
	<syncfusion:SfHubTile.HubTileTransitions>
		<shared:SlideTransition/>
	</syncfusion:SfHubTile.HubTileTransitions>

 <!--setting secondary content template-->
    <syncfusion:SfHubTile.SecondaryContentTemplate>
        <DataTemplate>
        <Grid>
            <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="Auto"/>
            </Grid.RowDefinitions>
            <Image Source="/Assets/HubTile.png" />
            <CheckBox x:Name="checkbox" Grid.Row="1" Foreground="White" Content="Freeze" IsChecked="{Binding ElementName=hubtile,Path=IsFrozen}" />
            <TextBlock Grid.Row="2" Text="This is the secondary content of the tile displayed at each transition." Foreground="White" FontSize="12" TextWrapping="Wrap" FontStyle="Italic"/>
        </Grid>
        </DataTemplate>
    </syncfusion:SfHubTile.SecondaryContentTemplate>
</syncfusion:SfHubTile>
{% endhighlight %}
{% endtabs %}

![wpf hubtile secondary content customization using secondary content template](Getting-Started_images/wpf-hubtile-secondary-content-template.jpg)
