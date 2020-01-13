---
layout: post
title: Getting Started with WPF PropertyGrid control | Syncfusion
description: Explore how to create and use basic features of Syncfusion WPF property grid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Getting started with WPF CurrencyTextBox

This section explains how to create a WPF [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control and its features.

## Visual structure

1. ButtonPanel Items
2. Group Button — Used to group the properties.
3. Sort Button — Used to sort the properties in ascending or descending order.
4. Search Box — Used to filter properties.
5. ToolTip — Displays the name and type of the property on mouse over.
6. Description Panel — Gives a short description about the property.

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#currencytextbox) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages)

## Adding WPF CurrencyTextBox via designer

You can add the [CurrencyTextBox](https://www.syncfusion.com/wpf-ui-controls/currency-textbox) control to an application by dragging it from the toolbox to a view of the designer. The following dependent assembly will be added automatically:

* Syncfusion.PropertyGrid.Wpf
* Syncfusion.Shared.WPF
* Syncfusion.Tools.Wpf

![CurrencyTextBox Control added by designer](Getting-Started_images/Getting-Started_img2.png)

## Adding WPF CurrencyTextBox via XAML

To add the `CurrencyTextBox` control manually in XAML, follow these steps:
1. Create a new WPF project in Visual Studio.

2. Add the  following assembly references to the project,
   * Syncfusion.PropertyGrid.Wpf
   * Syncfusion.Shared.WPF
   * Syncfusion.Tools.Wpf

 
3. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** and declare the `CurrencyTextBox` control in XAML page.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid  Name="propertyGrid1" Height="400" Width="300" >
</syncfusion:PropertyGrid>

{% endhighlight %}
{% endtabs %}

## Adding WPF CurrencyTextBox via C\#

To add the `CurrencyTextBox` control manually in C#, follow these steps:

1. Create a new WPF application via Visual Studio.

2. Add the  following assembly references to the project,
    * Syncfusion.PropertyGrid.Wpf
    * Syncfusion.Shared.WPF
    *  Syncfusion.Tools.Wpf

3. Include the required namespace.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.PropertyGrid;

{% endhighlight %}
{% endtabs %}

4. Create an instance of CurrencyTextBox and add it to the window.

{% tabs %}
{% highlight C# %}

    // Creating an instance of CurrencyTextBox control

    PropertyGrid propertyGrid1 = new PropertyGrid();

    // Setting height and width to CurrencyTextBox

    propertyGrid1.Height = 300;
    propertyGrid1.Width = 200;

    //Adding CurrencyTextBox as window content

    this.Content = propertyGrid1;

{% endhighlight %}
{% endtabs %}

![CurrencyTextBox control added to Window by code](Getting-Started_images/Getting-Started_img15.png)


## Populating the properties

The `PropertyGrid` allows to display the browsing and editing properties of the particular object specified by the [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.Property~SelectedObject.html) property.

The properties of the objects can be populated in the following ways,

### Populating the properties through XAML

The user can populate the properties of the Object using XAML

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid  Name="propertyGrid1" Height="500" Width="300" >
<syncfusion:PropertyGrid.SelectedObject>
<Button> </Button>
</syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% endtabs %}

In the above code snippet, the [Button](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.button?view=netframework-4.8) is set as `SelectedObject` for the `PropertyGrid`. Thus, the `PropertyGrid` shows all the properties available in the `Button`. 


### Populating the properties through C#

The user can sets the object to the `SelectedObject` property using C# to populate the properties in the `PropertyGrid`.

{% tabs %}
{% highlight c# %}

PropertyGrid pGrid = new PropertyGrid();
pGrid.SelectedObject = new Button();

{% endhighlight %}
{% endtabs %}


![ Populating the Button`s properties into the PropertyGrid control](Getting-Started_images/Getting-Started_img5.png)

## Name and description of properties

You can edit the custom object properties using the `PropertyGrid`. The following example illustrates how to edit the custom object properties.

Create a class called `Person` and define the properties.




















## Creating the control through Visual Studio

To create the PropertyGrid control:

1. Drag and drop the PropertyGrid from the Visual Studio Toolbox as shown below.

   ![image](Getting-Started_images/Getting-Started_img1.png)

   ![image](Getting-Started_images/Getting-Started_img2.png)

2. Configure the properties of the PropertyGrid using the VS Properties window.

## Creating the control through Expression Blend

The PropertyGrid control can also be created and configured using Microsoft Expression Blend. To create the control through Expression Blend:

1. Create a WPF project in Expression Blend and add the reference to the following assemblies:
   
   1. Syncfusion.Tools.Wpf
   2. Syncfusion.Shared.Wpf
   3. Syncfusion.PropertyGrid.Wpf
   4. Syncfusion.Core
   
2. Search for the PropertyGrid in the Toolbox.

   ![image](Getting-Started_images/Getting-Started_img3.png)

3. Drag and drop the PropertyGrid into the designer. The PropertyGrid control is created as shown in the following screenshot. 

   ![image](Getting-Started_images/Getting-Started_img4.png)

The user can customize any part of the PropertyGrid using the template editing feature in Expression Blend. 

## Populating the properties

This section explains how to populate the properties of any selected object.

### Through XAML

The user can populate the properties of selected object using XAML.

The following code snippet shows how to create the PropertyGrid control in XAML. 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid  Name="propertyGrid1" Height="500" Width="300" >
<syncfusion:PropertyGrid.SelectedObject>
<Button/>
</syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% endtabs %}

In the above code snippet, the Button is set as SelectedObject for the PropertyGrid; thus, the PropertyGrid shows all the properties available in the Button. 

This will create the property as shown in the following screenshot:



### Through C&#35

To create the PropertyGrid control:

1. Include the following namespace to the using directives list for creating the PropertyGrid control in C#.

{% tabs %}
{% highlight c# %}

using Syncfusion.Windows.PropertyGrid;

{% endhighlight %}
{% endtabs %}

2. Create the PropertyGrid as follows:

{% tabs %}
{% highlight c# %}

PropertyGrid pGrid = new PropertyGrid();
pGrid.SelectedObject = new Button();

{% endhighlight %}
{% endtabs %}

### Name and description of properties

You can edit the custom object properties using the PropertyGrid. The following example illustrates how to edit the custom object properties.

1. Create a class called Person and define the properties. 

{% tabs %}
{% highlight c# %}

[TypeConverter(typeof(ExpandableObjects))]
public class Person
{
	public Person()
	{            
		Name = "Johnson";
		Age = 30;
		Mobile = 91983467382;
		Email = "carljohnson@gta.com";
		ID = "0005A";
		DOB = new DateTime(1987, 10, 16);           
	}
	[CategoryAttribute("Identity")]
	[DisplayNameAttribute("Name")]
	[DescriptionAttribute("Name of the actual person.")]
	public string Name
	{
		get;
		set;
	}
	[CategoryAttribute("Identity")]
	[DisplayNameAttribute("ID")]
	[DescriptionAttribute("ID of the actual person.")]
	public string ID
	{
		get;
		set;
	}
	[CategoryAttribute("Identity")]
	[DisplayNameAttribute("Date of Birth")]
	[DescriptionAttribute("Birth date of the actual person.")]
	public DateTime DOB
	{
		get;
		set;
	}
	[CategoryAttribute("Contact Details")]
	[DisplayNameAttribute("Email ID")]
	[DescriptionAttribute("Email address of the actual person.")]
	public string Email
	{
		get;
		set;
	}
    [CategoryAttribute("Contact Details")]
	[DisplayNameAttribute("Mobile Number")]
	[DescriptionAttribute("Contact number of the actual person.")]
	public long Mobile
	{
		get;
		set;
	}
	[CategoryAttribute("Identity")]
	[DisplayNameAttribute("Age")]
	[DescriptionAttribute("Age of the actual person.")]
	public int Age
	{
		get;
		set;
	}
    [CategoryAttribute("Identity")]
	[DisplayNameAttribute("Gender")]
	[DescriptionAttribute("Gender information of the actual person.")]
	public Gender Gender
	{
		get;
		set;
	}
	[CategoryAttribute("Location")]
	[DisplayNameAttribute("Country")]
	[DescriptionAttribute("Country where the person is located.")]
	public Country Country
	{
		get;
		set;
	}       
}
public enum Country
{
	UnitedStates,
	Germany,
	Canada,
}

{% endhighlight %}
{% endtabs %}

2. Set the SelectedObject of the property to the instance of the class Person.

{% tabs %}
{% highlight c# %}

PropertyGrid pGrid = new PropertyGrid();
pGrid.SelectedObject = new Person();

{% endhighlight %}
{% endtabs %}

3. The PropertyGrid will be generated as shown in the following screenshot.

![Property grid exploring properties of Person class](Getting-Started_images/Getting-Started_img6.png)

### Edit properties using custom editor

The PropertyGrid also provides custom editor support. The following example shows how to create the custom editor.

1. Define the custom editor with the ITypeEditor interface as follows:

{% tabs %}
{% highlight c# %}

public class UpDownEditor : ITypeEditor
{
	public void Attach(PropertyViewItem property, PropertyItem info)
	{
		if (info.CanWrite)
		{
			var binding = new Binding("Value")
			{
				Mode = BindingMode.TwoWay,
				Source = info,
				ValidatesOnExceptions = true,
				ValidatesOnDataErrors = true
			};
			BindingOperations.SetBinding(upDown, UpDown.ValueProperty, binding);
		}
		else
		{
			upDown.AllowEdit = false;
			var binding = new Binding("Value")
			{
				Source = info,
				ValidatesOnExceptions = true,
				ValidatesOnDataErrors = true
			};
			BindingOperations.SetBinding(upDown, UpDown.ValueProperty, binding);
		}
	}
    UpDown upDown;
	public object Create(PropertyInfo propertyInfo)
	{
		upDown = new UpDown()
		{
			ApplyZeroColor = false
		};
		if (propertyInfo.Name == "FontSize" || propertyInfo.Name == "MinWidth" || propertyInfo.Name == "MinHeight" || propertyInfo.Name == "MaxHeight" || propertyInfo.Name == "MaxWidth" ||
		propertyInfo.Name == "Height" || propertyInfo.Name == "Width" || propertyInfo.Name == "ActualWidth" || propertyInfo.Name == "ActualHeight")
		{
			upDown.MinValue = 0;
		}
		if (propertyInfo.Name == "Opacity")
		{
			upDown.MinValue = 0.0;
			upDown.MaxValue = 1.0;
			upDown.Step = 0.1;
		}
		return upDown;
	}
	public void Detach(PropertyViewItem property)
	{
		throw new NotImplementedException();
	}
}

{% endhighlight %}
{% endtabs %}

The UpDownEditor given in the above code snippet is used to edit the double values. Since the UpDown control has features like scroll buttons to increase the value, it makes it easier to edit the property values of type double. 

2. Create an instance of Customer Editor with this UpDownEditor as follows:

{% tabs %}
{% highlight c# %}

CustomEditor upDownEditor = new CustomEditor() 
{ 
	HasPropertyType = true, 			
	PropertyType = typeof(double), 
	Editor = new UpDownEditor() 
};

{% endhighlight %}
{% endtabs %}

3. Add this custom editor instance to the CustomEditorCollection property of the PropertyGrid as follows:

{% tabs %}
{% highlight c# %}
 
pgridInstance.CustomEditorCollection.Add(brusheditor); 

{% endhighlight %}
{% endtabs %}

The PropertyGrid displays the UpDownEditor as shown in the following screenshot for the double type values.

![image](Getting-Started_images/Getting-Started_img7.png)

## Visual styles

The PropertyGrid control supports the following built-in visual styles:

* Office2007Blue
* Office2007Black
* Office2007Silver
* Office2010Blue
* Office2010Black
* Office2010Silver
* Blend
* Metro
* Transparent

The visual style can be applied in XAML as follows:

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid
syncfusion:SkinStorage.VisualStyle="Office2010Blue" />   

{% endhighlight %}
{% endtabs %}

The PropertyGrid control gets the Office2010Blue look.

The visual styles can be applied in C# as follows:

{% tabs %}
{% highlight c# %}

SkinStorage.SetVisualStyle(propertyGridInstance, "Office2010Blue");

{% endhighlight %}
{% endtabs %}

## Structure of the PropertyGrid control

![image](Getting-Started_images/Getting-Started_img8.png)

* Button panel—Shows the GroupButton and SortButton to help the user at run time.
* GroupButton—Groups the properties based on Category attribute of the property.
* SortButton—Displays the properties in sorting order in PropertyGrid.
* PropertyGrid—Lists all the properties

## Adding PropertyGrid to an application

The PropertyGrid control can be added to an application by using Visual Studio and Blend.

### Adding through C#

Following are the steps to add the PropertyGrid control by using VisualStudio in C#:

1. Open Visual Studio. On the File menu, select New -> Project. This opens the New Project Dialog box.

   ![image](Getting-Started_images/Getting-Started_img9.png)

2. On the Project Dialog window, select WPF Application, in the Name field, type the name of the project, and then click OK.

3. Add the following reference with the sample project:
   1. Syncfusion.PropertyGrid.Wpf.dll
   2. Syncfusion.Shared.Wpf.dll
   3. Syncfusion.Tools.Wpf.dll
   
4. Click the C# file and add the PropertyGrid control to your application as follows.

{% tabs %}
{% highlight c# %}

Syncfusion.Windows.PropertyGrid.PropertyGrid propertyGrid = new Syncfusion.Windows.PropertyGrid.PropertyGrid();
propertyGrid.Height = 250;
propertyGrid.Width = 250;
propertyGrid.BorderBrush = new SolidColorBrush(Colors.Gray);
propertyGrid.BorderThickness = new Thickness(2);
propertyGrid.SelectedObject = new Button();
LayoutRoot.Children.Add(propertyGrid);

{% endhighlight %}
{% endtabs %}

![image](Getting-Started_images/Getting-Started_img10.png)


### Adding through XAML

Following are the steps to add the PropertyGrid control by using Visual Studio in XAML.

1. Create a new application in Visual Studio.
2. In the Visual Studio Toolbox, click Syncfusion WPF Toolbox tab and select PropertyGrid.
3. Drag-and-drop the PropertyGrid to Design View, to add PropertyGrid to your application.
4. In the properties window, customize the properties of the PropertyGrid.

{% tabs %}
{% highlight xaml %}

<Window x:Class="PropertyGridSample.MainWindow" xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"       xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"        Title="MainWindow" Height="350" Width="525"        xmlns:syncfusion="clr-namespace:Syncfusion.Windows.PropertyGrid;assembly=Syncfusion.PropertyGrid.Wpf">
<Grid x:Name="LayoutRoot">
<syncfusion:PropertyGrid Margin="109,32,117,47" SelectedObject="{Binding ElementName=LayoutRoot}" BorderBrush="Gray" BorderThickness="2"/>        
</Grid>
</Window>

{% endhighlight %}
{% endtabs %}

![image](Getting-Started_images/Getting-Started_img11.png)

### Adding through Blend

Following are the steps to add the PropertyGrid control by using Blend. 

1. Open Blend, On the File Menu click New Project. This opens the New Project dialog box.

   ![image](Getting-Started_images/Getting-Started_img12.png)

2. In the Project type’s panel, select WPF application and then click OK.

   ![image](Getting-Started_images/Getting-Started_img13.png)

3. Add the following Reference with the sample project.

   1. Syncfusion.PropertyGrid.Wpf.dll
   2. Syncfusion.Shared.Wpf.dll
   3. Syncfusion.Tools.Wpf.dll
   4. On the Window menu, select Assets. This opens the Assets Library dialog box.
   5. In the Search box, type PropertyGrid. This displays the search results.
   6. Drag the PropertyGrid control to Design View.

![image](Getting-Started_images/Getting-Started_img14.png)

## ToolTip

ToolTips are used to show the information about the segment, when you mouse over on the segment.  You can show or hide the tooltip for the properties in the PropertyGrid by handling EnableToolTip Property. By default, `EnableToolTip` property is set to true.

{% tabs %}

{% highlight c# %}

// to hide the tooltip for the properties
this.propertygrid1.EnableToolTip = false;  

{% endhighlight %}

{% highlight vb %}

' to hide the tooltip for the properties
Me.propertygrid1.EnableToolTip = False

{% endhighlight %}

{% endtabs %}
