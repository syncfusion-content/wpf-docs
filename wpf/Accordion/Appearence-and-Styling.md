---
layout: post
title: Appearance and Styling in WPF Accordion control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion WPF Accordion (SfAccordion) control and more.
platform: WPF
control: SfAccordion
 documentation: ug

---

# Appearance and Styling in WPF Accordion (SfAccordion)

## Applying accent colors

SfAccordion supports accent colors to highlight the hot spots of the control. You can customize the accent colors using the [AccentBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_AccentBrush) property.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfAccordion x:Name="accordion"  AccentBrush="Red"  HorizontalAlignment="Center" VerticalAlignment="Center"/>
{% endhighlight %}
{% highlight C# %}
accordion.AccentBrush = new SolidColorBrush() { Color = Windows.UI.Colors.Red };
{% endhighlight %}
{% endtabs %}

![WPF Accordion Accent Colors](Appearance-and-Styling-images/wpf-accordion-accent-colors.png)

## Accordion header style

You can customize the appearance of SfAccordionItem header by setting the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_HeaderTemplate) property of SfAccordion.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfAccordion HorizontalAlignment="Center" Height="250"  VerticalAlignment="Center" Width="300">
	<!-- For customizinng header -->
	<syncfusion:SfAccordion.HeaderTemplate>
		<DataTemplate>
			<TextBlock Text="{Binding}" Foreground="Red" Opacity="1" FontFamily="Calibri" FontWeight="Bold" FontSize="20"/>
		</DataTemplate>
	</syncfusion:SfAccordion.HeaderTemplate>
	<syncfusion:SfAccordionItem Header="WindowsForms"/>
	<syncfusion:SfAccordionItem Header="WPF"/>
	<syncfusion:SfAccordionItem Header="UWP"/>
	<syncfusion:SfAccordionItem Header="WinRT"/>
</syncfusion:SfAccordion>
{% endhighlight %}
{% endtabs %}

![WPF Accordion Header Style](Appearance-and-Styling-images/wpf-accordion-header-style.png)

## Accordion expander style

You can customize the appearance of expander button by writing style of [AccordionButton](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.AccordionButton.html), the edited style can be applied to accordion item by setting the [AccordionButtonStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordionItem.html#Syncfusion_Windows_Controls_Layout_SfAccordionItem_AccordionButtonStyle) property of SfAccordionItem.

{% tabs %}
{% highlight XAML %}
<!--  AccordionButton Style -->
<Style TargetType="syncfusion:AccordionButton" x:Key="expanderButtonStyle">
    <!--  Customization codes -->
	<VisualStateManager.VisualStateGroups>
	    <VisualStateGroup x:Name="ExpansionStates">
		    <VisualState x:Name="Collapsed">
		        <Storyboard>
				    <DoubleAnimation BeginTime="00:00:00" Duration="00:00:00.3" Storyboard.TargetName="icon" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[2].(RotateTransform.Angle)" To="0" />
			    </Storyboard>
			</VisualState>
			<VisualState x:Name="Expanded">
				<Storyboard>
					<DoubleAnimation BeginTime="00:00:00" Duration="00:00:00.3" Storyboard.TargetName="icon" Storyboard.TargetProperty="(UIElement.RenderTransform).(TransformGroup.Children)[2].(RotateTransform.Angle)" To="90" />
					<ColorAnimationUsingKeyFrames BeginTime="00:00:00" Duration="00:00:00.0010000" Storyboard.TargetName="ExpandedBackground" Storyboard.TargetProperty="(Border.Background).(SolidColorBrush.Color)">
						<SplineColorKeyFrame KeyTime="00:00:00" Value="DeepPink" />
			    	</ColorAnimationUsingKeyFrames>
					<DoubleAnimationUsingKeyFrames BeginTime="00:00:00" Duration="00:00:00.0010000" Storyboard.TargetName="ExpandedBackground" Storyboard.TargetProperty="(UIElement.Opacity)">
			     		<SplineDoubleKeyFrame KeyTime="00:00:00" Value="0.5" />
					</DoubleAnimationUsingKeyFrames>
				</Storyboard>
			</VisualState>
		</VisualStateGroup>
	</VisualStateManager.VisualStateGroups>
	<Border x:Name="background" Background="{Binding Background}"  CornerRadius="1,1,1,1">
		<Grid>
			<Border Height="Auto" Margin="0,0,0,0" x:Name="ExpandedBackground" VerticalAlignment="Stretch" Opacity="0" Background="Red" BorderBrush="Yellow" BorderThickness="{TemplateBinding BorderThickness}" CornerRadius="1,1,1,1" />
				<Grid Height="19" HorizontalAlignment="Center" x:Name="icon"  VerticalAlignment="Center" Width="19" RenderTransformOrigin="0.5,0.5" Grid.Column="0" Grid.Row="0">
					<Grid.RenderTransform>
						<TransformGroup>
							<ScaleTransform />
							<SkewTransform />
							<RotateTransform Angle="-90" />
						<TranslateTransform />
					</TransformGroup>
				</Grid.RenderTransform>
				<Path Height="Auto" HorizontalAlignment="Center" Margin="0,0,0,0" x:Name="arrow" VerticalAlignment="Center" Width="Auto" RenderTransformOrigin="0.5,0.5" Stroke="Red" StrokeThickness="1.5" Stretch="Uniform" Data="M16.365994,20.000013L32.000027,29.802015 30.936978,31.497023 16.368008,22.360976 1.0660061,32.000013 2.7179741E-05,30.308973z M16.366,10L32.000001,19.802 30.937001,21.497 16.368001,12.361001 1.0659999,22 0,20.309z M16.366,0L32.000001,9.802 30.937001,11.497001 16.368001,2.3610001 1.0659999,12 0,10.309z"/>
			</Grid>
			<ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}"  x:Name="header" Grid.Column="1" Grid.Row="0" Grid.RowSpan="1" Content="{TemplateBinding Content}" ContentTemplate="{TemplateBinding ContentTemplate}" />
		</Grid>
	</Border>
</Style>
<!--SfAccordion Control -->
<syncfusion:SfAccordion x:Name="accordion1" HorizontalAlignment="Right" VerticalAlignment="Center" Width="180">
	<!-- Setting AccordionButtonStyle -->
	<syncfusion:SfAccordion.ItemContainerStyle>
		<Style TargetType="syncfusion:SfAccordionItem">
			<Setter Property="AccordionButtonStyle"  Value="{StaticResource expanderButtonStyle}"/>
		</Style>
	</syncfusion:SfAccordion.ItemContainerStyle>
</syncfusion:SfAccordion>
{% endhighlight %}
{% endtabs %}

![WPF Accordion Expander Style](Appearance-and-Styling-images/wpf-accordion-expander-style.png)

## AccordionItem header height customization

You can customize the height of SfAccordionItem header by setting the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_HeaderTemplate) property of SfAccordion. 

{% tabs %}
{% highlight XAML %}
<!-- For customizinng header -->		
<syncfusion:SfAccordion.HeaderTemplate>
	<DataTemplate>
		<TextBlock Text="{Binding Name}"  Height="50" FontSize="30"  VerticalAlignment="Center"/>
	</DataTemplate>
</syncfusion:SfAccordion.HeaderTemplate>
{% endhighlight %}
{% endtabs %}

![WPF Accordion Header Height Customization](Appearance-and-Styling-images/wpf-accordion-header-height-customization.png)

## AccordionItem content height customization

You can customize the height of SfAccordionItem content by setting the [ContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_ContentTemplate) property of SfAccordion.

{% tabs %}
{% highlight XAML %}
<!-- For customizinng SfAccordionItem content -->	
<syncfusion:SfAccordion.ContentTemplate>
	<DataTemplate>
		<TextBlock Text="{Binding Description}" Height="60"/>
	</DataTemplate>
</syncfusion:SfAccordion.ContentTemplate>
{% endhighlight %}
{% endtabs %}

![WPF Accordion Content Height Customization](Appearance-and-Styling-images/wpf-accordion-content-height-customization.png)

## Enable or disable the animation behaviour

You can enable or disable the animation behaviour when its item is expanded or collapsed. It can be achieved by setting [TargetSize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.ExpandableContentControl.html#Syncfusion_Windows_Controls_Layout_ExpandableContentControl_TargetSize) and [Percentage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.ExpandableContentControl.html#Syncfusion_Windows_Controls_Layout_ExpandableContentControl_Percentage) properties in [ExpandableContentControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.ExpandableContentControl.html) and writing the animation style in [SfAccordionItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordionItem.html), the edited style can be applied by using the [ItemContainerStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_ItemContainerStyle) property of the SfAccordion control.

{% tabs %}
{% highlight XAML %}
<!--  SfAccordionItem Style  -->
<Style x:Key="animationStyle"  TargetType="syncfusion:SfAccordionItem">
    <!-- Customization codes  -->
	<VisualStateManager.VisualStateGroups>
		<!-- Animation Style -->
		<VisualStateGroup x:Name="ExpansionStates">
			<VisualStateGroup.Transitions>
				<VisualTransition GeneratedDuration="0"/>
		 	</VisualStateGroup.Transitions>
            <!-- enable animation-->
			<VisualState x:Name="Collapsed">
				<Storyboard>
					<DoubleAnimationUsingKeyFrames BeginTime="00:00:01" Duration="00:00:10" Storyboard.TargetName="ExpandSite" Storyboard.TargetProperty="(layout:ExpandableContentControl.Percentage)">
 						<SplineDoubleKeyFrame KeySpline="0.2,0,0,1" KeyTime="00:00:10.0" Value="0" />
					</DoubleAnimationUsingKeyFrames>
				</Storyboard>
			</VisualState>
			<VisualState x:Name="Expanded">
				<Storyboard>
					<DoubleAnimationUsingKeyFrames BeginTime="00:00:01" Duration="00:00:10" Storyboard.TargetName="ExpandSite" Storyboard.TargetProperty="(layout:ExpandableContentControl.Percentage)">
						<SplineDoubleKeyFrame KeySpline="0.2,0,0,1" KeyTime="00:00:10.0" Value="1" />
					</DoubleAnimationUsingKeyFrames>
				</Storyboard>
			</VisualState>
		</VisualStateGroup>
	</VisualStateManager.VisualStateGroups>
	<Border x:Name="Background" Padding="{TemplateBinding Padding}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" CornerRadius="1,1,1,1">
		<Grid>
			<Grid.RowDefinitions>
				<RowDefinition Height="Auto" />
				<RowDefinition Height="Auto" />
			</Grid.RowDefinitions>
			<Grid.ColumnDefinitions>
				<ColumnDefinition Width="Auto" />
				<ColumnDefinition Width="Auto" />
			</Grid.ColumnDefinitions>
			<syncfusion:AccordionButton Name="ExpanderButton"  Style="{TemplateBinding AccordionButtonStyle}" Content="{TemplateBinding Header}" ContentTemplate="{TemplateBinding HeaderTemplate}" IsChecked="{TemplateBinding IsSelected}" IsTabStop="True" Grid.Row="0" Padding="0,0,0,0" Margin="0,0,0,0" FontFamily="{TemplateBinding FontFamily}" FontSize="{TemplateBinding FontSize}" FontStretch="{TemplateBinding FontStretch}" FontStyle="{TemplateBinding FontStyle}" FontWeight="{TemplateBinding FontWeight}" Foreground="{TemplateBinding Foreground}" HorizontalContentAlignment="{TemplateBinding HorizontalContentAlignment}" VerticalContentAlignment="{TemplateBinding VerticalContentAlignment}" HorizontalAlignment="{TemplateBinding HorizontalAlignment}" VerticalAlignment="{TemplateBinding VerticalAlignment}" Background="{TemplateBinding Background}" />
			<syncfusion:ExpandableContentControl Name="ExpandSite"  Grid.Row="1" IsTabStop="False" Percentage="0"  Content="{TemplateBinding Content}" ContentTemplate="{TemplateBinding ContentTemplate}" Margin="0,0,0,0" Style="{StaticResource expandableContentStyle}" FontFamily="{TemplateBinding FontFamily}" FontSize="{TemplateBinding FontSize}" FontStretch="{TemplateBinding FontStretch}" FontStyle="{TemplateBinding FontStyle}" FontWeight="{TemplateBinding FontWeight}" Foreground="{TemplateBinding Foreground}" HorizontalContentAlignment="{TemplateBinding HorizontalContentAlignment}" VerticalContentAlignment="{TemplateBinding VerticalContentAlignment}" HorizontalAlignment="{TemplateBinding HorizontalAlignment}" VerticalAlignment="{TemplateBinding VerticalAlignment}" />
		</Grid>
	</Border>
</Style>

<!--SfAccordion Control -->
<syncfusion:SfAccordion x:Name="accordion1" HorizontalAlignment="Center" VerticalAlignment="Center"  ItemContainerStyle="{StaticResource animationStyle}" />
{% endhighlight %}
{% endtabs %}

![WPF Accordion Animation](Appearance-and-Styling-images/wpf-accordion-animation.png)
