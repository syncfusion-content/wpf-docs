---
layout: post
title: IntelliSense Support in WPF Syntax Editor control | Syncfusion
description: Learn about IntelliSense Support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# IntelliSense Support in WPF Syntax Editor

The Essential Edit for WPF provides Visual Studio like IntelliSense support. With IntelliSense support users can quickly choose the possible words while typing text in the control.

IntelliSense support in Edit WPF facilitates you to select possible words while typing text in the EditControl.

When you type the text in the EditControl, it displays a list of possible words in a popup. You can navigate, using Up and Down arrow keys or mouse and Scrollbar, to appropriate items. Select an item from the list to append to the text in the EditControl.

**Important features**

* **IntelliSense** in Edit WPF works in two modes namely **Auto** or **Custom**. 
  * **Auto** **mode**: This automatically generates the list of items to be displayed from the pre-built assemblies specified in `AssemblyReferences` property. This mode of operation is currently supported for C# and Visual Basic language respectively.
  * **Custom** **mode**: This enables the users to provide the list of items to be displayed in the IntelliSense.
* Exclusive properties in EditControl enable the users to customize the look and feel of the IntelliSense pop-up and its items.

This provides the facility to modify the characters on the selected item to be appended, to the text similar to that of Visual Studio IntelliSense settings. It also provides options to enable or disable appending text when space bar is pressed.

### Customization of IntelliSense modes

IntelliSense in Edit WPF works in two modes: Auto and Custom.  IntelliSense modes can be switched by using `IntelliSenseMode` property in EditControl class. It is an enum of the type of IntelliSenseMode. By default, IntelliSenseMode property is set to Auto.

**Auto mode**

In Auto mode, EditControl generates the IntelliSense list box items similar to Visual Studio based on the current language configurations (Lexem). IntelliSense also displays Types, Properties, Events and Methods from pre-built assemblies specified using AssemblyReferences property of EditControl class.

N> Auto IntelliSense mode is currently supported for C# and Visual Basic languages and will be extended to other markup languages supported by EditControl in forthcoming releases.

### Adding EditControl to the application

Add EditControl to the application and set its IntelliSenseMode to Auto by using the following code.

{% tabs %}

{% highlight XAML %}

<!--Adding EditControl to application and setting its IntelliSenseMode to Auto-->

<syncfusion:EditControl Background="White" DocumentLanguage="CSharp" Name="EditControl1" IntellisenseMode="Auto"/>


{% endhighlight %}

{% highlight C# %}

public partial class MainWindow : Window

{

ObservableCollection<Uri> uriList;

public MainWindow()

{

InitializeComponent();

uriList = new ObservableCollection<Uri>();

EditControl1.DocumentSource = "../../Source.cs";

EditControl1.AssemblyReferences = uriList;

}

private void Button_Click(object sender, RoutedEventArgs e)

{

OpenFileDialog fileDialog = new OpenFileDialog();

fileDialog.Filter = "Assembly Files (*.dll) | *.dll";

fileDialog.ShowDialog();

if (fileDialog.FileName.Trim() != string.Empty)

{

uriList.Add(new Uri(fileDialog.FileName));

}

}

}



{% endhighlight %}

{% endtabs %}

N> Having an INotifyCollectionChanged implemented collection as AssemblyReferences will update the IntelliSense items automatically when an assembly reference is added at runtime.

The following image displays the Intellisense Demo Window.

![IntelliSense support](IntelliSense-Support_images/IntelliSense-Support_img3.jpeg)


**Custom mode**

IntelliSense support in Edit WPF enables you to bind collections of your business object as an ItemsSource of IntelliSenseListBox. It also provides the flexibility to change the ItemTemplate of the IntelliSenseListBox to suite your business object or requirements.

This ensures that your business object is implemented from IIntelliSenseItem interface to your business object compatible with the IntelliSenseListBox. The EditControl have exclusive properties implemented to enable the users bind custom collections and apply custom ItemTemplates.

* **IntelliSenseMode**: Set `IntelliSenseMode` property to custom to apply a custom ItemsSource to IntelliSense.
* **IntelliSenseCustomItemsSource**: IEnumerable type of property to bind custom ItemsSource to IntelliSense ListBox.
* **IntelliSenseItemTemplate**: DataTemplate type of property to apply custom **ItemTemplate to IntelliSense ListBox.

### Creating DataTemplate in the ResourceDictionary

Create DataTemplate in the ResourceDictionary to apply it as `IntellisenseItemTemplate` property of EditControl by using the following code.

{% tabs %}

{% highlight XAML %}

<DataTemplate x:Key="CustomIntelliSenseItemTemplate">

<Grid>

<Grid.ColumnDefinitions>

<ColumnDefinition Width="Auto"/>

<ColumnDefinition Width="*"/>

</Grid.ColumnDefinitions>

<Image Source="{Binding Icon}" MaxHeight="16" MaxWidth="16" Margin="3"/>

<TextBlock Text="{Binding Text}" Grid.Column="1" Margin="3"/>

</Grid>

</DataTemplate>



{% endhighlight %}

{% endtabs %}

Apply `IntellisenseMode` and `IntellisenseItemTemplate` properties by using the following code.

{% tabs %}

{% highlight XAML %}

<!--Adding EditControl to application and setting its IntelliSenseMode to Custom-->

<syncfusion:EditControl Background="White" Name="EditControl1"  IntellisenseMode="Custom"

IntellisenseItemTemplate="{StaticResource 

CustomIntelliSenseItemTemplate}"/>



{% endhighlight %}

{% endtabs %}

### Creating a custom business object

Create a Custom Business Object implemented using IIntellisenseItem interface by using the following code.

{% tabs %}

{% highlight C# %}
/// <summary>

/// Business object implemented from IIntelliSenseItem interface in 

/// Syncfusion.Windows.Edit namespace

/// </summary>

public class CustomIntelliSenseItem : IIntellisenseItem

{


/// <summary>

/// Gets or sets a value indicating Icon to be displayed in the IntelliSenseListBox

/// </summary>

public ImageSource Icon

{

get;

set;

}

/// <summary>

/// Gets or sets a value indicating Text to be displayed in the IntelliSenseListBox

/// </summary>

public string Text

{

get;

set;

}

/// <summary>

/// Gets or sets a collection of sub-items to be displayed

/// </summary>

public IEnumerable<IIntellisenseItem> NestedItems

{

get;

set;

}


}



{% endhighlight %}

{% endtabs %}

### Creating a custom collection of the business object

Now, create a Custom Collection of the Business Object and set as Custom ItemsSource using `IntellisenseCustomItemsSource` property by using the following code.

{% tabs %}

{% highlight C# %}

// Initializing custom business object collection 

ObservableCollection<CustomIntelliSenseItem> customItems = new

ObservableCollection<CustomIntelliSenseItem>();

customItems.Add(new CustomIntelliSenseItem()

{

Text = "Syncfusion",

Icon = new BitmapImage(new Uri("/CustomIntelliSenseDemo;component/Resources/syncfusion.png", UriKind.Relative))

});

customItems.Add(new CustomIntelliSenseItem()

{

Text = "Silverlight",

Icon = new BitmapImage(new Uri("/CustomIntelliSenseDemo;component/Resources/silverlight.png", UriKind.Relative))

});

customItems.Add(new CustomIntelliSenseItem()

{

Text = "WPF",

Icon = new BitmapImage(new Uri("/CustomIntelliSenseDemo;component/Resources/wpf.png", UriKind.Relative))

});

// Applying custom business object collection as IntelliSenseCustomItemsSource

EditControl1.IntellisenseCustomItemsSource = customItems;





{% endhighlight %}

{% endtabs %}

When the code runs, the following output displays.

The following image displays the Custom Intellisense Demo Window.

![IntelliSense support](IntelliSense-Support_images/IntelliSense-Support_img4.jpeg)


### Customizing IntelliSense list box style

The EditControl enables the users to customize the look and feel of the IntelliSense listbox by applying custom style to the IntelliSense listbox. The `IntelliSenseBoxStyle` property of EditControl class can be used to apply custom style for IntelliSense listbox.

Customize the IntelliSense List Box Style, by using the following code.

{% tabs %}

{% highlight XAML %}

<Style x:Key="ListBoxItemStyle" TargetType="ListBoxItem">

<Setter Property="FontSize" Value="11"/>

<Setter Property="FontFamily" Value="Verdana"/>

<Setter Property="FocusVisualStyle" Value="{x:Null}" />

<Setter Property="syncfusion:SkinStorage.VisualStyle" Value="Default"/>

</Style>

<Style x:Key="ListBoxStyle" TargetType="ListBox">

<Setter Property="ItemContainerStyle" Value="{StaticResource ListBoxItemStyle}"/>

<Setter Property="syncfusion:SkinStorage.VisualStyle" Value="Default"/>

<Setter Property="Background" Value="Aqua"/>

</Style>

<syncfusion:EditControl Name="EditControl1"  IntellisenseBoxStyle="{StaticResource ListBoxStyle}"/>



{% endhighlight %}

{% endtabs %}

The following figure displays displays the window that appears after applying IntelliSenseBox Style.

![Customizing intellisense list box style](IntelliSense-Support_images/IntelliSense-Support_img5.jpeg)


### Applying multi-level IntelliSense items in custom mode

As mentioned in earlier topics, EditControl supports applying custom collection of business objects as IntelliSense, when the business objects are implemented using IIntelliSenseItem interface. This IIntelliSenseItem interface has a `NestedItems` property which can be used to display sub items in IntelliSense. The EditControl has a property under CurrentLanguage, a `DrillDownChar` property of the type char to specify on which character press, the sub-items are to be displayed in IntelliSense.  The default value of DrillDownChar is **“.”** (Periods)  and when **“.”(**Periods) key is pressed, the EditControl will automatically get the collection from the NestedItems property and displays it in the EditControl.

Create a Custom IntelliSense for tables and fields for SQL language by using the following code.

{% tabs %}

{% highlight XAML %}

<!--Resources-->

<DataTemplate x:Key="CustomIntelliSenseItemTemplate">

<TextBlock Text="{Binding Text}" Margin="3"/>

</DataTemplate>

<!--Adding EditControl to application and setting its IntelliSenseMode to Auto-->

<syncfusion:EditControl Background="White" Name="EditControl1" DocumentLanguage="SQL"  IntellisenseMode="Custom" 

IntellisenseItemTemplate="{StaticResource CustomIntelliSenseItemTemplate}"/>



{% endhighlight %}

{% highlight C# %}
/// <summary>

/// Business object implemented from IIntelliSenseItem interface in 

/// Syncfusion.Windows.Edit namespace

/// </summary>

public class CustomIntelliSenseItem : IIntellisenseItem

{



/// <summary>

/// Gets or sets a value indicating Icon to be displayed in the IntelliSenseListBox

/// </summary>

public ImageSource Icon

{

get;

set;

}

/// <summary>

/// Gets or sets a value indicating Text to be displayed in the IntelliSenseListBox

/// </summary>

public string Text

{

get;

set;

}

/// <summary>

/// Gets or sets a collection of sub-items to be displayed

/// </summary>

public IEnumerable<IIntellisenseItem> NestedItems

{

get;

set;

}


}



{% endhighlight %}

{% highlight C# %}

ObservableCollection<CustomIntelliSenseItem> customItems = new

ObservableCollection<CustomIntelliSenseItem>();

//Intializing sub-items for products

ObservableCollection<CustomIntelliSenseItem> productsSubItem = new

ObservableCollection<CustomIntelliSenseItem>();

productsSubItem.Add(new CustomIntelliSenseItem() { Text = "ID" });

productsSubItem.Add(new CustomIntelliSenseItem() { Text = "Name" });

productsSubItem.Add(new CustomIntelliSenseItem() { Text = "Manufacturer" });

productsSubItem.Add(new CustomIntelliSenseItem() { Text = "Price" });

productsSubItem.Add(new CustomIntelliSenseItem() { Text = "OrderQuantity" });

productsSubItem.Add(new CustomIntelliSenseItem() { Text = "Units" });

//Intializing sub-items for employee

ObservableCollection<CustomIntelliSenseItem> employeeSubItem = new

ObservableCollection<CustomIntelliSenseItem>();

employeeSubItem.Add(new CustomIntelliSenseItem() { Text = "ID" });

employeeSubItem.Add(new CustomIntelliSenseItem() { Text = "Name" });

employeeSubItem.Add(new CustomIntelliSenseItem() { Text = "DOB" });

employeeSubItem.Add(new CustomIntelliSenseItem() { Text = "City" });

employeeSubItem.Add(new CustomIntelliSenseItem() { Text = "ContactNumber" });

//Intializing sub-items for customer

ObservableCollection<CustomIntelliSenseItem> customerSubItem = new

ObservableCollection<CustomIntelliSenseItem>();

customerSubItem.Add(new CustomIntelliSenseItem() { Text = "ID" });

customerSubItem.Add(new CustomIntelliSenseItem() { Text = "Name" });

customerSubItem.Add(new CustomIntelliSenseItem() { Text = "City" });

customerSubItem.Add(new CustomIntelliSenseItem() { Text = "State" });

customerSubItem.Add(new CustomIntelliSenseItem() { Text = "Country" });

customerSubItem.Add(new CustomIntelliSenseItem() { Text = "ContactNumber" });

//adding items to main collection

customItems.Add(new CustomIntelliSenseItem()

{

Text = "Products",

NestedItems =

productsSubItem

});

customItems.Add(new CustomIntelliSenseItem()

{

Text = "Employee",

NestedItems =

employeeSubItem

});

customItems.Add(new CustomIntelliSenseItem()

{

Text = "Customer",

NestedItems =

customerSubItem

});

// Applying custom business object collection as IntelliSenseCustomItemsSource

EditControl1.IntellisenseCustomItemsSource = customItems;



{% endhighlight %}

{% endtabs %}
The following screenshot illustrates IntelliSense displaying first-level of items from custom collection.

![IntelliSense displaying first-level of items from custom collection](IntelliSense-Support_images/IntelliSense-Support_img6.jpeg)


The following screenshot illustrates IntelliSense displaying sub-items from selected item.

![IntelliSense displaying sub-items from selected item](IntelliSense-Support_images/IntelliSense-Support_img7.jpeg)


Following classes in EditControl will be helpful to perform various operations related to IntelliSense.

<table>
<tr>
<td>
Name of Property<br/><br/></td><td>
Description<br/><br/></td><td>
Type of Property<br/><br/></td><td>
Value It Accepts<br/><br/></td></tr>
<tr>
<td>
EnableIntelliSense<br/><br/></td><td>
Gets or sets a value indicating if IntelliSense Support has to be enabled or disabled.<br/><br/></td><td>
Boolean<br/><br/></td><td>
True/false<br/><br/></td></tr>
<tr>
<td>
IntelliSenseMode<br/><br/></td><td>
Gets or sets a value representing IntelliSense mode of operations.<br/><br/></td><td>
IntelliSenseMode<br/><br/></td><td>
IntellisenseMode.Auto/IntellisenseMode.Custom<br/><br/></td></tr>
<tr>
<td>
IntelliSenseCustomItemsSource<br/><br/></td><td>
To specify the custom collection of business objects to be displayed in custom IntelliSense.<br/><br/></td><td>
IEnumerable<br/><br/></td><td>
Any collection of items implemented using IIntellisenseItem      <br/><br/></td></tr>
<tr>
<td>
IntelliSenseBoxStyle<br/><br/></td><td>
IntelliSense.<br/><br/></td><td>
Style<br/><br/></td><td>
Style object<br/><br/></td></tr>
<tr>
<td>
IntelliSenseItemTemplate<br/><br/></td><td>
IntelliSense.<br/><br/></td><td>
DataTemplate<br/><br/></td><td>
DataTemplate object<br/><br/></td></tr>
</table>


Following classes in LanguageBase will be helpful to perform various operations related to IntelliSense specific support and custom languages. These properties can be modified in custom language classes inherited from LanguageBase or ProceduralLanguageBase or MarkupLanguageBase class. It can also be modified using `CurrentLanguage` property of EditControl class.



<table>
<tr>
<td>
Name of the property<br/><br/></td><td>
Description<br/><br/></td><td>
Type of the property<br/><br/></td></tr>
<tr>
<td>
DrillDownChar<br/><br/></td><td>
The character specified is used to drill down to nested items. When the user presses the corresponding key, IntelliSense drills down and displays the sub-items in the IntelliSense.        <br/><br/></td><td>
Char<br/><br/></td></tr>
<tr>
<td>
IntelliSenseCommitCharacters<br/><br/></td><td>
Specifies the characters when used. The IntelliSense should append the selected IntelliSense item to EditControl’s text.<br/><br/></td><td>
String<br/><br/></td></tr>
<tr>
<td>
CommitsIntelliSenseItemOnSpaceBar<br/><br/></td><td>
Specifies if the selected IntelliSense item to be appended to the EditControl’s text when a space bar is pressed.<br/><br/></td><td>
Boolean<br/><br/></td></tr>
<tr>
<td>
SupportsIntelliSense<br/><br/></td><td>
To allow or restrict IntelliSense auto mode in custom languages.<br/><br/></td><td>
Boolean<br/><br/></td></tr>
</table>

**Events**

<table>
<tr>
<td>
Event<br/><br/></td><td>
Usage<br/><br/></td><td>
Handler Type<br/><br/></td><td>
Handler<br/><br/></td></tr>
<tr>
<td>
IntelliSenseBoxOpening<br/><br/></td><td>
This event gets triggered before the IntelliSense pop-up is displayed. <br/><br/></td><td>
IntelliSenseBoxEventHandler<br/><br/></td><td>
Set `IsCancel` property in the EventArgs to cancel displaying of IntelliSense popup.<br/><br/></td></tr>
<tr>
<td>
IntelliSenseDrillDown<br/><br/></td><td>
This event gets triggered when a DrillDownChar specified is encountered.<br/><br/></td><td>
IntelliSenseBoxEventHandler<br/><br/></td><td>
Set IsCancel property in the EventArgs to cancel displaying of IntelliSense popup.<br/><br/></td></tr>
</table>

IntelliSenseBoxEventArgs contains following arguments.

<table>
<tr>
<td>
Argument<br/><br/></td><td>
Usage<br/><br/></td></tr>
<tr>
<td>
Assemblies<br/><br/></td><td>
Contains the list of assemblies included as AssemblyReferences.<br/><br/></td></tr>
<tr>
<td>
Cancel<br/><br/></td><td>
A boolean argument can be used to cancel the event.<br/><br/></td></tr>
<tr>
<td>
CursorIndex<br/><br/></td><td>
Contains current Cursor Index where the event is triggered.<br/><br/></td></tr>
<tr>
<td>
ItemsSource<br/><br/></td><td>
Contains the ItemsSource to be applied to the IntelliSense, it can also be changed if there are any Custom Filtrations to be done in the event.<br/><br/></td></tr>
<tr>
<td>
LineIndex<br/><br/></td><td>
Contains current Line Index where the event is triggered<br/><br/>(0 based values).<br/><br/></td></tr>
</table>
