---
layout: post
title: Concepts-And-Features | NavigationDrawer | WPF | Syncfusion
description: concepts and features
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Concepts and Features

## ContentView

ContentView is the main view of the NavigationDrawer where the desired items can be placed.

{% highlight xml%}

    <syncfusion:SfNavigationDrawer x:Name="drawer">
		<syncfusion:SfNavigationDrawer.ContentView>
			<Grid Background="Black">
				<Button BorderBrush="#393939" BorderThickness="2" VerticalAlignment="Center" Click="ButtonBase_OnClick" HorizontalAlignment="Center" >
					<StackPanel Orientation="Vertical" VerticalAlignment="Center" HorizontalAlignment="Center">
						<Image Source="/Assets/NavigationDrawer/User.png" Height="80" Width="100"/>
						<TextBlock HorizontalAlignment="Center" Margin="0 10 0 0" Text="James Pollock"/>
					</StackPanel>
				</Button>
			</Grid>
		</syncfusion:SfNavigationDrawer.ContentView>
	</syncfusion:SfNavigationDrawer>

{% endhighlight %}


![](Concepts-and-features_images/ContentView_img1.png)  


## DrawerContentView

The SfNavigationDrawer control contains the DrawerContentView, a part of the DrawerView panel. The DrawerContentView displays the navigation items that you need to jump to.

{% highlight xml%}

    <syncfusion:SfNavigationDrawer.DrawerContentView>
			<Grid Background="Black">
				<ListBox x:Name="list" ItemsSource="{Binding Contents}">
					<ListBox.ItemTemplate>
						<DataTemplate>
							<TextBlock  Text="{Binding Name}" Padding="15" TextAlignment="Center" FontSize="23" Foreground="White"/>
						</DataTemplate>
					</ListBox.ItemTemplate>
				</ListBox>
			</Grid>
		</syncfusion:SfNavigationDrawer.DrawerContentView>

{% endhighlight %}


## DrawerFooterView

Gets or sets the footer for the DrawerView panel in the SfNavigationDrawer control.  

{% highlight xml%}

    <syncfusion:SfNavigationDrawer.DrawerFooterView>
			<Grid Background="#31ade9">
				<TextBlock Text="james@gmail.com" HorizontalAlignment="Center" Style="{StaticResource PhoneTextNormalStyle}" Padding="0 0 0 15" Foreground="White" VerticalAlignment="Center"/>
			</Grid>
		</syncfusion:SfNavigationDrawer.DrawerFooterView>

{% endhighlight %}

![](Concepts-and-features_images/DrawerFooterView_img1.png) 


## DrawerHeaderView

Gets or sets the DrawerHeaderView of the DrawerView panel in the SfNavigationDrawer control.

{% highlight xml%}
	
    <syncfusion:SfNavigationDrawer.DrawerHeaderView>
			<Grid Background="#31ade9">
				<Image Source="/Assets/NavigationDrawer/User.png" Height="75" VerticalAlignment="Center" HorizontalAlignment="Center" Margin="0 0 0 5" />
			</Grid>
		</syncfusion:SfNavigationDrawer.DrawerHeaderView>

{% endhighlight %}


## DrawerHeight

Gets or sets the height for the DrawerView panel in the NavigationDrawer control.

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" DrawerHeight="400"/>

{% endhighlight %}

{% highlight c# %}

	drawer.DrawerHeight = 400d;
	
{% endhighlight %}

{% endtabs %}


## DrawerWidth

Gets or sets the width for the DrawerView panel in the NavigationDrawer control.

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" DrawerWidth="200"/>

{% endhighlight %}

{% highlight c# %}

	drawer.DrawerWidth = 200d;
	
{% endhighlight %}

{% endtabs %}


## TouchThreshold

Gets or sets the threshold value from the edges for easy panning from the edges. The default value of TouchThreshold is 15.

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" TouchThreshold="25"/>

{% endhighlight %}
{% highlight c# %}

	drawer.TouchThreshold = 25d;

{% endhighlight %}
{% endtabs %}

## Animation Duration

Gets or sets the TimeSpan value, by which the DrawerContent can be brought to view.

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" AnimationDuration="100"/>

{% endhighlight %}
{% highlight c# %}

	drawer.AnimationDuration = 100;

{% endhighlight %}
{% endtabs %}

## Position

The Position property specifies the position of the DrawerView panel. The Position property has the following four options:

* Left
* Right
* Top
* Bottom

The default position is Left.  

{% tabs %}

{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" Position="Left" ></syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

	drawer.Position = Position.Left;

{% endhighlight %}

{% endtabs %}

![](Concepts-and-features_images/Position_img1.png)                                            


The following code example shows how to set the SfNavigationDrawer to the right.  

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" Position="Right" ></syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

	drawer.Position = Position.Right;

{% endhighlight %}

{% endtabs %}

![](Concepts-and-features_images/Position_img2.png)

The following code example shows how to set the SfNavigationDrawer at the top.  

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" Position="Top" ></syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

	drawer.Position = Position.Top;

{% endhighlight %}

{% endtabs %}

![](Concepts-and-features_images/Position_img3.png)                                           


The following code example shows how to set the SfNavigationDrawer at the bottom.  

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" Position="Bottom" ></syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

	drawer.Position = Position.Bottom;

{% endhighlight %}

{% endtabs %}

![](Concepts-and-features_images/Position_img4.png)



## Transition

The Transition property specifies the animations for the DrawerView panel. The Transition property has the following options:

* SlideOnTop
* Push
* Reveal

The default transition is SlideOnTop. That draws the DrawerContent on top of the main content.


{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" Transition="SlideOnTop" ></syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

	drawer.Transition = Transition.SlideOnTop;

{% endhighlight %}

{% endtabs %}

![](Concepts-and-features_images/Transition_img1.png)                                           


The following code example shows how to set Transition as Push to SfNavigationDrawer. This transition moves the Drawer and main content simultaneously.

{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" Transition="Push" ></syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

	drawer.Transition = Transition.Push;

{% endhighlight %}

{% endtabs %}

![](Concepts-and-features_images/Transition_img2.png)                                              


The following code example shows how to set Transition as Reveal to SfNavigationDrawer. In this transition, the Drawer content is stable and the main content is moved to reveal the drawer content.


{% tabs %}
{% highlight xml %}

	<syncfusion:SfNavigationDrawer x:Name="drawer" Transition="Reveal" ></syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

	drawer.Transition = Transition.Reveal;

{% endhighlight %}

{% endtabs %}


![](Concepts-and-features_images/Transition_img3.png)                                         
