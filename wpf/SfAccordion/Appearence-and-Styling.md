---
layout: post
title: Appearance and Styling | SfAccordion | WPF | Syncfusion
description: This section explains how to customize the appearance and styling of SfAccordion control.
platform: WPF
control: SfAccordion
documentation: ug

---

## Applying Accent Colors

SfAccordion support accent colors to highlight the hot spots of the control. You can customize the accent colors using [AccentBrush](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~AccentBrush.html) property.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfAccordion x:Name="accordion"  AccentBrush="Red"  HorizontalAlignment="Center" VerticalAlignment="Center"/>
{% endhighlight %}
{% highlight C# %}
accordion.AccentBrush = new SolidColorBrush() { Color = Windows.UI.Colors.Red };
{% endhighlight %}
{% endtabs %}

![Accent Colors applied on SfAccordion header](Appearance-and-Styling-images/Accent-Brush_img1.png)

## Accordion Header Style

You can customize the appearance of SfAccordionItem header by setting the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~HeaderTemplate.html) of SfAccordion.

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

![SfAccordionItem header style customized using HeaderTemplate](Appearance-and-Styling-images/Accordion-Header-Style_img1.png)

## AccordionItem Style

You can customize the appearance of SfAccordionItem content by setting [ItemContainerStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~ItemContainerStyle.html) property of SfAccordion.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfAccordion  Width="300"  HorizontalAlignment="Center" VerticalAlignment="Center">
	<syncfusion:SfAccordion.ItemContainerStyle>
		<Style TargetType="syncfusion:SfAccordionItem">
			<Setter Property="Foreground"  Value="Red"/>
			<Setter Property="FontSize"  Value="14"/>
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

![SfAccordionItem header style customized using ItemContainerStyle](Appearance-and-Styling-images/AccordionItem-Content-img1.png)

## Accordion Expander Style

You can customize the appearance of expander button by writing the style of TargetType [AccordionButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.AccordionButton.html), the edited style can be applied to accordion item by setting [AccordionButtonStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordionItem~AccordionButtonStyle.html) property of SfAccordionItem.

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
										<Path Height="Auto" HorizontalAlignment="Center" Margin="0,0,0,0" x:Name="arrow" VerticalAlignment="Center" Width="Auto" RenderTransformOrigin="0.5,0.5" Stroke="Yellow" StrokeThickness="2" Data="M 1,1.5 L 4.5,5 L 8,1.5">
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
<syncfusion:SfAccordion x:Name="accordion1" HorizontalAlignment="Right" VerticalAlignment="Center" Width="180">
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

![Expander button customization](Appearance-and-Styling-images/Expander-Button-Style_img1.png)

## AccordionItem Header Height Customization

You can customize the height of SfAccordionItem header by setting the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~HeaderTemplate.html) of SfAccordion. 

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

![SfAccordionItem header height customized](Appearance-and-Styling-images/Accordion-Header-Style_img2.png)

## AccordionItem Content Height Customization

You can customize the height of SfAccordionItem content by setting the [ContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~ContentTemplate.html) of SfAccordion.

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

![SfAccordionItem content height customized](Appearance-and-Styling-images/AccordionItem-Height_img1.png)

## Enable/ Disable the Animation Behaviour

You can enable or disable the animation behaviour when its item is expanded/collapsed. It can be achieved by editing the style in [ExpandableContentControl](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.ExpandableContentControl.html) and [SfAccordionItem](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordionItem.html), the edited style can be applied by using ItemContainerStyle property of SfAccordion control.

{% tabs %}
{% highlight XAML %}
<!-- ExpandableContentControl Style  -->
<Style TargetType="syncfusion:ExpandableContentControl" x:Key="expandableContentStyle">
	<Setter Property="TargetSize" Value="200,200"/>
	<Setter Property="Template">
		<Setter.Value>
			<ControlTemplate TargetType="syncfusion:ExpandableContentControl">
				<ContentPresenter x:Name="ContentSite"  Cursor="{TemplateBinding Cursor}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" Margin="0" ContentTemplate="{TemplateBinding ContentTemplate}" />
	 		</ControlTemplate>
		</Setter.Value>
	</Setter>
</Style>

<!--  SfAccordionItem Style  -->
<Style x:Key="Style1"  TargetType="syncfusion:SfAccordionItem">
	<Setter Property="Template">
		<Setter.Value>
			<ControlTemplate TargetType="syncfusion:SfAccordionItem">
				<!-- Background="{TemplateBinding Background}"  -->
				<Grid Background="Blue" HorizontalAlignment="{TemplateBinding HorizontalAlignment}" VerticalAlignment="{TemplateBinding VerticalAlignment}">
					<VisualStateManager.VisualStateGroups>
	 					<!-- ExpansionStates -->
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
						<!-- ExpansionStates -->
						<VisualStateGroup x:Name="LockedStates">
							<VisualStateGroup.Transitions>
								<VisualTransition GeneratedDuration="0" />
							</VisualStateGroup.Transitions>
							<VisualState x:Name="Locked">
								<Storyboard>
									<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetName="ExpanderButton" Storyboard.TargetProperty="IsEnabled">
										<DiscreteObjectKeyFrame KeyTime="0">
											<DiscreteObjectKeyFrame.Value>
												<sys:Boolean>False</sys:Boolean>
											</DiscreteObjectKeyFrame.Value>
										</DiscreteObjectKeyFrame>
									</ObjectAnimationUsingKeyFrames>
								</Storyboard>
							</VisualState>
							<VisualState x:Name="Unlocked">
								<Storyboard>
									<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetName="ExpanderButton" Storyboard.TargetProperty="IsEnabled">
										<DiscreteObjectKeyFrame KeyTime="0">
											<DiscreteObjectKeyFrame.Value>
												<sys:Boolean>True</sys:Boolean>
											</DiscreteObjectKeyFrame.Value>
										</DiscreteObjectKeyFrame>
									</ObjectAnimationUsingKeyFrames>
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
				</Grid>
			</ControlTemplate>
		</Setter.Value>
	</Setter>
</Style>

<!--SfAccordion Control -->
<syncfusion:SfAccordion x:Name="accordion1" HorizontalAlignment="Center" VerticalAlignment="Center"  ItemContainerStyle="{StaticResource Style1}" >
	<syncfusion:SfAccordionItem Header="WindowsForms">
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
	<syncfusion:SfAccordionItem Header="UWP"">
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

 N> In this Animation behaviour, [TargetSize](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.ExpandableContentControl~TargetSize.html) and [Percentage](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.ExpandableContentControl~Percentage.html) properties are used for animate the size.

 ![SfAccordionItem animation](Appearance-and-Styling-images/Accordion-Animation_img1.png)