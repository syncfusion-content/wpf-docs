---
layout: post
title: Appearance and Styling | SfAccordion | WPF | Syncfusion
description: This section explains how to customize the appearance and styling of SfAccordion control.
platform: WPF
control: SfAccordion
documentation: ug

---

# Applying Accent Colors

SfAccordion support accent colors to highlight the hot spots of the control. You can customize the accent colors using [AccentBrush](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~AccentBrush.html) property.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfAccordion x:Name="accordion"  AccentBrush="Red"  HorizontalAlignment="Center" VerticalAlignment="Center"/>
{% endhighlight %}
{% highlight C# %}
accordion.AccentBrush = new SolidColorBrush() { Color = Windows.UI.Colors.Red };
{% endhighlight %}
{% endtabs %}

![SfAccordionItem header customized](Appearence-and-Styling-images/Accent-Brush_img1.png)

## AccordionItem Style

You can customize the appearence of accordion item by writing the style of TargetType [SfAccordionItem](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordionItem.html), the edited style can be applied to SfAccordion control by setting SfAccordion.[ItemContainerStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~ItemContainerStyle.html) property.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfAccordion  Width="300" AccentBrush="Green" HorizontalAlignment="Center" VerticalAlignment="Center">
	<syncfusion:SfAccordion.ItemContainerStyle>
		<Style TargetType="syncfusion:SfAccordionItem">
				<Setter Property="Foreground" Value="Blue"/>
				<Setter Property="Background" Value="Pink"/>
				<Setter Property="BorderBrush" Value="White"/>
		</Style>
	</syncfusion:SfAccordion.ItemContainerStyle>
	<syncfusion:SfAccordionItem Header="WPF" Content="Essential Studio for WPF"/>
	<syncfusion:SfAccordionItem Header="Silverlight" Content="Essential Studio for Silverlight"/>
	<syncfusion:SfAccordionItem Header="WinRT" Content="Essential Studio for WinRT"/>
	<syncfusion:SfAccordionItem Header="Windows Phone" Content="Essential Studio for Windows Phone"/>
	<syncfusion:SfAccordionItem Header="Universal"  Content="Essential Studio for Universal"/>
</syncfusion:SfAccordion>
{% endhighlight %}
{% endtabs %}

![SfAccordionItem customization](Appearence-and-Styling-images/Accordion-Header-Style_img1.png)

## Accordion Expander Style

You can customize the appearence of expander button by writing the style of TargetType [AccordionButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.AccordionButton.html), the edited style can be applied to accordion item by setting [AccordionButtonStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordionItem~AccordionButtonStyle.html) property.

{% tabs %}
{% highlight XAML %}
<Window.Resources>
    <!--  AccordionButton Style -->
	<Style TargetType="syncfusion:AccordionButton" x:Key="expanderButtonStyle">
		<Setter Property="Template">
			<Setter.Value>
				<ControlTemplate TargetType="syncfusion:AccordionButton">
					<Grid Margin="{TemplateBinding Padding}" Background="Transparent">
						<VisualStateManager.VisualStateGroups>
							<VisualStateGroup x:Name="ExpandDirectionStates">
								<VisualStateGroup.Transitions>
									<VisualTransition GeneratedDuration="0" />
								</VisualStateGroup.Transitions>
							</VisualStateGroup>
							<VisualStateGroup x:Name="ExpansionStates">
								<VisualStateGroup.Transitions>
									<VisualTransition GeneratedDuration="0" />
								</VisualStateGroup.Transitions>
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
								<Border Height="Auto" Margin="0,0,0,0" x:Name="MouseOverBackground" VerticalAlignment="Stretch" Opacity="0" Background="Green" BorderBrush="Yellow" BorderThickness="{TemplateBinding BorderThickness}" CornerRadius="1,1,1,1" />
								<Grid Background="Transparent">
									<Grid.ColumnDefinitions>
										<ColumnDefinition Width="Auto"  />
										<ColumnDefinition Width="Auto" />
									</Grid.ColumnDefinitions>
									<Grid.RowDefinitions>
										<RowDefinition Height="Auto"/>
										<RowDefinition Height="Auto"  />
									</Grid.RowDefinitions>
									<Grid Height="19" HorizontalAlignment="Center" x:Name="icon"  VerticalAlignment="Center" Width="19" RenderTransformOrigin="0.5,0.5" Grid.Column="0" Grid.Row="0">
										<Grid.RenderTransform>
											<TransformGroup>
												<ScaleTransform />
												<SkewTransform />
												<RotateTransform Angle="-90" />
												<TranslateTransform />
											</TransformGroup>
										</Grid.RenderTransform>
										<Path Height="Auto" HorizontalAlignment="Center" Margin="0,0,0,0" x:Name="arrow" VerticalAlignment="Center" Width="Auto" RenderTransformOrigin="0.5,0.5" Stroke="Black" StrokeThickness="2" Data="M 1,1.5 L 4.5,5 L 8,1.5">
											<Path.RenderTransform>
												<TransformGroup>
													<ScaleTransform />
													<SkewTransform />
													<RotateTransform />
													<TranslateTransform />
												</TransformGroup>
											</Path.RenderTransform>
										</Path>
									</Grid>
						    		<ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="6,6,6,0" x:Name="header" Grid.Column="1" Grid.Row="0" Grid.RowSpan="1" Content="{TemplateBinding Content}" ContentTemplate="{TemplateBinding ContentTemplate}" />
								</Grid>
							</Grid>
						</Border>
					</Grid>
				</ControlTemplate>
			</Setter.Value>
		</Setter>
	</Style>
</Window.Resources>

<!--SfAccordion Control -->
<syncfusion:SfAccordion x:Name="accordion2" HorizontalAlignment="Right" AccentBrush="Red" VerticalAlignment="Center" Width="180">
    <syncfusion:SfAccordionItem Header="WindowsForms" AccordionButtonStyle="{StaticResource expanderButtonStyle}">
		<Grid  Background="#FFF4F3F2">
			<Grid.RowDefinitions>
	    		<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
			</Grid.RowDefinitions>
			<TextBlock Text="Grids" Margin="10,10,10,2" FontSize="13.333" Grid.Row="0"/>
			<TextBlock Text="Layout" Margin="10,10,10,2" FontSize="13.333" Grid.Row="1"/>
			<TextBlock Text="Data Visualization" Margin="10,10,10,2" FontSize="13.333" Grid.Row="2"/>
		</Grid>
    </syncfusion:SfAccordionItem>
	<syncfusion:SfAccordionItem Header="WPF" AccordionButtonStyle="{StaticResource expanderButtonStyle}">
		<Grid  Background="#FFF4F3F2">
			<Grid.RowDefinitions>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
			</Grid.RowDefinitions>
		    <TextBlock Text="Grids" Margin="10,10,10,2" FontSize="13.333" Grid.Row="0"/>
		    <TextBlock Text="Layout" Margin="10,10,10,2" FontSize="13.333" Grid.Row="1"/>
		    <TextBlock Text="Data Visualization" Margin="10,10,10,2" FontSize="13.333" Grid.Row="2"/>
		</Grid>
	</syncfusion:SfAccordionItem>
	<syncfusion:SfAccordionItem Header="UWP" AccordionButtonStyle="{StaticResource expanderButtonStyle}">
		<Grid  Background="#FFF4F3F2">
			<Grid.RowDefinitions>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
			</Grid.RowDefinitions>
			<TextBlock Text="Grids" Margin="10,10,10,2" FontSize="13.333" Grid.Row="0"/>
			<TextBlock Text="Layout" Margin="10,10,10,2" FontSize="13.333" Grid.Row="1"/>
			<TextBlock Text="Data Visualization" Margin="10,10,10,2" FontSize="13.333" Grid.Row="2"/>
		</Grid>
	</syncfusion:SfAccordionItem>
</syncfusion:SfAccordion>
{% endhighlight %}
{% endtabs %}

![Expander button customization](Appearence-and-Styling-images/Expander-Button-Style_img1.png)

## AccordionItem Content Style

You can customize the content control in expanded state by writing the style of TargetType [ExpandableContentControl](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.ExpandableContentControl.html), the edited style can be applied to accordion item by setting [ExpandableContentControlStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordionItem~ExpandableContentControlStyle.html) property.

{% tabs %}
{% highlight XAML %}
<Window.Resources>
    <!-- ExpandableContentControl Style  -->
	<Style TargetType="syncfusion:ExpandableContentControl" x:Key="expandableContentStyle">
		<Setter Property="TargetSize" Value="300,200" />
		<Setter Property="Percentage" Value="1" />
		<Setter Property="Template">
			<Setter.Value>
				<ControlTemplate TargetType="syncfusion:ExpandableContentControl">
					<ContentPresenter x:Name="ContentSite"  Cursor="{TemplateBinding Cursor}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" Margin="0" ContentTemplate="{TemplateBinding ContentTemplate}" />
				</ControlTemplate>
			</Setter.Value>
		</Setter>
	</Style>
</Window.Resources>

<!--SfAccordion Control -->
<syncfusion:SfAccordion x:Name="accordion1" SelectionMode="OneOrMore"  HorizontalAlignment="Center"  VerticalAlignment="Center" Width="180">
	<syncfusion:SfAccordionItem Header="WindowsForms" ExpandableContentControlStyle="{StaticResource expandableContentStyle}">
		<Grid  Background="#FFF4F3F2">
			<Grid.RowDefinitions>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
			</Grid.RowDefinitions>
			<TextBlock Text="Grids" Margin="10,10,10,2" FontSize="13.333" Grid.Row="0"/>
			<TextBlock Text="Layout" Margin="10,10,10,2" FontSize="13.333" Grid.Row="1"/>
			<TextBlock Text="Data Visualization" Margin="10,10,10,2" FontSize="13.333" Grid.Row="2"/>
		</Grid>
	</syncfusion:SfAccordionItem>
	<syncfusion:SfAccordionItem Header="WPF">
		<Grid  Background="#FFF4F3F2">
			<Grid.RowDefinitions>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
			</Grid.RowDefinitions>
			<TextBlock Text="Grids" Margin="10,10,10,2" FontSize="13.333" Grid.Row="0"/>
			<TextBlock Text="Layout" Margin="10,10,10,2" FontSize="13.333" Grid.Row="1"/>
			<TextBlock Text="Data Visualization" Margin="10,10,10,2" FontSize="13.333" Grid.Row="2"/>
		</Grid>
	</syncfusion:SfAccordionItem>
	<syncfusion:SfAccordionItem Header="UWP">
		<Grid  Background="#FFF4F3F2">
			<Grid.RowDefinitions>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
				<RowDefinition Height="40"/>
			</Grid.RowDefinitions>
	    	<TextBlock Text="Grids" Margin="10,10,10,2" FontSize="13.333" Grid.Row="0"/>
		    <TextBlock Text="Layout" Margin="10,10,10,2" FontSize="13.333" Grid.Row="1"/>
			<TextBlock Text="Data Visualization" Margin="10,10,10,2" FontSize="13.333" Grid.Row="2"/>
		</Grid>
	</syncfusion:SfAccordionItem>
</syncfusion:SfAccordion>
{% endhighlight %}
{% endtabs %}

![Expandable content control customization](Appearence-and-Styling-images/Expandable-Content-Control-Style_img1.png)
