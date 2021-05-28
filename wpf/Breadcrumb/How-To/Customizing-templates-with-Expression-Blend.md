---
layout: post
title: Customizing templates with Expression Blend| Hierarchical Navigator | Wpf | Syncfusion
description: customizing templates with expression blend
platform: wpf
control: Hierarchical Navigator
 documentation: ug
---

## Customizing templates with Expression Blend

The steps to customize templates by using Expression Blend are as follows:

1. Create a new application in Expression Blend. Refer Creating a HierarchyNavigator control by using Expression Blend.

   The following are the default resources, which are used for HierarchyNavigator control that can be changed in Expression Blend.

   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img1.png)



2. Right-click the HierarchyNavigator control and select Edit, then select Style, and type a name.

   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img2.png)



3. Right-click the HierarchyNavigatorItemsControl and select Edit, then select Template, and then select Edit a Copy, to edit the Refresh button, the History button, or the overall content. Additional styles (templates) can be used to edit a template available in the HierarchyNavigatorItemsControl class.

   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img3.png)



4. Right-click the Part_HierarchyNavigatorItemsControl and select Edit, and then select Additional Templates. A list of additional styles to edit will be displayed. Figure 40 displays the style names.

   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img4.png)



   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img5.png)



5. Storyboards used in the VisualStateManager of every control are easy to customize and manage. 
6. For example, the HierarchyNavigatorItem control has two states: Normal and MouseOver. This is available on the States window, which can be accessed by clicking the Window menu and selecting States.


   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img6.png)



7. Click the Visual State name, to edit the storyboard.

   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img7.png)



   
#### Customized sample styles

The steps to customize sample styles are as follows:

1. Add a HierarchyNavigator control to the new sample project
2. Add items. Refer Adding items to the HierarchyNavigator control.

   ~~~xaml
   
      xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Tools.Controls;
	  assembly=Syncfusion.Tools.Silverlight"

       <syncfusion:HierarchyNavigator x:Name="hierarchyNavigator1" 
	    Width="500" 
		VerticalAlignment="Center" 
		Style="{DynamicResource HierarchyNavigatorStyle1}">  
		<syncfusion:HierarchyNavigator.Items>     
		<syncfusion:HierarchyNavigatorItem Content="Syncfusion">
		<syncfusion:HierarchyNavigatorItem.Items>
		<syncfusion:HierarchyNavigatorItem Content="Silverlight">
		<syncfusion:HierarchyNavigatorItem.Items>
		<syncfusion:HierarchyNavigatorItem Content="Tools"/>
		<syncfusion:HierarchyNavigatorItem Content="Grid"/>
		<syncfusion:HierarchyNavigatorItem Content="Chart"/>
		<syncfusion:HierarchyNavigatorItem Content="Gauge"/>
		<syncfusion:HierarchyNavigatorItem Content="Edit"/>
		<syncfusion:HierarchyNavigatorItem Content="Schedule"/>
		</syncfusion:HierarchyNavigatorItem.Items>           
		</syncfusion:HierarchyNavigatorItem>
		<syncfusion:HierarchyNavigatorItem Content="WPF"/>     
		</syncfusion:HierarchyNavigatorItem.Items>  
		</syncfusion:HierarchyNavigatorItem>   
		</syncfusion:HierarchyNavigator.Items>
		</syncfusion:HierarchyNavigator>

   ~~~

      ItemContainerStyle has been changed for the HierarchyNavigator control.

      To steps to edit the styles are as follows:

3. Right-click the HierarchyNavigator control and select Edit Template, then select Edit Copy and type specify the style name for the HierarchyNavigator control. Then, edit the template as you require. 

   The following XAML is used for the HierarchyNavigator control’s main style. 

4. Right-click the PART_HierarchyNavigatorItemsControl and select Edit Additional Templates, then select Edit Generated Item Container (ItemContainerStyle), and select Edit a Copy, to edit the item-container style.

   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img8.png)



5. In the Create Style Resource dialog box, type the style name.

   ![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img9.png)



#### Sample XAML for ItemContainerStyle

The XAML displayed below is used to customize the item-container style.



{% highlight xaml %}

<Style x:Key="HierarchyNavigatorStyle1" TargetType="{x:Type syncfusion:HierarchyNavigator}">
<Setter Property="BorderBrush" Value="Black"/>
<Setter Property="Background">
<Setter.Value>
<SolidColorBrush Color="#FFEDF6FE" Opacity="0.5"/>
</Setter.Value>
</Setter>
<Setter Property="BorderThickness" Value="0.5"/>
<Setter Property="Template">

<Setter.Value>
<ControlTemplate TargetType="{x:Type syncfusion:HierarchyNavigator}">
<Grid x:Name="PART_Root" Background="{TemplateBinding Background}">
<VisualStateManager.VisualStateGroups>
<VisualStateGroup x:Name="CommonStates">
<VisualState x:Name="NormalProgress">
<Storyboard>
<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)" Storyboard.TargetName="PART_ProgressBar">
<SplineDoubleKeyFrame KeyTime="0" Value="0"/>
</DoubleAnimationUsingKeyFrames>
<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="PART_ProgressBar">
<SplineDoubleKeyFrame KeyTime="0" Value="0"/>
</DoubleAnimationUsingKeyFrames>
</Storyboard>
</VisualState>

<VisualState x:Name="ShowProgress">
<Storyboard>
<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)" Storyboard.TargetName="PART_ProgressBar">
<SplineDoubleKeyFrame KeyTime="0" Value="0"/>
<SplineDoubleKeyFrame KeyTime="0:0:0.5" Value="1"/>
<SplineDoubleKeyFrame KeyTime="0:0:0.6" Value="1"/>
<SplineDoubleKeyFrame KeyTime="0:0:0.7" Value="0"/>
</DoubleAnimationUsingKeyFrames>
<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="PART_ProgressBar">
<SplineDoubleKeyFrame KeyTime="0" Value="0.8"/>
<SplineDoubleKeyFrame KeyTime="0:0:0.5" Value="0.8"/>
<SplineDoubleKeyFrame KeyTime="0:0:0.6" Value="0"/>
</DoubleAnimationUsingKeyFrames>
</Storyboard>
</VisualState>
</VisualStateGroup>
</VisualStateManager.VisualStateGroups>

<syncfusion:HierarchyNavigatorItemsControl x:Name="PART_HierarchyNavigatorItemsControl" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}" CornerRadius="{TemplateBinding CornerRadius}" MinHeight="30" Opacity="{TemplateBinding Opacity}">
<syncfusion:HierarchyNavigatorItemsControl.ItemContainerStyle>
<Style TargetType="{x:Type syncfusion:HierarchyNavigatorBarContent}">
<Setter Property="Template">
<Setter.Value>
<ControlTemplate TargetType="{x:Type syncfusion:HierarchyNavigatorBarContent}">

<Grid x:Name="PART_Root" Background="Transparent" Opacity="{TemplateBinding Opacity}">

<VisualStateManager.VisualStateGroups>
<VisualStateGroup x:Name="CommonStates">
<VisualState x:Name="Normal">
<Storyboard/>
</VisualState>
<VisualState x:Name="Open">
<Storyboard>
<DoubleAnimationUsingKeyFrames BeginTime="0" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)" Storyboard.TargetName="PART_PopUpBorder">
<SplineDoubleKeyFrame KeyTime="0:0:0.3" Value="1"/>
</DoubleAnimationUsingKeyFrames>
<DoubleAnimationUsingKeyFrames BeginTime="0" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)" Storyboard.TargetName="PART_PopUpBorder">
<SplineDoubleKeyFrame KeyTime="0:0:0.3" Value="1"/>
</DoubleAnimationUsingKeyFrames>
<DoubleAnimationUsingKeyFrames BeginTime="0" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[2].(RotateTransform.Angle)" Storyboard.TargetName="PART_path">
<SplineDoubleKeyFrame KeyTime="0" Value="0"/>
<SplineDoubleKeyFrame KeyTime="0:0:0.3" Value="90"/>
</DoubleAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="BorderBrush" Storyboard.TargetName="PART_NavigationButton">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<SolidColorBrush Color="#FF31658D"/>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background" Storyboard.TargetName="PART_OuterBorder">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FF596E7A" Offset="0"/>
<GradientStop Color="#FF6D8D9F" Offset="0.006"/>
<GradientStop Color="#FF6D8D9F" Offset="0.026"/>
<GradientStop Color="#FFA6C7D9" Offset="0.041"/>
<GradientStop Color="#FFA6C7D9" Offset="0.072"/>
<GradientStop Color="#FFC2E4F6" Offset="0.087"/>
<GradientStop Color="#FFC2E4F6" Offset="0.41"/>
<GradientStop Color="#FFA9D9F2" Offset="0.425"/>
<GradientStop Color="#FF90CBEB" Offset="0.991"/>
<GradientStop Color="#FF7D96A7" Offset="1"/>
</LinearGradientBrush>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_LeftLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_FirstLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_RightLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
</Storyboard>
</VisualState>
<VisualState x:Name="Close">
<Storyboard>
<DoubleAnimationUsingKeyFrames BeginTime="0" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)" Storyboard.TargetName="PART_PopUpBorder">
<SplineDoubleKeyFrame KeyTime="0:0:0.3" Value="0"/>
</DoubleAnimationUsingKeyFrames>
<DoubleAnimationUsingKeyFrames BeginTime="0" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)" Storyboard.TargetName="PART_PopUpBorder">
<SplineDoubleKeyFrame KeyTime="0:0:0.3" Value="0"/>
</DoubleAnimationUsingKeyFrames>
</Storyboard>
</VisualState>
<VisualState x:Name="MouseOver">
<Storyboard>
<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background" Storyboard.TargetName="PART_NavigationButton">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FFF8FCFD" Offset="0"/>
<GradientStop Color="#FFD8F0FC" Offset="0.383"/>
<GradientStop Color="#FFBDE6FD" Offset="0.438"/>
<GradientStop Color="#FFA7DAF5" Offset="0.956"/>
<GradientStop Color="#FFE0F2FB" Offset="1"/>
</LinearGradientBrush>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background" Storyboard.TargetName="PART_OuterBorder">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FFF8FCFD" Offset="0"/>
<GradientStop Color="#FFD8F0FC" Offset="0.383"/>
<GradientStop Color="#FFBDE6FD" Offset="0.438"/>
<GradientStop Color="#FFA7DAF5" Offset="0.956"/>
<GradientStop Color="#FFE0F2FB" Offset="1"/>
</LinearGradientBrush>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_LeftLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_FirstLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_RightLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
</Storyboard>
</VisualState>
<VisualState x:Name="NavigationButtonMouseOver">
<Storyboard>
<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="PART_MouseOverNavigationButton"/>
<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background" Storyboard.TargetName="PART_OuterBorder">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FFF2F2F2" Offset="0.035"/>
<GradientStop Color="#FFECECEC" Offset="0.392"/>
<GradientStop Color="#FFDEDEDE" Offset="0.399"/>
<GradientStop Color="#FFECECEC" Offset="0.406"/>
<GradientStop Color="#FFDBDBDB" Offset="0.538"/>
<GradientStop Color="LightGray" Offset="0.839"/>
<GradientStop Color="#FFC7C7C7" Offset="0.846"/>
<GradientStop Color="LightGray" Offset="0.853"/>
<GradientStop Color="#FFD1D1D1" Offset="0.986"/>
<GradientStop Color="#FFDADADA" Offset="1"/>
</LinearGradientBrush>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_LeftLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_FirstLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_RightLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
</Storyboard>
</VisualState>
<VisualState x:Name="Pressed">
<Storyboard>
<DoubleAnimationUsingKeyFrames BeginTime="0" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[2].(RotateTransform.Angle)" Storyboard.TargetName="PART_path">
<SplineDoubleKeyFrame KeyTime="0" Value="0"/>
<SplineDoubleKeyFrame KeyTime="0:0:0.3" Value="90"/>
</DoubleAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="BorderBrush" Storyboard.TargetName="PART_NavigationButton">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<SolidColorBrush Color="#FF31658D"/>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background" Storyboard.TargetName="PART_OuterBorder">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FF596E7A" Offset="0"/>
<GradientStop Color="#FF6D8D9F" Offset="0.006"/>
<GradientStop Color="#FF6D8D9F" Offset="0.026"/>
<GradientStop Color="#FFA6C7D9" Offset="0.041"/>
<GradientStop Color="#FFA6C7D9" Offset="0.072"/>
<GradientStop Color="#FFC2E4F6" Offset="0.087"/>
<GradientStop Color="#FFC2E4F6" Offset="0.41"/>
<GradientStop Color="#FFA9D9F2" Offset="0.425"/>
<GradientStop Color="#FF90CBEB" Offset="0.991"/>
<GradientStop Color="#FF7D96A7" Offset="1"/>
</LinearGradientBrush>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_LeftLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_FirstLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Visibility" Storyboard.TargetName="PART_RightLine">
<DiscreteObjectKeyFrame KeyTime="0">
<DiscreteObjectKeyFrame.Value>
<Visibility>Visible</Visibility>
</DiscreteObjectKeyFrame.Value>
</DiscreteObjectKeyFrame>
</ObjectAnimationUsingKeyFrames>
</Storyboard>
</VisualState>
<VisualState x:Name="Released">
<Storyboard/>
</VisualState>
</VisualStateGroup>
</VisualStateManager.VisualStateGroups>

<Border x:Name="PART_OuterBorder" BorderThickness="0" Margin="0,1,0,0" Padding="0">
<Border.Background>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FF1C6998" Offset="0.043"/>
<GradientStop Color="#FFC0CCDE" Offset="0.522"/>
<GradientStop Color="#FF1C6998" Offset="0.989"/>
</LinearGradientBrush>
</Border.Background>
<Grid x:Name="PART_LayoutRoot">
<Grid.ColumnDefinitions>
<ColumnDefinition/>
<ColumnDefinition Width="Auto"/>
<ColumnDefinition Width="Auto"/>
</Grid.ColumnDefinitions>
<Grid.RowDefinitions>
<RowDefinition Height="*"/>
<RowDefinition Height="0"/>
</Grid.RowDefinitions>
<Line x:Name="PART_FirstLine" Grid.Column="0" Fill="#FF979899" HorizontalAlignment="Left" Margin="0" Grid.RowSpan="2" Stretch="UniformToFill" Stroke="#FF979899" StrokeThickness="0.5" Visibility="Collapsed" VerticalAlignment="Stretch" Y2="1"/>
<ContentControl x:Name="PART_ContentControl" ContentTemplate="{TemplateBinding HeaderTemplate}" Content="{TemplateBinding Header}" FontSize="12" FontFamily="/Syncfusion.Tools.WPF;component/Fonts/Fonts.zip#Segoe UI" HorizontalAlignment="Center" HorizontalContentAlignment="Center" VerticalAlignment="Center" VerticalContentAlignment="Center"/>
<Border x:Name="PART_NavigationButton" BorderBrush="Transparent" Background="Transparent" Grid.Column="1" Grid.RowSpan="2" Visibility="{TemplateBinding NextButtonVisibility}" VerticalAlignment="Stretch" Width="20">
<Grid>
<Border x:Name="PART_MouseOverNavigationButton" BorderBrush="Transparent" Opacity="0" Visibility="{TemplateBinding NextButtonVisibility}" VerticalAlignment="Stretch" Width="20">
<Border.Background>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FFF8FCFD" Offset="0"/>
<GradientStop Color="#FFD8F0FC" Offset="0.383"/>
<GradientStop Color="#FFBDE6FD" Offset="0.438"/>
<GradientStop Color="#FFA7DAF5" Offset="0.956"/>
<GradientStop Color="#FFE0F2FB" Offset="1"/>
</LinearGradientBrush>
</Border.Background>
</Border>
<Path x:Name="PART_path" Data="M-5.143136,-6.7254906 L5.9791045,-6.7152343 L5.870235,3.8053918 L-5.2263737,3.7391238 z" Fill="#FF034371" HorizontalAlignment="Center" Height="10.529" RenderTransformOrigin="0.5,0.5" Stretch="Fill" VerticalAlignment="Center" Width="11.218" UseLayoutRounding="False">
<Path.RenderTransform>
<TransformGroup>
<ScaleTransform/>
<SkewTransform/>
<RotateTransform/>
<TranslateTransform/>
</TransformGroup>
</Path.RenderTransform>
</Path>
<Line x:Name="PART_LeftLine" Fill="#FF979899" HorizontalAlignment="Left" Margin="0" Stretch="UniformToFill" Stroke="#FF979899" StrokeThickness="0.5" Visibility="Collapsed" VerticalAlignment="Stretch" Y2="1"/>
</Grid>
</Border>
<Line x:Name="PART_RightLine" Grid.Column="1" Fill="#FF979899" HorizontalAlignment="Right" Grid.RowSpan="2" Stretch="UniformToFill" Stroke="#FF979899" StrokeThickness="0.5" Visibility="Collapsed" VerticalAlignment="Stretch" Y2="1"/>
<Popup x:Name="PART_HierarchyNavigatorDropDownPopup" AllowsTransparency="True" Grid.Column="1" HorizontalOffset="-30" IsOpen="{TemplateBinding IsPopupOpen}" Placement="Right" Grid.Row="1" VerticalOffset="{TemplateBinding ActualHeight}">
<Border x:Name="PART_PopUpBorder" BorderBrush="#FF727272" BorderThickness="1" Background="#FFF0F0F0" Margin="0,0.2,0,0" MinWidth="220" Opacity="{TemplateBinding Opacity}">
<Border.RenderTransform>
<TransformGroup>
<ScaleTransform ScaleY="0" ScaleX="0"/>
<SkewTransform/>
<RotateTransform/>
<TranslateTransform/>
</TransformGroup>
</Border.RenderTransform>
<Grid x:Name="PART_Container">
<Rectangle x:Name="PART_LeftBar" Fill="#FFF1F1F1" HorizontalAlignment="Left" RadiusY="2" RadiusX="2" Width="28"/>
<Rectangle x:Name="PART_ItemSeparatorFill" HorizontalAlignment="Left" Margin="27,0,0,0" Stroke="#FFE5E6E6" StrokeThickness="0.5" Width="1"/>
<Rectangle x:Name="PART_ItemSeparatorStroke" HorizontalAlignment="Left" Margin="28,0,0,0" Stroke="#FFFCFCFC" StrokeThickness="0.5" Width="1"/>
<ScrollViewer x:Name="PART_ScrollViewerRoot" BorderThickness="0" HorizontalScrollBarVisibility="Auto" MaxHeight="212" Padding="2" VerticalScrollBarVisibility="Auto">
<ItemsPresenter x:Name="PART_ItemsPresenter"/>
</ScrollViewer>
</Grid>
</Border>
</Popup>
</Grid>
</Border>

</Grid>
</ControlTemplate>
</Setter.Value>
</Setter>
</Style>
</syncfusion:HierarchyNavigatorItemsControl.ItemContainerStyle>
</syncfusion:HierarchyNavigatorItemsControl>

<Grid x:Name="PART_ProgressBar" Margin="1" Opacity="0" RenderTransformOrigin="0,0.5">
<Grid.RenderTransform>
<TransformGroup>
<ScaleTransform ScaleX="0"/>
<SkewTransform/>
<RotateTransform/>
<TranslateTransform/>
</TransformGroup>
</Grid.RenderTransform>
<Rectangle>
<Rectangle.Fill>
<LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
<GradientStop Color="#FFB5C6B7" Offset="0"/>
<GradientStop Color="#FFDEF8DF" Offset="0.017"/>
<GradientStop Color="#FFC9E4CE" Offset="0.06"/>
<GradientStop Color="#FFB4E1C1" Offset="0.224"/>
<GradientStop Color="#FF68D582" Offset="0.271"/>
<GradientStop Color="#FF63CF7B" Offset="0.784"/>
<GradientStop Color="#FF77D688" Offset="0.94"/>
<GradientStop Color="#FF8FE89B" Offset="0.974"/>
<GradientStop Color="#FF8AB393" Offset="1"/>
</LinearGradientBrush>
</Rectangle.Fill>
</Rectangle>
<Rectangle Opacity="0.295">
<Rectangle.Fill>
<LinearGradientBrush EndPoint="0.982,0.53" StartPoint="0.916,0.513">
<GradientStop Color="#0064CE7A" Offset="0.736"/>
<GradientStop Color="#FF67BE79" Offset="1"/>
</LinearGradientBrush>
</Rectangle.Fill>
</Rectangle>
</Grid>

</Grid>
</ControlTemplate>
</Setter.Value>
</Setter>
</Style>

{% endhighlight  %}

Each part of a template can be edited. In the output for the above style, as shown in Figure 47 the background has been changed to a gradient and the down arrow has been changed to a square.

![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img10.png)



![](Customizing-templates-with-Expression-Blend_images/Customizing-templates-with-Expression-Blend_img11.png)



