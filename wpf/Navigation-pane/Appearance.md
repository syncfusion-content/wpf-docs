---
layout: post
title: Appearance| GroupBar | Wpf | Syncfusion
description: This section explain about how to customize the appearance of Syncfusion WPF GroupBar. 
platform: wpf
control: GroupBar
documentation: ug
---

# Appearance in WPF Navigation Pane (GroupBar)

This section deals with the appearance of GroupBar control and contains the following topics:

## Visual Mode

Visual Mode feature in GroupBar is used to change the visual style of the GroupBar. This is done using the VisualMode property. This dependency property can be used to set the visual mode for GroupBar content. It returns the visual mode of the GroupBar.

There are three types of visual modes available in GroupBar.

* Default
* MultipleExpansion
* StackMode

### Default

By setting this enum to the VisualMode property, expand and collapse of the GroupBarItem in GroupBar is enabled. Only one GroupBar item can be expanded at a time. On expanding another GroupBar item, the previously expanded groupbar item will be collapsed.

### MultipleExpansion

By setting this enum to the VisualMode property, the style of GroupBar will be similar to the tree view structure in terms of expand and collapse. Any number of GroupBar items can be expanded or collapsed. 

### StackMode

By setting this enum to the VisualMode property, the GroupBar behavior is set to behave like the Outlook GroupBar.

Use the following code snippet to set the VisualMode property to _Default_.



{% tabs %}
{% highlight xaml %} 
<!-- Adding GroupBar that have visual mode is Default -->
<syncfusion:GroupBar Height="300" Width="230" VisualMode="Default" Name="groupBar">  
<!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">    <!-- Adding content for GroupBar item using GroupView -->    <syncfusion:GroupView>      <syncfusion:GroupViewItem Text="List View"/>      <syncfusion:GroupViewItem Text="Show ContextMenu"/>      <syncfusion:GroupViewItem Text="Show ToolTip"/>    </syncfusion:GroupView>  </syncfusion:GroupBarItem>  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode">    <!-- Adding content for GroupBar item using GroupView -->    <syncfusion:GroupView>      <syncfusion:GroupViewItem Text="Default"/>      <syncfusion:GroupViewItem Text="Multiple Expansion"/>      <syncfusion:GroupViewItem Text="StackMode"/>    </syncfusion:GroupView>  </syncfusion:GroupBarItem>  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence">    <!-- Adding content for GroupBar item using GroupView -->    <syncfusion:GroupView>      <syncfusion:GroupViewItem Text="Save State"/>      <syncfusion:GroupViewItem Text="Load State"/>      <syncfusion:GroupViewItem Text="Reset State"/>    </syncfusion:GroupView>  </syncfusion:GroupBarItem>  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem Name="groupBarItem4" HeaderImageSource="bin.png" Header="Orientation">    <!-- Adding content for GroupBar item using panel -->    <StackPanel Orientation="Vertical">      <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    </StackPanel>  </syncfusion:GroupBarItem></syncfusion:GroupBar> {% endhighlight %} 

{% highlight C# %} 
//Setting visual mode as Default
groupBar.VisualMode = VisualMode.Default; 
{% endhighlight %} 
{% endtabs %}




![](Appearance_images/Appearance_img1.jpeg)



### Multiple Expansion

In Multiple Expansion mode, more than one item can be expanded as seen in a tree view structure.

Use the following code snippet to set VisualMode property to Multiple Expansion.

{% tabs %}
{% highlight xaml %}
 <!-- Adding GroupBar that have visual mode is Multiple Expansion -->
 <syncfusion:GroupBar Height="300" Width="230" VisualMode="MultipleExpansion" Name="groupBar">  
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">   
 <!-- Adding content for groupbar item using GroupView -->    
 <syncfusion:GroupView>    
 <syncfusion:GroupViewItem Text="List View"/>     
 <syncfusion:GroupViewItem Text="Show ContextMenu"/>     
 <syncfusion:GroupViewItem Text="Show ToolTip"/>    
 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem>  
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode">   
 <!-- Adding content for groupbar item using GroupView -->  
 <syncfusion:GroupView>     
 <syncfusion:GroupViewItem Text="Default"/>   
 <syncfusion:GroupViewItem Text="Multiple Expansion"/>  
 <syncfusion:GroupViewItem Text="StackMode"/>  
 </syncfusion:GroupView>  
 </syncfusion:GroupBarItem>  
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence"> 
 <!-- Adding content for groupbar item using GroupView -->  
 <syncfusion:GroupView>   
 <syncfusion:GroupViewItem Text="Save State"/>      
 <syncfusion:GroupViewItem Text="Load State"/>  
 <syncfusion:GroupViewItem Text="Reset State"/> 
 </syncfusion:GroupView>  </syncfusion:GroupBarItem> 
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem4" HeaderImageSource="bin.png" Header="Orientation"> 
 <!-- Adding content for groupbar item using panel -->  
 <StackPanel Orientation="Vertical">      
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>     
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>   
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton>  
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>  
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>     
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton> 
 </StackPanel>  </syncfusion:GroupBarItem></syncfusion:GroupBar> 
 {% endhighlight %} 

{% highlight C# %}
 //groupBar is a name of groupbar
 //groupbar that have visual mode is MultipleExpansion
 groupBar.VisualMode = VisualMode.MultipleExpansion;
 {% endhighlight %} 
{% endtabs %}




![](Appearance_images/Appearance_img2.jpeg)



### Stack Mode

In StackMode, only one item can be expanded, Items are organized in stack-like mode. It looks like an Outlook groupbar. In stack mode, the pop-up menu is displayed at the bottom of the groupbar. This helps customize groupbar items in a GroupBar control.

Use the following code snippet to set the VisualMode property to StackMode.


{% tabs %}
{% highlight xaml %} 
<!-- Adding GroupBar that have visual mode is StackMode-->
<syncfusion:GroupBar Height="300" Width="230" VisualMode="StackMode" Name="groupBar"> 
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">  
 <!-- Adding content for groupbar item using GroupView -->  
 <syncfusion:GroupView>     
 <syncfusion:GroupViewItem Text="List View"/>      
 <syncfusion:GroupViewItem Text="Show ContextMenu"/>   
 <syncfusion:GroupViewItem Text="Show ToolTip"/>    
 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem> 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode">
 <!-- Adding content for groupbar item using GroupView -->  
 <syncfusion:GroupView>     
 <syncfusion:GroupViewItem Text="Default"/>    
 <syncfusion:GroupViewItem Text="Multiple Expansion"/> 
 <syncfusion:GroupViewItem Text="StackMode"/>    
 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem>
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence">  
 <!-- Adding content for groupbar item using GroupView -->  
 <syncfusion:GroupView>   
 <syncfusion:GroupViewItem Text="Save State"/>   
 <syncfusion:GroupViewItem Text="Load State"/>   
 <syncfusion:GroupViewItem Text="Reset State"/>   
 </syncfusion:GroupView>  
 </syncfusion:GroupBarItem> 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem4" HeaderImageSource="bin.png" Header="Orientation">  
 <!-- Adding content for groupbar item using panel -->  
 <StackPanel Orientation="Vertical">    
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>  
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton> 
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton> 
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/> 
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>    
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>
 </StackPanel>  
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar>
 {% endhighlight %} 

{% highlight C# %} 
//groupBar is a name of groupbar
//groupbar that have visual mode is StackMode
groupBar.VisualMode = VisualMode.StackMode; 

{% endhighlight %} 
{% endtabs %}

![](Appearance_images/Appearance_img3.jpeg)



## Theme

GroupBar supports various built-in themes. Refer to the below links to apply themes for the GroupBar,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)
  

![](Appearance_images/Appearance_img4.jpeg)





![](Appearance_images/Appearance_img5.jpeg)







![](Appearance_images/Appearance_img6.png)





![](Appearance_images/Appearance_img7.png)



## Item Container Style

1. The ItemContainerStyle property of GroupBar sets the style for GroupBarItem. This style will be applied to all items in the GroupBar control.style for GroupBarItem.


   ~~~xaml

		<Style TargetType="{x:Type syncfusion:GroupBarItem}" x:Key="GroupBarItemStyle">

		<Setter Property="HeaderTemplate" >

		<Setter.Value>

		<DataTemplate >

		<Grid>

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="25" />

		<ColumnDefinition Width="*" />

		</Grid.ColumnDefinitions>                            

		<TextBlock Text="{Binding XPath=@Name}" Margin="5" Foreground="Green" VerticalAlignment="Center" FontWeight="Bold" FontFamily="Bookman Old Style" Grid.Column="1"/>

		</Grid>

		</DataTemplate>



		</Setter.Value>

		</Setter>

		<Setter Property="ContentTemplate">

		<Setter.Value>

		<DataTemplate>

		<Grid >

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="4*"/>

		<ColumnDefinition Width="6*"/>

		</Grid.ColumnDefinitions>

		<Image Source="{Binding XPath=@ImagePath}"/>

		<TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" Grid.Column="1"/>

		</Grid>

		</DataTemplate>

		</Setter.Value>

		</Setter>

		</Style>

   ~~~



2. Set ItemContainerStyle of GroupBar as follows.



   ~~~xaml
		<syncfusion:GroupBar Name="groupBar1" AllowCollapse="True" 

		VisualMode="StackMode" 

		ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"  

		ItemContainerStyle="{StaticResource GroupBarItemStyle}"

		/>


   ~~~


3. This will generate the following GroupBar control.

   ![](Appearance_images/Appearance_img8.png)





## Item Container Style Selector

The ItemContainerStyleSelector property is used to choose the ItemContainerStyle at run time based on specified conditions. 

1. Create the styles in the Window’s resource.

   ~~~xaml

		<Style TargetType="{x:Type syncfusion:GroupBarItem}" x:Key="WpfItemStyle">

		<Setter Property="HeaderTemplate" >

		<Setter.Value>

		<DataTemplate>

		<StackPanel Orientation="Horizontal">

		<Image Margin="3" Source="D:\IUE_DOC\GroupBarWPF\GroupBarIUEDemo\GroupBarIUEDemo\Data\wpf.png" Width="20" Height="20"/>

		<TextBlock Text="{Binding XPath=@Name}" FontWeight="Bold" Foreground="Blue"/>

		</StackPanel>

		</DataTemplate>

		</Setter.Value>

		</Setter>            

		<Setter Property="ContentTemplate">

		<Setter.Value>                    

		<DataTemplate>

		<Grid >

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="4*"/>

		<ColumnDefinition Width="6*"/>

		</Grid.ColumnDefinitions>

		<Image Source="{Binding XPath=@ImagePath}"/>

		<TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" Grid.Column="1"/>

		</Grid>

		</DataTemplate>

		</Setter.Value>

		</Setter>

		</Style>



		<Style TargetType="{x:Type syncfusion:GroupBarItem}" x:Key="CsItemStyle">

		<Setter Property="HeaderTemplate" >

		<Setter.Value>

		<DataTemplate>

		<StackPanel Orientation="Horizontal">

		<Image Margin="3" Source="D:\IUE_DOC\GroupBarWPF\GroupBarIUEDemo\GroupBarIUEDemo\Data\images.jpg" Width="20" Height="20"/>

		<TextBlock Text="{Binding XPath=@Name}" FontWeight="Bold" Foreground="Green"/>

		</StackPanel>

		</DataTemplate>

		</Setter.Value>

		</Setter>

		<Setter Property="ContentTemplate">

		<Setter.Value>

		<DataTemplate>

		<Grid >

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="4*"/>

		<ColumnDefinition Width="6*"/>

		</Grid.ColumnDefinitions>

		<Image Source="{Binding XPath=@ImagePath}"/>

		<TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" Grid.Column="1"/>

		</Grid>

		</DataTemplate>

		</Setter.Value>

		</Setter>

		</Style>


   ~~~

2. Create the StyleSelector in the code.


   ~~~csharp


		public class GroupBarItemContainerStyleSelector : StyleSelector

		{



		public override Style SelectStyle(object item, DependencyObject container)

		{



		Window window = Application.Current.MainWindow;



		string bookname = (item as System.Xml.XmlElement).GetAttribute("Name").ToString().ToLower();

		if (bookname.Contains("wpf"))

		{

		return ((Style)window.Resources["WpfItemStyle"]);

		}

		else

		{

		return ((Style)window.Resources["CsItemStyle"]);

		}



		}

		}


   ~~~

3. Now define the style selector in the Window’s resource.



   ~~~xaml
			<local:GroupBarItemContainerStyleSelector 
			x:Key="groupBarItemContainerStyleSelector"/>

   ~~~



4. Now set ItemContainerStyle for the GroupBar control.


   ~~~xaml
		<syncfusion:GroupBar Name="groupBar1"  AllowCollapse="True" 

		VisualMode="StackMode" 

		ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"  

		ItemContainerStyleSelector="{StaticResource groupBarItemContainerStyleSelector}"

		/>

   ~~~



This will generate the following GroupBar control.



![](Appearance_images/Appearance_img9.png)

   

## Drag Marker Color

You can apply a custom brush for the drag marker by using the DragMarkerBrush property. This brush setting can be visualized while dragging the items in the GroupBar.

DragMarkerBrush – This dependency property sets the brush value for the drag marker. 

Use the below code snippet to set this property.


{% tabs %}
{% highlight xaml %}
 <!-- Adding GroupBar -->
 <syncfusion:GroupBar Height="200" DragMarkerBrush="Red" Width="230" Name="groupBar"> 
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem">   
 <!-- Adding content for GroupBar item using panel -->   
 <StackPanel Orientation="Vertical">     
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>    
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>   
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>  
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>     
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>  
 </StackPanel>  
 </syncfusion:GroupBarItem>
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">  
 <!-- Adding content for GroupBar item using GroupView -->  
 <syncfusion:GroupView Name="groupView" IsListViewMode="True">   
 <syncfusion:GroupViewItem Text="List View"/>    
 <syncfusion:GroupViewItem Text="Show ContextMenu"/>   
 <syncfusion:GroupViewItem Text="Show ToolTip"/>   
 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar> 
 {% endhighlight %} 

{% highlight C# %} 
//Setting drag marker brush
groupBar.DragMarkerBrush = Brushes.Red; 
{% endhighlight %} 
{% endtabs %}


## Custom Template for the Collapse Button

CollapseButtonTemplate property is used to customize the collapse button by applying custom templates. The target type of template is toggle button. By using this property, the user must write their own control template of target type ToggleButton.

Use the following code snippet for setting a template for the CollapsedButton.



{% highlight xaml %}



<!-- Adding GroupBar that has animation speed -->

<syncfusion:GroupBar Height="300" Width="230" Name="groupBar" AllowCollapse="True" VisualMode="StackMode">

  <syncfusion:GroupBar.CollapseButtonTemplate>

    <ControlTemplate TargetType="{x:Type ToggleButton}">

      <Border Height="16" Width="16">

        <Path Name="path" Data="M0,0L3.5,4 7,0z" Fill="Black" HorizontalAlignment="Center" VerticalAlignment="Center"/>

      </Border>

      <ControlTemplate.Triggers>

        <Trigger Property="IsChecked" Value="True">

          <Setter Property="Data" TargetName="path" Value="M 3 1 L 7 5 L 3 9 z"/>

        </Trigger>

      </ControlTemplate.Triggers>

    </ControlTemplate>

  </syncfusion:GroupBar.CollapseButtonTemplate>



  <!-- Adding GroupBarItem -->

  <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">



    <!-- Adding content for GroupBar item using GroupView -->

    <syncfusion:GroupView Name="groupView" IsListViewMode="True">

      <syncfusion:GroupViewItem Text="List View"/>

      <syncfusion:GroupViewItem Text="Show ContextMenu"/>

      <syncfusion:GroupViewItem Text="Show ToolTip"/>

    </syncfusion:GroupView>

  </syncfusion:GroupBarItem>

</syncfusion:GroupBar>

{% endhighlight %} 

## Collapse Button Color

You can also set the background brush and MouseOver background brush for the collapse button using the CollapseButtonBackground and CollapseButtonMouseOverBackground properties, respectively.

Use the following code snippet to set these properties.


{% tabs %}
{% highlight xaml %}
 <!-- Adding GroupBar  -->
 <syncfusion:GroupBar Height="300" Width="230" Name="groupBar" CollapseButtonBackground="AliceBlue" CollapseButtonMouseOverBackground="Bisque" AllowCollapse="True"  VisualMode="StackMode"> 
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif"  Header="General">   
 <!-- Adding content for GroupBar item using GroupView -->  
 <syncfusion:GroupView Name="groupView" IsListViewMode="True">   
 <syncfusion:GroupViewItem Text="List View"/>      
 <syncfusion:GroupViewItem Text="Show ContextMenu"/>    
 <syncfusion:GroupViewItem Text="Show ToolTip"/>   
 </syncfusion:GroupView>  
 </syncfusion:GroupBarItem>  
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2"  Header="Visual Mode">  
 <!-- Adding content for GroupBar item using GroupView -->  
 <syncfusion:GroupView>     
 <syncfusion:GroupViewItem Text="Default"/>  
 <syncfusion:GroupViewItem Text="Multiple Expansion"/>  
 <syncfusion:GroupViewItem Text="StackMode"/>   
 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem> 
 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3"  Header="State Persistence">  
 <!-- Adding content for GroupBar item using GroupView -->   
 <syncfusion:GroupView>      
 <syncfusion:GroupViewItem Text="Save State"/>
 <syncfusion:GroupViewItem Text="Load State"/>    
 <syncfusion:GroupViewItem Text="Reset State"/>  
 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar> 
 {% endhighlight %}  

 
{% highlight C# %} 
//Enable AllowCollapse property for GroupBar
groupBar.AllowCollapse = true; 
//Set the Background brush for Collapse button
groupBar.CollapseButtonBackground = Brushes.AliceBlue;
//Set the MouseOverBackground brush for Collapse Button
groupBar.CollapseButtonMouseOverBackground = Brushes.Bisque;
 {% endhighlight %}  
{% endtabs %}


## Customizing Group Bar Header

Group Bar header can be customized in a required manner. Customized background color, corner radius, height, text alignment etc. for a Group Bar header can be customized in the following way.



{% highlight xaml %}



<Style x:Key="headerStyle" TargetType="{x:Type Border}">

<Setter Property="CornerRadius" Value="7"/>

<Setter Property="Background" Value="Pink"/>

<Setter Property="Height" Value="30" />

</Style>

<syncfusion:GroupBar  GroupBarHeaderStyle="{StaticResource headerStyle}"/>

{% endhighlight %} 





![](Appearance_images/Appearance_img10.jpeg)



