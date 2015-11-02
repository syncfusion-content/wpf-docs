---
layout: post
title: Patterns and Practices
description: Patterns and Practices
platform: wpf
control: Ribbon
documentation: ug
---
## Patterns and Practices

## MVVM

Ribbon supports MVVM Pattern to get better control customization. The following code illustrate this

###Model

{% highlight c# %}

[C#]

public class CustomRibbonTab

{

public string TabHeader { get; set; }

public ObservableCollection<CustomRibbonBar> CustomRibbonBars { get; set; }

public CustomRibbonTab()

{

CustomRibbonBars = new ObservableCollection<CustomRibbonBar>();

}

}

public class CustomRibbonBar

{

public string BarHeader { get; set; }

public ObservableCollection<CustomRibbonItem> CustomRibbonItems { get; set; }

public CustomRibbonBar()

{

CustomRibbonItems = new ObservableCollection<CustomRibbonItem>();

}

}

public class CustomRibbonItem

{

public CustomRibbonItem()

{

IsSplitButton = false;

IsBoolean = true;

}

public string ItemHeader

{

get;

set;

}

public string Image { get; set; }

public bool IsBoolean { get; set; }

public bool IsLarge { get; set; }

public bool IsSplitButton { get; set; }

}





{% endhighlight %}

###ViewModel

{% highlight c# %}

[C#]

public class ViewModel

{

public ObservableCollection<CustomRibbonTab> CustomRibbonTabs { get; set; }

public ViewModel()

{

CustomRibbonTabs = new ObservableCollection<CustomRibbonTab>();

PopulateRibbonTabs();

}

void PopulateRibbonTabs()

{

CustomRibbonTab Tab1 = new CustomRibbonTab() { TabHeader = "Home" };

PopulateRibbonHomeBars(Tab1);

CustomRibbonTabs.Add(Tab1);

}

//Home Tab

void PopulateRibbonHomeBars(CustomRibbonTab Tab)

{

CustomRibbonBar Bar1 = new CustomRibbonBar() { BarHeader = "Clipboard" };

PopuplateRibbonNewItems(Bar1);

CustomRibbonBar Bar2 = new CustomRibbonBar() { BarHeader = "Editing" };

PopuplateRibbonEditingItems(Bar2);

Tab.CustomRibbonBars.Add(Bar1);

Tab.CustomRibbonBars.Add(Bar2);

}

void PopuplateRibbonNewItems(CustomRibbonBar Bar)

{

CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Paste", IsLarge = true, Image = "Paste32.png" };

CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Cut", Image = "Cut16.png" };

CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Copy", Image = "Copy16.png" };

CustomRibbonItem Item4 = new CustomRibbonItem() { ItemHeader = "Format Painter", Image = "FormatPainter16.png" };

Bar.CustomRibbonItems.Add(Item1);

Bar.CustomRibbonItems.Add(Item2);

Bar.CustomRibbonItems.Add(Item3);

Bar.CustomRibbonItems.Add(Item4);

}

private void PopuplateRibbonEditingItems(CustomRibbonBar Bar)

{

CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Hyperlink", IsLarge = true, Image = "hyperlink32.png" };

CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Replace", IsLarge = true, Image = "replace_32.png" };

CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Zoom", IsLarge = true, Image = "Zoom_32x32.png" };

Bar.CustomRibbonItems.Add(Item1);

Bar.CustomRibbonItems.Add(Item2);

Bar.CustomRibbonItems.Add(Item3);

}



}



{% endhighlight %}

####MainWindow.xaml

{% highlight xml %}

[XAML]

<syncfusion:RibbonWindow x:Class="RibbonSample_in_MVVM.MainWindow"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" syncfusion:SkinStorage.VisualStyle="Office2013"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

xmlns:local="clr-namespace:RibbonSample_in_MVVM"

Title="MainWindow" Height="350" Width="525">

<Window.Resources>

<ResourceDictionary>

<ResourceDictionary.MergedDictionaries>

<ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/Ribbon/Themes/Office2013Style.xaml" />

</ResourceDictionary.MergedDictionaries>

<local:BooltoSizeformConverter x:Key="sizeform"/>

<local:ItemDataTemplateSelector x:Key="selector"/>

<local:ImageConverter x:Key="image"/>

<DataTemplate x:Key="Ribbonbutton">

<syncfusion:RibbonButton Label="{Binding ItemHeader}" SizeForm="{Binding IsLarge, Converter={StaticResource sizeform}}"  LargeIcon="{Binding Image,Converter={StaticResource image}}" SmallIcon="{Binding Image,Converter={StaticResource image}}"/>

</DataTemplate>

<DataTemplate x:Key="Splitbutton">

<syncfusion:SplitButton Label="{Binding ItemHeader}" SizeForm="{Binding IsLarge, Converter={StaticResource sizeform}}"  LargeIcon="{Binding Image,Converter={StaticResource image}}" SmallIcon="{Binding Image,Converter={StaticResource image}}"/>

</DataTemplate>

</ResourceDictionary>



</Window.Resources>

<Window.DataContext>

<local:ViewModel/>

</Window.DataContext>

<Grid>

<syncfusion:Ribbon 

x:Name="Ribbon"  VerticalAlignment="Top"   

ItemsSource="{Binding CustomRibbonTabs}" >

<syncfusion:Ribbon.ItemContainerStyle>

<Style TargetType="{x:Type syncfusion:RibbonTab}">

<Setter Property="Caption" Value="{Binding TabHeader}"></Setter>

<Setter Property="ItemsSource" Value="{Binding CustomRibbonBars}"/>

<Setter Property="ItemContainerStyle">

<Setter.Value>

<Style BasedOn="{StaticResource Office2013RibbonBarStyle}" TargetType="{x:Type syncfusion:RibbonBar}">

<Setter Property="Header" Value="{Binding BarHeader}"/>

<Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/>

<Setter Property="ItemTemplateSelector" Value="{StaticResource selector}"/>



</Style>

</Setter.Value>

</Setter>

</Style>

</syncfusion:Ribbon.ItemContainerStyle>



</syncfusion:Ribbon>

</Grid>

</syncfusion:RibbonWindow>





{% endhighlight %}

####Converter.cs

{% highlight c# %}

[C#]

public class BooltoSizeformConverter:IValueConverter

{



public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

{



if (value.Equals(true))

{

return "Large";

}

else

{

return "Small";

}

}

public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

{

throw new NotImplementedException();

}



}

public class ItemDataTemplateSelector : DataTemplateSelector

{

public override DataTemplate SelectTemplate(object item, DependencyObject container)

{

FrameworkElement element = container as FrameworkElement;

if (element != null && item != null )

{

if (item is CustomRibbonItem && (item as CustomRibbonItem).IsSplitButton)

{

return

element.FindResource("Splitbutton") as DataTemplate;

}

else

{

return element.FindResource("Ribbonbutton") as DataTemplate;

}



}

return null;

}

}

public class ImageConverter : IValueConverter

{

public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

{

if (value != null)

{

string str = value.ToString();

return "../Images/" + str;

}

else

return value;

}

public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

{

throw new System.NotImplementedException();

}

}



{% endhighlight %}

![](PatternsandPractices_images/PatternsandPractices_img1.jpeg)


## Practice with PRISM


Ribbon control provides prism support. The following steps will help to create sample project in the PRISM.

1. Create a New WPF project and add the following references to the solution project.

 Microsoft.Practices.Composite.dll

 Microsoft.Practices.Composite.Presentation.dll

 Microsoft.Practices.Composite.UnityExtensions.dll

 Microsoft.Practices.ServiceLocation.dll

 Microsoft.Praactices.Unity.dll

2. Rename MainWindow to Shell in the Project
3. Add new class called Bootstrapper.cs to initialize the prism application.
	
	{% highlight c# %}

	[C#]

 	class Bootstrapper : UnityBootstrapper

	{

	protected override DependencyObject CreateShell()

	{

	Shell shell = new Shell();

	shell.Show();

	return shell;

	}

	protected override IModuleCatalog GetModuleCatalog()

	{

	ModuleCatalog catalog = new ModuleCatalog();

	catalog.AddModule(typeof(HomeTabModule.HomeTabModules));

	return catalog;

	}

	}

	{% endhighlight %}

4. Override Onstartup method in the App.xaml.cs to execute Bootstrapper when the application starts

	{% highlight c# %}

	[C#]

	public partial class App : Application

	{

	protected override void OnStartup(StartupEventArgs e)

	{

	base.OnStartup(e);

	Bootstrapper bootstrapper = new Bootstrapper();

	bootstrapper.Run();

	}

	}

	{% endhighlight %}

5. Next step is to create regions in the shell. To do this, first add the following namespace in the shell Window

	{% highlight xml %}

	[XAML]

	xmlns:Cal="http://www.codeplex.com/CompositeWPF"

	{% endhighlight %}

	In the below code, a region called “Tabs” has been created to load RibbonTab Module views

	{% highlight xml %}

	[XAML]

	<syncfusion:RibbonWindow x:Class="RibbonDemoSample.Shell"

	xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

	xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

	xmlns:Cal="http://www.codeplex.com/CompositeWPF" syncfusion:SkinStorage.VisualStyle="Office2013"

	xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

	Title="MainWindow" Height="350" Width="525">

	<Grid>

	<syncfusion:Ribbon Cal:RegionManager.RegionName="Tabs"  VerticalAlignment="Top">

	</syncfusion:Ribbon>

	</Grid>

	</syncfusion:RibbonWindow>

	{% endhighlight %}

6. Adding Module to the project

	Right click the Solution project, point to “Add” and then click “NewProject”.Then NewWindow called AddNewProject will open.Select “ClassLibrary” from Visual C# .then rename the project with desired name and click OK.Now a New Module will be created in the Solution Project

	Now add following assemblies to the Module project

	* PresentationCore.dll
	* PresentationFramework.dll
	* WindowsBase.dll

	Also add following Prism assemblies

	* Microsoft.Practices.Composite.dll
	* Microsoft.Practices.Composite.Presentation.dll
	* Microsoft.Practices.Composite.UnityExtensions.dll
	* Microsoft.Practices.ServiceLocation.dll
	* Microsoft.Praactices.Unity.dll

7. In the Shell project, add the reference to the “HomeTabModule” project by registering with ModuleCatalog instance in the GetModuleCatalog method

	{% highlight c# %}

	[C#]

	class Bootstrapper : UnityBootstrapper

	{

	protected override DependencyObject CreateShell()

	{

	Shell shell = new Shell();

	shell.Show();

	return shell;

	}

	protected override IModuleCatalog GetModuleCatalog()

	{

	ModuleCatalog catalog = new ModuleCatalog();

	catalog.AddModule(typeof(HomeTabModule.HomeTabModules));

	return catalog;

	}

	}

	{% endhighlight %}

8. Adding Views to the Module

	{% highlight xml %}

	[XAML]

	<syncfusion:RibbonTab x:Class="HomeTabModule.HomeTab"

	xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

	xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

	xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" 

	xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 

	xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

	mc:Ignorable="d" 

	d:DesignHeight="300" d:DesignWidth="300" Caption="Home" IsChecked="True" >

	<syncfusion:RibbonBar>

	<syncfusion:RibbonBar.Resources>

	<ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/Ribbon/Themes/Office2013Style.xaml" />

	</syncfusion:RibbonBar.Resources>

	<syncfusion:RibbonBar.Style>

	<Style BasedOn="{StaticResource Office2013RibbonBarStyle}" TargetType="{x:Type syncfusion:RibbonBar}">

	</Style>

	</syncfusion:RibbonBar.Style>

	<syncfusion:RibbonButton Width="44"

	Margin="3,0,3,3"

	Label="Paste"

	SizeForm="Large"

	syncfusion:Ribbon.KeyTip="CP"

	syncfusion:RibbonCommandManager.SynchronizedItem="Paste">

	<syncfusion:RibbonButton.ToolTip>

	<syncfusion:ScreenTip Description="Paste (Ctrl+V)">

	<TextBlock Width="130"

	HorizontalAlignment="Left"

	Foreground="#FF4C4C4C"

	Text="Paste the contents of clipboard."

	TextWrapping="Wrap" />

	</syncfusion:ScreenTip>

	</syncfusion:RibbonButton.ToolTip>

	</syncfusion:RibbonButton>

	<syncfusion:RibbonButton HorizontalAlignment="Left"

	Label="Cut"

	SizeForm="Small"

	syncfusion:Ribbon.KeyTip="CT">

	<syncfusion:RibbonButton.ToolTip>

	<syncfusion:ScreenTip Description="Cut (Ctrl+X)">

	<TextBlock Width="130"

	HorizontalAlignment="Left"

	Text="Cut the selection and put it on the clipboard."

	TextWrapping="Wrap" />

	</syncfusion:ScreenTip>

	</syncfusion:RibbonButton.ToolTip>

	</syncfusion:RibbonButton>

	<syncfusion:RibbonButton HorizontalAlignment="Left"

	Label="Copy"

	SizeForm="Small"

	syncfusion:Ribbon.KeyTip="CY">

	<syncfusion:RibbonButton.ToolTip>

	<syncfusion:ScreenTip Description="Copy (Ctrl+C)">

	<TextBlock Width="130"

	HorizontalAlignment="Left"

	Foreground="#FF4C4C4C"

	Text="Copy the selection and put it on the clipboard."

	TextWrapping="Wrap" />

	</syncfusion:ScreenTip>

	</syncfusion:RibbonButton.ToolTip>

	</syncfusion:RibbonButton>

	<syncfusion:RibbonButton Label="Format Painter"

	SizeForm="Small"

	syncfusion:Ribbon.KeyTip="CR">

	<syncfusion:RibbonButton.ToolTip>

	<syncfusion:ScreenTip Description="Format painter (Ctrl+Shift+C)" HelpText="Press F1 for more help.">

	<TextBlock Width="175"

	HorizontalAlignment="Left"

	Foreground="#FF4C4C4C"

	TextWrapping="Wrap">

	<Run Text="Copy formatting from one place and apply it to another." />

	<LineBreak />

	<LineBreak />

	<Run Text="Double-click this button to apply the same formatting to multiple places in the document." />

	</TextBlock>

	</syncfusion:ScreenTip>

	</syncfusion:RibbonButton.ToolTip>

	</syncfusion:RibbonButton>

	</syncfusion:RibbonBar>

	</syncfusion:RibbonTab>

	{% endhighlight %}

9. Add a region to the shell

	After creating View for the Module, register the view as Module using the below code.

	{% highlight c# %}

	[C#]

	public class HomeTabModules:IModule

	{

	private readonly IRegionManager regionManager;

	public HomeTabModules(IRegionManager regionManager)

	{

	this.regionManager = regionManager;

	}

	public void Initialize()

	{

	regionManager.Regions["Tabs"].Add(new HomeTab());

	}

	}

	{% endhighlight %}

	Then Run the project.RibbonTabModule will get added as one of the Module in the Shell.Similarly you can add the any number of Modules based on the complexity of the project.

	![](PatternsandPractices_images/PatternsandPractices_img2.jpeg)
