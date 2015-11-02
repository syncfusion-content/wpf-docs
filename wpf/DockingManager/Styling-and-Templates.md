---
layout: post
title: Styling and Templates | Docking Manager | WPF | Syncfusion
description: Styling and Templates
platform: wpf
control: DockingManager
documentation: ug
---


# Styling and Templates

The UI for Dock, Float and Document windows of DockingManager can be changed using different styles and Templates.

## Visual Styles

When you want a rich and professional look and feel for the Dockwindows, you can apply the visual styles. Some of the available visual style are as follows:

<table>
<tr>
<td>
* Blend<br/>* Office2007Blue<br/>* Office2007Black<br/>* Office2007Silver<br/>* Office2010Blue<br/>* Office2010Black<br/>* Office2010Silver<br/>* VS2010<br/>* Metro<br/>* Transparent<br/></td></tr>
</table>

The visual style can be applied for the DockingManager using the property `VisualStyle` , an attached property of the `SkinStorage`.

* Blend – Set the visual style as Blend for the DockingManager.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Blend");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img1.jpeg)


* Office2007Blue – Set visual style for DockingManager as Office2007Blue.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Office2007Blue");

{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img2.jpeg)


* Office2007Black – Setting visual style for DockingManager as Office2007Black.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Office2007Black");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img3.jpeg)


* Office2007Silver – Setting visualstyle for the DockingManager as Office2007Silver.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Office2007Silver");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img4.jpeg)


* Office2010Blue – Set the visual style for DockingManager as Office2010Blue.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Office2010Blue");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img5.jpeg)


* Office2010Black – Set visual style for DockingManager as Office2010Black

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Office2010Black");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img6.jpeg)




* Office2010SSilver – Set visual style as Office2010Silver.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Office2010Silver");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img7.jpeg)


* VS2010- Setting visual style for the DockingManager as VS2010.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"VS2010");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img8.jpeg)


* Metro – Sett visual style for DockingManager as Metro.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Metro");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img9.jpeg)


* Transparent – Setting visual style for DockingManager as Transparent.

{% highlight c# %}

SkinStorage.SetVisualStyle(DockingManager1,"Transparent");





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img10.jpeg)

## Dock Window Style

DockingManager allows you to set style for some of the Docking controls such as DockedHeaderPresenter, DockedElementTabbedHost. This is explained in detail under the DockHeaderStyle and DockedElementTabbedHostStyle section.

### AwlButtonTemplate

The style of the pin button of the Dock window can customized using the `AwlButtonTemplate` property of DockingManager with the TargetType as `ToggleButton` to have a customized look and feel for the Pin Button. 

{% highlight xaml %}
<syncfusion:DockingManager  x:Name="DockingManager1">

<syncfusion:DockingManager.AwlButtonTemplate>

<ControlTemplate TargetType="{x:Type ToggleButton}">

<Border x:Name="Border1">

<TextBlock x:Name="Text1" Text="PinButton" Foreground="White"></TextBlock>

</Border>

<ControlTemplate.Triggers>

<Trigger Property="IsMouseOver" Value="True">

<Setter TargetName="Border1" Property="Background" Value="Black"></Setter>

<Setter TargetName="Text1" Property="Foreground" Value="Red"></Setter>

</Trigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.AwlButtonTemplate>

<ContentControl syncfusion:DockingManager.Header="Child1"/>

<ContentControl syncfusion:DockingManager.Header="Child2"/>

</syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img14.jpeg)



### CloseButtonTemplate


The close button for the Docked window can be customized using the `CloseButtonTemplate`, and can be used to get or set the control template for the close button for the windows of DockingManager with TargetType as ToggleButton.


{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1">

<syncfusion:DockingManager.CloseButtonTemplate>

<ControlTemplate TargetType="{x:Type ToggleButton}">

<StackPanel

<Border x:Name="Border1">

<TextBlock x:Name="Block" Background="Red" Text="Close" Foreground="Black"></TextBlock>

</Border>

</StackPanel>

</ControlTemplate>

</syncfusion:DockingManager.CloseButtonTemplate>

<ContentControl

syncfusion:DockingManager.Header="Child1"/>

<ContentControl

syncfusion:DockingManager.Header="Child2"/>

</syncfusion:DockingManager>





{% endhighlight %}


![](StylingandTemplates_images/StylingandTemplates_img15.jpeg)


### MenuButtonTemplate

The context menu button appearance in the Dock window header can be customized using `MenuButtonTemplate` property by setting with the Target Type as `ToggleButton`.


{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1">

<syncfusion:DockingManager.MenuButtonTemplate>

<ControlTemplate TargetType="{x:Type ToggleButton}">

<StackPanel>

<Border x:Name="Border1">

<TextBlock x:Name="TextBlock" Text="Menu" Foreground="Black"></TextBlock>

</Border>

</StackPanel>

<ControlTemplate.Triggers>

<Trigger Property="IsMouseOver" Value="True">

<Setter TargetName="Border1" Property="Background" Value="Black"></Setter>

<Setter TargetName="TextBlock" Property="Foreground" Value="Red"/>

</Trigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.MenuButtonTemplate>

<ContentControl syncfusion:DockingManager.Header="Child1"/>

<ContentControl syncfusion:DockingManager.Header="Child2"/>

</syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img16.jpeg)


### MinimizeButton Template

The minimize button for the dock window can be customized using the `MinimizeButtonTemplate` by setting with the TargetType as `ToggleButton`.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" MinimizeButtonEnabled="True" >

<syncfusion:DockingManager.MinimizeButtonTemplate>

<ControlTemplate TargetType="{x:Type ToggleButton}">

<Border x:Name="Border1">

<TextBlock x:Name="Block" Background="Red" Text="mini" ></TextBlock>

</Border>

<ControlTemplate.Triggers>

<Trigger Property="IsMouseOver" Value="True">

<Setter TargetName="Border1" Property="Background" Value="Black"></Setter>

</Trigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.MinimizeButtonTemplate>

<ContentControl syncfusion:DockingManager.Header="Child1"/>

<ContentControl syncfusion:DockingManager.Header="Child2"/>

</syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img17.jpeg)


### MaximizeButtonTemplate

The maximize button for the dock window can be customized using the `MaximizeButtonTemplate` property with the TargetType as `ToggleButton`.

{% highlight xaml %}


<syncfusion:DockingManager  x:Name="DockingManager1" MaximizeButtonEnabled="True" MinimizeButtonEnabled="True" >

<syncfusion:DockingManager.MaximizeButtonTemplate>

<ControlTemplate TargetType="{x:Type ToggleButton}">

<Border x:Name="Border1">

<TextBlock x:Name="Block" Background="Red" Text="Maxi"/>

</Border>

<ControlTemplate.Triggers>

<Trigger Property="IsMouseOver" Value="True">

<Setter TargetName="Border1" Property="Background" Value="Black"/>

</Trigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.MaximizeButtonTemplate>

<ContentControl syncfusion:DockingManager.Header="Child1"/>

<ContentControl syncfusion:DockingManager.Header="Child2"/>

</syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img18.jpeg)


### RestoreButtonTemplate 

The Restore button for the dock window can be customized using the `RestoreButtonTemplate` property with the TargetType as `ToggleButton`.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" MaximizeButtonEnabled="True">

<syncfusion:DockingManager.RestoreButtonTemplate>

<ControlTemplate TargetType="{x:Type ToggleButton}">

<Border x:Name="Border1">

<TextBlock x:Name="text1" Background="Red" Text="Maxim"/>

</Border>

<ControlTemplate.Triggers>

<Trigger Property="IsMouseOver" Value="True">

<Setter TargetName="Border1" Property="Background" Value="Black"></Setter>

</Trigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.RestoreButtonTemplate>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Dock"/>

<ContentControl syncfusion:DockingManager.Header="Child2" syncfusion:DockingManager.State="Dock"/>
 
<ContentControl syncfusion:DockingManager.Header="Child3" syncfusion:DockingManager.State="Dock"/>

<ContentControl syncfusion:DockingManager.Header="Child4" syncfusion:DockingManager.State="Dock"/>

<ContentControl syncfusion:DockingManager.Header="Child5" syncfusion:DockingManager.State="Dock"/>

</syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img19.jpeg)


### TabItemTemplate

DockedElementTabbedHost have internal TabControl for Tabbed Windows in DockingManager and its tabitem template can be customized using `TabItemTemplate` with the TargetType as `TabItem`.


{% highlight xaml %}

<Window.Resources>

<Style x:Key="TabItemStyle1" TargetType="{x:Type TabItem}" >

<Setter Property="Header" Value="{Binding Path=(Syncfusion:DockingManager.Header)}" />

<Setter Property="Syncfusion:DockingManager.ListenTabItemEvents" Value="True" />

<Setter Property="MinWidth" Value="21" />

<Setter Property="MinHeight" Value="21" />

<Setter Property="SnapsToDevicePixels" Value="True" />

<Setter Property="Tag" Value="IsInternalTabItem" />

<Setter Property="Template">

<Setter.Value>

<ControlTemplate TargetType="{x:Type TabItem}">

<Grid Name="Transform">

<Syncfusion:ContextMenuBorder Name="Border" Background="{TemplateBinding Background}"
	                          BorderBrush="{TemplateBinding BorderBrush}"BorderThickness="1">

<Border.ContextMenu>

<Syncfusion:CustomContextMenu Name="PART_ContextMenu"  Focusable="false"  />

</Border.ContextMenu>

<Border.LayoutTransform>

<RotateTransform Angle="0" />

</Border.LayoutTransform>

<DockPanel LastChildFill="True" Background="Red">

<Border Name="Icon" DockPanel.Dock="Left" Margin="1" Width="16"
        Background="{Binding Path=(TabItem.Content).(Syncfusion:DockingManager.Icon), RelativeSource={RelativeSource TemplatedParent}}" />

<ContentPresenter x:Name="ContentSite" VerticalAlignment="Center" HorizontalAlignment="Center"
    ContentSource="Header" Margin="2,2,2,2" RecognizesAccessKey="True"
	ContentTemplate="{Binding Path=(TabItem.Content).(Syncfusion:DockingManager.HeaderTemplate), RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type TabItem}}}"/>

</DockPanel>

</Syncfusion:ContextMenuBorder>

</Grid>

</ControlTemplate>

</Setter.Value>

</Setter>

</Style>

</Window.Resources>

<Grid x:Name="Grid1">

<Syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" TabItemStyle="{StaticResource TabItemStyle1}">

<ContentControl Syncfusion:DockingManager.Header="Window1" x:Name="Content1" Syncfusion:DockingManager.State="Dock"/>

<ContentControl Syncfusion:DockingManager.Header="Window2" Syncfusion:DockingManager.State="Dock" x:Name="Content2" 
                Syncfusion:DockingManager.TargetNameInDockedMode="Content1" Syncfusion:DockingManager.SideInDockedMode="Tabbed"/>

</Syncfusion:DockingManager>

</Grid>

</Window>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img20.jpeg)


### DockedElementTabbedHostStyle

The DockedElementTabbedHost can be customized using the DockedElementTabbedHostStyle with the TargetType as DockedElementTabbedHost

{% highlight xaml %}

<Syncfusion:DockingManager.DockedElementTabbedHostStyle>

<Style TargetType="{x:Type Syncfusion:DockedElementTabbedHost}">

<Setter Property="Syncfusion:DockingManager.InternalDataContext"
        Value="{Binding Path=(Syncfusion:DockedElementTabbedHost.HostedElement), RelativeSource={RelativeSource Self}}"/>

<Setter Property="FocusVisualStyle" 
	    Value="{Binding Path=(Syncfusion:DockedElementTabbedHost.DockingManager).(Syncfusion:DockingManager.FocusVisualStyle),
		RelativeSource={RelativeSource TemplatedParent}}"/>

<Setter Property="Template">

<Setter.Value>

<ControlTemplate TargetType="{x:Type Syncfusion:DockedElementTabbedHost}">

<Border x:Name="BorderWrap" Width="Auto" 
	    FocusVisualStyle="{Binding Path=(Syncfusion:DockedElementTabbedHost.DockingManager).(Syncfusion:DockingManager.FocusVisualStyle),
        RelativeSource={RelativeSource TemplatedParent}}" SnapsToDevicePixels="True" BorderBrush="{TemplateBinding BorderBrush}" 
		Background="Pink" BorderThickness="1">

<DockPanel x:Name="DockPanel" Width="Auto" LastChildFill="True" Focusable="False">

<Syncfusion:DockHeaderPresenter x:Name="header"DockPanel.Dock="Top" RenderTransformOrigin="0.5,0.5"
            Style="{Binding Path=(Syncfusion:DockedElementTabbedHost.DockingManager).(Syncfusion:DockingManager.DockHeaderStyle),
			RelativeSource={RelativeSource AncestorType={x:Type Syncfusion:DockedElementTabbedHost}}}"
            IsTemplateParenKeyboardFocusWithin="{TemplateBinding IsKeyboardFocusWithin}"/>

<Grid>

<ContentPresenter Name="HostedElement" ClipToBounds="True" ContentSource="HostedElement"
                  ContentTemplate="{TemplateBinding ContentControl.ContentTemplate}"
                  ContentTemplateSelector="{TemplateBinding ContentControl.ContentTemplateSelector}"/>

<Border Name="PART_CoverletControl" Visibility="Collapsed" Background="Transparent" />

</Grid>

</DockPanel>

</Border>

</ControlTemplate>

</Setter.Value>

</Setter>

</Style>

</Syncfusion:DockingManager.DockedElementTabbedHostStyle>


{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img21.jpeg)


### DockHeaderStyle

The header of the dock window can be customized using the property `DockHeaderStyle` with the TargetType as DockHeaderPresenter.

{% highlight xaml %}
<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True"   >

<syncfusion:DockingManager.DockHeaderStyle>

<Style TargetType="{x:Type syncfusion:DockHeaderPresenter}">

<Setter Property="MinHeight" Value="60"></Setter>

</Style>

</syncfusion:DockingManager.DockHeaderStyle>

<ContentControl x:Name="Content1"  syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.Header="Child1" />

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Child2" />

</syncfusion:DockingManager>

{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img22.jpeg)


### DockWindowContextMenuItemStyle


The context menu of DockingManager can be customized using the DockWindowContextMenuItemStyle by setting its Target Type as `CustomMenuItem`



{% highlight xaml %}

<Syncfusion:DockingManager UseDocumentContainer="True" ContainerMode="TDI" UseNativeFloatWindow="True">

<Syncfusion:DockingManager.DockWindowContextMenuItemStyle>

<Style TargetType="{x:Type Syncfusion:CustomMenuItem}">

<Setter Property="Foreground" Value="Red"></Setter>

</Style>

</Syncfusion:DockingManager.DockWindowContextMenuItemStyle>

<Syncfusion:DockingManager.CustomMenuItems>

<Syncfusion:CustomMenuItemCollection>

<Syncfusion:CustomMenuItem Header="CustomItem1"/>

<Syncfusion:CustomMenuItem Header="CustomItem2"/>

</Syncfusion:CustomMenuItemCollection>

</Syncfusion:DockingManager.CustomMenuItems>

<ContentControl Syncfusion:DockingManager.Header="Child1" Syncfusion:DockingManager.State="Dock"/>

<ContentControl Syncfusion:DockingManager.Header="Child2" Syncfusion:DockingManager.State="Dock"/>

<ContentControl Syncfusion:DockingManager.Header="Child3" Syncfusion:DockingManager.State="Dock"/>

</Syncfusion:DockingManager>

{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img23.jpeg)


## Float Window Style

The float window can be customized using its template and style.

### FloatWindowTemplate 

Template of FloatWindow can be customized using the `FloatWindowTemplate` with the TargetType as ContentControl.

{% highlight xml %}

<Syncfusion:DockingManager UseDocumentContainer="True" ContainerMode="TDI"  EnableDocumentTabHeaderEdit="True">

<Syncfusion:DockingManager.FloatWindowTemplate>

<ControlTemplate  TargetType="{x:Type ContentControl}">

<AdornerDecorator>

<DockPanel Focusable="False" LastChildFill="True" Opacity="{Binding Path=Opacity,
	       RelativeSource={RelativeSource AncestorType={x:Type Syncfusion:IWindow}}}">

<Border Name="FloatWindowOutBorder"  Focusable="False" BorderBrush="{TemplateBinding BorderBrush}" 
	    BorderThickness="{TemplateBinding BorderThickness}" Background="Red" >

<Grid Focusable="False">

<Grid.RowDefinitions>

<RowDefinition Name="TopRow"/>

<RowDefinition Height="*" />

<RowDefinition Name="BottomRow" Height="7" />

</Grid.RowDefinitions>

<Grid.ColumnDefinitions>

<ColumnDefinition Name="LeftCol" Width="7" />

<ColumnDefinition Width="*"/>

<ColumnDefinition Name="RightCol" Width="7" />

</Grid.ColumnDefinitions>

<Syncfusion:FloatWindowBorder BorderMode="LeftTop" Name="BorderLeftTop" Grid.Column="0" Grid.Row="0" />

<Syncfusion:FloatWindowBorder BorderMode="Header" Name="BorderHeader" Grid.Column="1" Grid.Row="0" />

<Syncfusion:FloatWindowBorder BorderMode="RightTop" Name="BorderRightTop" Grid.Column="2" Grid.Row="0" />

<Syncfusion:FloatWindowBorder BorderMode="Left" Name="BorderLeft" Grid.Column="0" Grid.Row="1" />

<ContentPresenter Name="ContentPresenter" Grid.Column="1" Grid.Row="1" ContentTemplate="{TemplateBinding ContentControl.ContentTemplate}"
	              Content="{TemplateBinding ContentControl.Content}" />

<Syncfusion:FloatWindowBorder BorderMode="Right" Name="BorderRight" Grid.Column="2" Grid.Row="1" />

<Syncfusion:FloatWindowBorder BorderMode="LeftBottom" Name="BorderLeftBottom" Grid.Column="0" Grid.Row="2" />

<Syncfusion:FloatWindowBorder BorderMode="Bottom" Name="BorderBottom" Grid.Column="1" Grid.Row="2" />

<Syncfusion:FloatWindowBorder BorderMode="RightBottom" Name="BorderRightBottom" Grid.Column="2" Grid.Row="2" />

</Grid>

</Border>

</DockPanel>

</AdornerDecorator>

</ControlTemplate>

</Syncfusion:DockingManager.FloatWindowTemplate>

<ContentControl Syncfusion:DockingManager.Header="Child1" Syncfusion:DockingManager.State="Float"/>

<ContentControl Syncfusion:DockingManager.Header="Child2" Syncfusion:DockingManager.State="Document"/>

<ContentControl Syncfusion:DockingManager.Header="Child3" Syncfusion:DockingManager.State="Document"/>

</Syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img24.jpeg)


### FloatWindowStyle

The style for the float window can be applied using the `FloatWindowStyle` property of the DockingManager by setting its TargetType as `AutoTemplatedContentControl`. It gets or sets the style for the floatwindow when it is rendered.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1">
	
	<syncfusion:DockingManager.FloatWindowStyle>
	
	<Style TargetType="{x:Type syncfusion:AutoTemplatedContentControl}">
	<Setter Property="Background" Value="Red"></Setter>
	</Style>	
	
	</syncfusion:DockingManager.FloatWindowStyle>
	
	<ContentControl syncfusion:DockingManager.Header="Child" 
	                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.SideInDockedMode="Left"/>
					
	<ContentControl syncfusion:DockingManager.Header="Child2"></ContentControl>
	
</syncfusion:DockingManager>

{% endhighlight %}

### NativeWindowStyle

The NativeFloatwindow of DockingManager can be customized using the `NativeWindowStyle` property of the DockingManager with the TargetType as NativeFloatWindow.

{% highlight xaml %}

<Syncfusion:DockingManager UseDocumentContainer="True" ContainerMode="TDI" UseNativeFloatWindow="True">

<Syncfusion:DockingManager.NativeWindowStyle>

<Style TargetType="{x:Type Syncfusion:NativeFloatWindow}">

<Setter Property="Background" Value="Red"></Setter>

</Style>

</Syncfusion:DockingManager.NativeWindowStyle>

<ContentControl Syncfusion:DockingManager.Header="Child1" Syncfusion:DockingManager.State="Float"/>

<ContentControl Syncfusion:DockingManager.Header="Child2" Syncfusion:DockingManager.State="Document"/>

<ContentControl Syncfusion:DockingManager.Header="Child3" Syncfusion:DockingManager.State="Document"/>

</Syncfusion:DockingManager>



{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img25.jpeg)


## Auto Hide Window Style

AutoHidden window is constructed by SidePanels and SideTabItems. To customize the AutoHidden window, the following  style and Templates are used as follows:

### SideTabItemTemplate

The template of the SideTabItem of the DockingManager can be customized using the `SideTabItemTemplate` with the TargetType as TabItem.


{% highlight xaml %}

<ControlTemplate x:Key="SideTabItemTemplate" TargetType="{x:Type TabItem}">

<Border Name="Border" CornerRadius="5,5,0,0"
        BorderBrush="{StaticResource TabItemBorderBrush}" BorderThickness="1">

<Border.LayoutTransform>

<RotateTransform Angle="90" />

</Border.LayoutTransform>

<Grid>

<DockPanel LastChildFill="True" Background="Orange">

<Rectangle Fill="Transparent"  Height="Auto" Width="Auto" RadiusX="5" RadiusY="5" />

<Border Name="Icon" DockPanel.Dock="Left" Margin="1" Width="16"
        Background="{Binding Path=(TabItem.Content).(Syncfusion:DockingManager.Icon), 
		RelativeSource={RelativeSource TemplatedParent}}" />

<ContentPresenter x:Name="ContentSite" VerticalAlignment="Center" HorizontalAlignment="Center" 
	    ContentSource="Header" Margin="2,2,2,2" RecognizesAccessKey="True"
        ContentTemplate="{Binding Path=(Border.DataContext).(Syncfusion:DockingManager.HeaderTemplate), ElementName=Border}"
		ContentTemplateSelector="{StaticResource TabItemTrimmingTemplate}" TextBlock.Foreground="{StaticResource Default.TabForeground}"/>

</DockPanel>

</Grid>

</Border>

</ControlTemplate>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img26.jpeg)


### SideItemStyle

The style for the sideTabItem can be changed using `SideItemStyle`, by settings its TargetType as TabItem

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True" ContainerMode="TDI" >

<syncfusion:DockingManager.SideItemStyle>

<Style TargetType="{x:Type TabItem}">

<Setter Property="Background" Value="Red"></Setter>

<Setter Property="MinHeight" Value="500"></Setter>

<Setter Property="MinWidth" Value="200"></Setter>

</Style>

</syncfusion:DockingManager.SideItemStyle>

<ContentControl x:Name="content1" 

syncfusion:DockingManager.Header="Child1"

syncfusion:DockingManager.State="Dock"/>

<ContentControl x:Name="content2" syncfusion:DockingManager.Header="Child2"

syncfusion:DockingManager.State="AutoHidden"/>

<ContentControl x:Name="content3" syncfusion:DockingManager.Header="Child3"

syncfusion:DockingManager.State="Dock"></ContentControl>

</syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img27.jpeg)


### SidePanelTemplate

SidePanel template in AutoHidden window can changed using `SidePanelTemplate` with the TargetType SidePanel.

{% highlight xml %}

<ControlTemplate x:Key="SidePanelTemplate" TargetType="{x:Type Syncfusion:SidePanel}" >
	
<Canvas KeyboardNavigation.TabNavigation="Local" ClipToBounds="False" >
	
<Border Name="PART_BorderName"  Height="{TemplateBinding ActualHeight}" Width="{TemplateBinding ActualWidth}"
        Margin="0" ClipToBounds="True" Background="Orange"Panel.ZIndex="1" KeyboardNavigation.TabIndex="1"
        BorderThickness="{Binding Path=SidePanelBorderThickness, RelativeSource={RelativeSource FindAncestor, 
		AncestorType={x:Type Syncfusion:DockingManager}}}" BorderBrush="{StaticResource TabItemBorderBrush}">

<Border.ContextMenu>
<ContextMenu Style="{StaticResource SideContextMenuStyle}" ItemsSource="{TemplateBinding TabChildren}"/>
</Border.ContextMenu>

<Syncfusion:DirectTabPanel Name="PART_PanelName" KeyboardNavigation.TabNavigation="Local" IsItemsHost="True"/>

</Border>

<Syncfusion:OpacityDockPanel LastChildFill="True" Opacity="{Binding Path=ContentOpacity, RelativeSource={RelativeSource TemplatedParent}}"/>
</ Canvas >
</ControlTemplate>

{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img28.jpeg)


###  SidePanelStyle

The style for the sidepanel of the DockingManager can be customized using the `SidePanelStyle` property with the TargetType as SidePanel.

{% highlight xml%}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True" ContainerMode="TDI">
	
<syncfusion:DockingManager.SidePanelStyle>
	
<Style TargetType="{x:Type syncfusion:SidePanel}">
	
<Setter Property="Background" Value="Red"></Setter>

</Style>
	  
</syncfusion:DockingManager.SidePanelStyle>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="AutoHidden"/> 
<ContentControl syncfusion:DockingManager.Header="Child2"syncfusion:DockingManager.State="Document"/>
<ContentControl syncfusion:DockingManager.Header="Child3"syncfusion:DockingManager.State="Document"/> 
	
</syncfusion:DockingManager>

{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img29.jpeg)

## Drag Provider Style

DragProviders are those that appear while dragging a window. It allows you to drag the window to the left, right, top and bottom using the respective drag providers.

DragProviders are displayed for providing options to dock the floatwindow while dragging and this drag provider button templates can be changed by the following templates.

### BottomDragProvider

The BottomDragProvider is used to dock the children of the Docking in the bottom side and it’s template can be customized using the `BottomDragProviderTemplate` by setting its TargetType as ContentControl.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True" EnableDocumentTabHeaderEdit="True" >

<syncfusion:DockingManager.BottomDragProvider>

<ControlTemplate TargetType="{x:Type ContentControl}">

<Image Name="Img" syncfusion:DockPreviewManagerVS2005.ProviderAction="GlobalLeft" Source="Images\synclogo.png" />

<ControlTemplate.Triggers>

<DataTrigger Binding="{Binding Path=IsSideButtonActive, 
	        RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:DockPreviewMainButtonVS2005}}}" Value="true">

<Setter TargetName="Img" Property="Source" Value="Images\synclogo.png"/>

</DataTrigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.BottomDragProvider>

<ContentControlsyncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Dock"/>

</syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img30.jpeg)


### LeftDragProvider

The LeftDragProvider is used to dock the dock window to the left side and it can be customized using the `LeftDragProvider` property that helps to customize the template for the Left DragProvider by setting its Target as ContentControl. The same has been explained below:

{% highlight xaml %}
<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True" EnableDocumentTabHeaderEdit="True" >

<syncfusion:DockingManager.LeftDragProvider>

<ControlTemplate TargetType="{x:Type ContentControl}">

<Image Name="Img" syncfusion:DockPreviewManagerVS2005.ProviderAction="GlobalLeft" Source="Images\synclogo.png" />

<ControlTemplate.Triggers>

<DataTrigger Binding="{Binding Path=IsSideButtonActive, 
	RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:DockPreviewMainButtonVS2005}}}" Value="true">

<Setter TargetName="Img" Property="Source" Value="Images\synclogo.png"/>

</DataTrigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.LeftDragProvider>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Dock"/>

</syncfusion:DockingManager> 





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img31.jpeg)


### RightDragProvider

To dock the DockingManager to the right side, the RightDragProvider is used and it can be customized using the `RightDragProviderTemplate` with the TargetType as ContentControl.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True" EnableDocumentTabHeaderEdit="True" >

<syncfusion:DockingManager.RightDragProvider>

<ControlTemplate TargetType="{x:Type ContentControl}">

<Image Name="Img" syncfusion:DockPreviewManagerVS2005.ProviderAction="GlobalLeft" Source="Images\synclogo.png" />

<ControlTemplate.Triggers>

<DataTrigger Binding="{Binding Path=IsSideButtonActive, 
	RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:DockPreviewMainButtonVS2005}}}" Value="true">

<Setter TargetName="Img" Property="Source" Value="Images\synclogo.png"/>

</DataTrigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.RightDragProvider>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Dock"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img32.jpeg)


### TopDragProvider

To dock the DockingManager at the top, the TopDragProvider is used and it can be customized using the `TopDragProviderTemplate` with the TargetType as ContentControl.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True" EnableDocumentTabHeaderEdit="True" >

<syncfusion:DockingManager.LeftDragProvider>

<ControlTemplate TargetType="{x:Type ContentControl}">

<Image Name="Img" syncfusion:DockPreviewManagerVS2005.ProviderAction="GlobalLeft" Source="Images\synclogo.png" />

<ControlTemplate.Triggers>

<DataTrigger Binding="{Binding Path=IsSideButtonActive, 
	RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:DockPreviewMainButtonVS2005}}}" Value="true">

<Setter TargetName="Img" Property="Source" Value="Images\synclogo.png"/>

</DataTrigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.LeftDragProvider>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Dock"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img33.jpeg)


### CenterDragProvider

CenterDragProvider is used to dock the children of the DockingManager at the center Position and its template can be customized using the property CenterDragProvider.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True">            
	
<syncfusion:DockingManager.CenterDragProvider>

<ControlTemplate TargetType="{x:Type ContentControl}">

<Image Name="Img" syncfusion:DockPreviewManagerVS2005.ProviderAction="GlobalLeft" Source="Images\synclogo.png" />

<ControlTemplate.Triggers>

<DataTrigger Binding="{Binding Path=IsSideButtonActive, 
	RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:DockPreviewMainButtonVS2005}}}" Value="true">

<Setter TargetName="Img" Property="Source" Value="Images\synclogo.png"/>

</DataTrigger>

</ControlTemplate.Triggers>

</ControlTemplate>

</syncfusion:DockingManager.CenterDragProvider>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Dock"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img34.jpeg)


## DocumentTabControlStyle

Document state in DockingManager used the DocumentTabControl. To customize the Document in the DockingManager the `DocumentTabControlStyle` property is used by setting its TargetType as DocumentTabControl.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True">

<syncfusion:DockingManager.DocumentTabControlStyle>

<Style TargetType="{x:Type syncfusion:DocumentTabControl}">

<Setter Property="TabItemSelectedBackground" Value="Red" />

</Style>

</syncfusion:DockingManager.DocumentTabControlStyle>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Document"/>

<ContentControl syncfusion:DockingManager.Header="Child2" syncfusion:DockingManager.State="Document"/>

<ContentControl syncfusion:DockingManager.Header="Child3" syncfusion:DockingManager.State="Document"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img35.jpeg)


## DocumentTabItemStyle

Each Document TabItem in DockingManager constructed by the TabItemExt and its style can be customized using `DocumentTabItemStyle` with the TargetType as TabItemExt.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True"   >

<syncfusion:DockingManager.DocumentTabItemStyle>

<Style TargetType="{x:Type syncfusion:TabItemExt}">

<Setter Property="BorderBrush" Value="Red" />

</Style>

</syncfusion:DockingManager.DocumentTabItemStyle>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Document"/>

<ContentControl syncfusion:DockingManager.Header="Child2" syncfusion:DockingManager.State="Document"/>

<ContentControl syncfusion:DockingManager.Header="Child3" syncfusion:DockingManager.State="Document"/> 
	
</syncfusion:DockingManager>


{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img36.jpeg)


## DocumentMDIHeaderStyle

The header style for the Document MDI can be changed using the `DocumentMDIHeaderStyle` with the TargetType as DocumentHeader.

{% highlight xaml %}

<syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True" ContainerMode="MDI">
	
<syncfusion:DockingManager.DocumentMDIHeaderStyle>
	
<Style TargetType="{x:Type syncfusion:DocumentHeader}">
	
<Setter Property="Background" Value="Maroon"></Setter><Setter Property="Foreground" Value="White"/>
	
<Setter Property="HeaderTemplate">
	
<Setter.Value>
	
<DataTemplate >
<TextBlock x:Name="Block" Text="Text1" />
</DataTemplate>

</Setter.Value>

</Setter>

</Style>

</syncfusion:DockingManager.DocumentMDIHeaderStyle>

<ContentControl syncfusion:DockingManager.Header="Child1" syncfusion:DockingManager.State="Document"/>
<ContentControl syncfusion:DockingManager.Header="Child2" syncfusion:DockingManager.State="Document"/>
<ContentControl syncfusion:DockingManager.Header="Child3" syncfusion:DockingManager.State="Document"/>
	
</syncfusion:DockingManager>


{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img37.jpeg)


## TabControl style

Tabcontrol inside the DockWindow for Tabbed side Windows can be customized using `TabControlStyle` with the TargetType as TabControl in the DockingManager

{% highlight xaml %}

<Syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True"   >

<Syncfusion:DockingManager.TabControlStyle>

<Style TargetType="{x:Type TabControl}">

<Setter Property="Background" Value="Orange" />       

<Setter Property="ItemContainerStyle" Value="{Binding Path=(Syncfusion:DockedElementTabbedHost.DockingManager).
	    (Syncfusion:DockingManager.TabItemStyle), 
		RelativeSource={RelativeSource  AncestorType={x:Type Syncfusion:DockedElementTabbedHost}}}" />

</Style>

</Syncfusion:DockingManager.TabControlStyle>

<ContentControl Syncfusion:DockingManager.State="Dock" Syncfusion:DockingManager.Header="Child1" />

<ContentControl Syncfusion:DockingManager.Header="Child2" Syncfusion:DockingManager.SideInDockedMode="Tabbed"
	              Syncfusion:DockingManager.TargetNameInDockedMode="Content1">
</ContentControl>

</Syncfusion:DockingManager>





{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img38.jpeg)


### TabItemStyle

The style for the Tabbed children of DockingManager can be customized using the `TabItemStyle` property with the Target Type as TabItem.

{% highlight xaml %}

<Syncfusion:DockingManager  x:Name="DockingManager1" UseDocumentContainer="True">   
	
<Syncfusion:DockingManager.TabItemStyle>

<Style TargetType="{x:Type TabItem}">

<Setter Property="Background" Value="Maroon"/>

<Setter Property="Header" Value="{Binding Path=(Syncfusion:DockingManager.Header)}" />

</Style>

</Syncfusion:DockingManager.TabItemStyle>

<ContentControl Syncfusion:DockingManager.State="Dock" x:Name="Content1" Syncfusion:DockingManager.Header="Child1"/>

<ContentControl Syncfusion:DockingManager.Header="Child2"
	            Syncfusion:DockingManager.SideInDockedMode="Tabbed" Syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>

</Syncfusion:DockingManager>

{% endhighlight %}

![](StylingandTemplates_images/StylingandTemplates_img39.jpeg)


