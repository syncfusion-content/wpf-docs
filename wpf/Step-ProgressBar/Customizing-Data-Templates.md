---
layout: post
title: Customizing Data Templates| Step ProgressBar | Wpf | Syncfusion
description: customizing data templates
platform: wpf
control: SfStepProgressBar
documentation: ug
---

# Customizing Data Templates

Data templates can be customized for items and content. The next sections explain how to customize data templates.

## Item Template

You can customize how an object is displayed by using ItemTemplate of StepViewItem. The following example shows how to use ItemTemplate.following code, StepViewItem’s content is customized with DataTemplate. The value of content is assigned to the TextBlock’s text and TextBlock’s properties like FontWeight, FontFamily and Foreground are modified for a customized look.



{% highlight xaml %}

 <syncfusion:SfStepProgressBar
                x:Name="stepperControlName"
                Margin="40"
                ItemsSource="{Binding StepViewItems}"
                Orientation="Horizontal"
                SelectedIndex="2">
        <syncfusion:SfStepProgressBar.ItemContainerStyle>
                <Style TargetType="syncfusion:StepViewItem">
                        <Setter Property="Content" Value="{Binding ModelText}" />
                        <Setter Property="TextSpacing" Value="{Binding TitleSpace}" />
                </Style>
        </syncfusion:SfStepProgressBar.ItemContainerStyle>
        <syncfusion:SfStepProgressBar.ItemTemplate>
                <DataTemplate>
                        <TextBlock
                            Grid.Row="0"
                            FontFamily="Segoe UI"
                            FontSize="15"
                            FontWeight="SemiBold">
                            Create
                        </TextBlock>
                </DataTemplate>
        </syncfusion:SfStepProgressBar.ItemTemplate>
        <syncfusion:SfStepProgressBar.DataContext>
                <local:ViewModel />
        </syncfusion:SfStepProgressBar.DataContext>
</syncfusion:SfStepProgressBar>
{% endhighlight %}

Implementing the above code will create the following GroupBar control.



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img1.png)



## Item Template Selector

Using ItemTemplateSelector, you can use different templates for items depending on specific constraints. The following example illustrates this.

1. Create the template selector in the code.


   ~~~csharp

		public class GroupBarItemTemplateSelector : DataTemplateSelector

		{

		public override DataTemplate SelectTemplate(object item, DependencyObject container)

		{

		Window window = Application.Current.MainWindow;

		string bookname = (item as System.Xml.XmlElement).GetAttribute("Name").ToString().ToLower();

		if (bookname.Contains("wpf"))

		{

		return ((DataTemplate)window.Resources["WpfBookTemplate"]);

		}

		else

		{

		return ((DataTemplate)window.Resources["CsBookTemplate"]);

		}



		}

		}


   ~~~


2. Define the data templates in the Window’s resources.


   ~~~xaml


		<DataTemplate x:Key="WpfBookTemplate">

		<Grid>

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="25" />

		<ColumnDefinition Width="*" />

		</Grid.ColumnDefinitions>

		<Image Source="wpf.png"/>

		<TextBlock Text="{Binding XPath=@Name}" Margin="5" Foreground="Green" VerticalAlignment="Center" FontWeight="Bold" FontFamily="Bookman Old Style" Grid.Column="1"/>

		</Grid>

		</DataTemplate>



		<DataTemplate x:Key="CsBookTemplate">

		<Grid>

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="25" />

		<ColumnDefinition Width="*" />

		</Grid.ColumnDefinitions>

		<Image Source="images.jpg"/>

		<TextBlock Text="{Binding XPath=@Name}" Margin="5" Foreground="Green" VerticalAlignment="Center" FontWeight="Bold" FontFamily="Bookman Old Style" Grid.Column="1"/>

		</Grid>

		</DataTemplate>

   ~~~



3. The template selector in the Window’s resources.




   ~~~xaml
			<local:GroupBarItemTemplateSelector 
			x:Key="groupBarItemTemplateSelector"/>

   ~~~



4. Use this template selector to choose a template for the GroupBar control.


   ~~~xaml

		<syncfusion:GroupBar Name="groupBar1"  Margin="20" AllowCollapse="True" VisualMode="StackMode" ItemTemplateSelector="{StaticResource groupBarItemTemplateSelector}" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"  >



		</syncfusion:GroupBar>

   ~~~


This will generate the following GroupBar control.



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img2.png)

  

## Header Template

You can customize the header of a GroupViewItem by using a header template. This is illustrated in the following example.

1. Define the data template for the header as follows.


   ~~~xaml
		<DataTemplate x:Key="headerTemplate">

		<Grid>

		<Border Background="Gray">

		<TextBlock Text="{Binding XPath=@Name}" Margin="5" Foreground="White" VerticalAlignment="Center" FontWeight="Bold" FontFamily="Bookman Old Style" Grid.Column="1"/>

		</Border>

		</Grid>

		</DataTemplate>


   ~~~

2. Set HeaderTemplate for GroupBarItem to the above template.


   ~~~xaml

		<syncfusion:GroupBar Name="groupBar1"  Margin="20"  VisualMode="StackMode" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}">

		<syncfusion:GroupBar.ItemContainerStyle>

		<Style TargetType="{x:Type syncfusion:GroupBarItem}">

		<Setter Property="HeaderTemplate" Value="{StaticResource headerTemplate}" />                                      

		</Style>

		</syncfusion:GroupBar.ItemContainerStyle>



		</syncfusion:GroupBar>

   ~~~   

The code above applies HeaderTemplate to the GroupBar, so the headers of the group-bar items will contains a text box with a white foreground. 

## Content Template

You can customize the content of GroupViewItem by using ContentTemplate. This is demonstrated in the following example.

1. Define DataTemplate for the content as follows.


   ~~~xaml

		<DataTemplate x:Key="contentTemplate">

		<Grid >

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="4*"/>

		<ColumnDefinition Width="6*"/>

		</Grid.ColumnDefinitions>

		<Image Source="{Binding XPath=@ImagePath}"/>

		<TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" Grid.Column="1"/>

		</Grid>

		</DataTemplate>

   ~~~


2. Set ContentTemplate for GroupBarItem to the above template.


   ~~~xaml

		<syncfusion:GroupBar Name="groupBar1"  Margin="20"  VisualMode="StackMode" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}">

		<syncfusion:GroupBar.ItemContainerStyle>

		<Style TargetType="{x:Type syncfusion:GroupBarItem}">

		<Setter Property="HeaderTemplate" Value="{StaticResource headerTemplate}" />  

		<Setter Property="ContentTemplate" Value="{StaticResource contentTemplate}"/>

		</Style>

		</syncfusion:GroupBar.ItemContainerStyle>

		</syncfusion:GroupBar>


   ~~~


This will populate the GroupBar control.



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img3.png)

  

## Header Template Selector

With HeaderTemplateSelector, you can use different templates for the GroupBarItem’s header depending on specific constraints. The following example illustrates this. 

1. Create the template selector in code.


   ~~~csharp
   
		public class GroupBarItemHeaderTemplateSelector : DataTemplateSelector

		{

		public override DataTemplate SelectTemplate(object item, DependencyObject container)

		{

		Window window = Application.Current.MainWindow;

		string bookname = (item as System.Xml.XmlElement).GetAttribute("Name").ToString().ToLower();

		if (bookname.Contains("wpf"))

		{

		return ((DataTemplate)window.Resources["WpfBookHeaderTemplate"]);

		}

		else

		{

		return ((DataTemplate)window.Resources["CsBookHeaderTemplate"]);

		}



		}

		}

   ~~~

2. Define the data templates in the Window’s resources.


   ~~~xaml

		<DataTemplate x:Key="WpfBookHeaderTemplate">

		<Grid>

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="25" />

		<ColumnDefinition Width="*" />

		</Grid.ColumnDefinitions>

		<Image Source="wpficon.png"/>

		<TextBlock Text="{Binding XPath=@Name}" Margin="5" Foreground="Green" VerticalAlignment="Center" FontWeight="Bold" FontFamily="Bookman Old Style" Grid.Column="1"/>

		</Grid>

		</DataTemplate>



		<DataTemplate x:Key="CsBookHeaderTemplate">

		<Grid>

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="25" />

		<ColumnDefinition Width="*" />

		</Grid.ColumnDefinitions>

		<Image Source="csicon.png"/>

		<TextBlock Text="{Binding XPath=@Name}" Margin="5" Foreground="Blue" VerticalAlignment="Center" FontWeight="Bold" FontFamily="Bookman Old Style" Grid.Column="1"/>

		</Grid>

		</DataTemplate>


   ~~~

3. Create an instance for the template selector in the Window’s resources.


   ~~~xaml
   
		<local:GroupBarItemHeaderTemplateSelector 
		x:Key="groupBarItemHeaderTemplateSelector"/>

   ~~~

   

Now assign the key given in the above code to GroupBar’s HeaderTemplateSelector.

## Content Template Selector

With ContentTemplateSelector, you can use different templates for GroupBarItem’s content depending on specific constraints. The following example illustrates this.

1. Create the template selector in the code as follows.


   ~~~csharp

		public class GroupBarItemContentTemplateSelector : DataTemplateSelector

		{

		public override DataTemplate SelectTemplate(object item, DependencyObject container)

		{

		Window window = Application.Current.MainWindow;

		string bookname = (item as System.Xml.XmlElement).GetAttribute("Name").ToString().ToLower();

		if (bookname.Contains("wpf"))

		{

		return ((DataTemplate)window.Resources["WpfBookContentTemplate"]);

		}

		else

		{

		return ((DataTemplate)window.Resources["CsBookContentTemplate"]);

		}



		}

		}

   ~~~


2. Define the data templates in the Window’s resources.

   ~~~csharp

		<DataTemplate x:Key="CsBookHeaderTemplate">

		<Grid>

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="25" />

		<ColumnDefinition Width="*" />

		</Grid.ColumnDefinitions>

		<Image Source="csicon.png"/>

		<TextBlock Text="{Binding XPath=@Name}" Margin="5" Foreground="Blue" VerticalAlignment="Center" FontWeight="Bold" FontFamily="Bookman Old Style" Grid.Column="1"/>

		</Grid>

		</DataTemplate>



		<DataTemplate x:Key="WpfBookContentTemplate">

		<Grid >

		<Grid.ColumnDefinitions>

		<ColumnDefinition Width="4*"/>

		<ColumnDefinition Width="6*"/>

		</Grid.ColumnDefinitions>

		<Image Source="{Binding XPath=@ImagePath}"/>

		<TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" Foreground="Green" Grid.Column="1"/>

		</Grid>

		</DataTemplate>


   ~~~


3. Create an instance of the template selector in the Window’s resources.

   ~~~csharp
   
	  <local:GroupBarItemContentTemplateSelector 
	  x:Key="groupBarItemContentTemplateSelector"/>

   ~~~



4. Now use HeaderTemplateSelector and ContentTemplateSelector.

   ~~~csharp

		<syncfusion:GroupBar Name="groupBar1"  AllowCollapse="True" VisualMode="StackMode" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"   >

		<syncfusion:GroupBar.ItemContainerStyle>

		<Style TargetType="{x:Type syncfusion:GroupBarItem}">

		<Setter Property="HeaderTemplateSelector" Value="{StaticResource groupBarItemHeaderTemplateSelector}"/>

		<Setter Property="ContentTemplateSelector" Value="{StaticResource groupBarItemContentTemplateSelector}"/>

		</Style>

		</syncfusion:GroupBar.ItemContainerStyle>



		</syncfusion:GroupBar>


   ~~~


This will populate the GroupBar control.



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img4.png)

  

