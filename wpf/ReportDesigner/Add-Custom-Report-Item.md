---
layout: post
title: Custom Report Item
description: Overview of Custom Report Item
platform: WPF
control: ReportDesigner
documentation: ug
---
## Overview

A custom report item allows users to add functionality that's not natively supported in RDL or extend the functionality of existing controls in RDL standard. The design-time component allows the custom report item to be defined and manipulated in design surface of ReportDesigner.


## Creating a custom report item design-time component
The design-time component is a control that can be used in Syncfusion Report Designer as like other built-in report items such as Textbox, Tablix, Rectangle etc. The following section provides guideline to create **Barcode** custom report item.

### Create report item assembly
1.	Open the Visual Studio and select class library project type, name the project as "Syncfusion.Extensions.BarcodeDesigner" for design-time component.
2.	Add the Syncfusion references "Syncfusion.ReportControls.Wpf" and "Syncfusion.ReportDesigner.WPF" to application.
3.	Add new class file "BarcodeCRIDesigner" by inheriting the `CustomReportItemDesigner` class. 

>Note:  Refer the above assemblies from the below installed location For report platform: %localappdata%\Syncfusion\ReportsSDK\Samples\Common\Assemblies and
For Essential Studio: C:\Program Files (x86)\Syncfusion\Essential Studio{{ site.releaseversion }}\Assemblies 

The following attributes must be set to BarcodeCRIDesigner class.

Attribute Name	|Description
----------|------------
Localized Name	|This is the attribute used to specify display name to use for the custom report item.
Custom Editor	|This is used to invoke property editor for custom report item.
CustomReportItem	|This is the attribute used to identify the type of the custom report item. The name must match the value of the <Name> attribute of the ReportItem element in the ReportExtension.config file.
ToolboxBitmap|	Icon that represents the custom report item in user interface.


{% highlight c# %}
namespace Syncfusion.Extensions.BarcodeDesigner
{
    [LocalizedName("Barcode")]
    [Editor(typeof(CustomEditor), typeof(ComponentEditor))]
    [ToolboxBitmap(typeof(BarcodeCRIDesigner), "Barcode.ico")]
    [CustomReportItem("Barcode")]

    public class BarcodeCRIDesigner : CustomReportItemDesigner
    {
        ...
        ...
    }
}
{% endhighlight %}

### Create the component class
The following sections guides you to initialize the custom report item design-time component and add new properties or access existing properties.

#### Initializing the component
The implementation of BarcodeCRIDesigner class should override the `InitializeNewComponent` method to create a new instance of your component's `CustomData` class and set it to default values.

{% highlight c# %}
public override void InitializeNewComponent()
{
    //Initialize UI elements required for the barcode item.
    SfBarcode barcodeControl = new SfBarcode();
    CustomData CustomData = new CustomData();
    //Initialize other required properties (SortExpressions, DataRow, Filters etc.) in CustomData
}
{% endhighlight %}

The `Draw` method is invoked when runtime editing or user interaction is performed on the custom report item. The panel type argument is used to add the new/edit UIElement to control when edit action like resize, drag-drop is performed, also the `ReportItemDrawParams` flag is used to identify the current action and the value is Default for new control initialization.

{% highlight c# %}
public override void Draw(Panel panel, ReportItemDrawParams dp)
{
    try
    {
        //Assign required properties to custom control like alignment, size etc..
        barcodeControl.HorizontalAlignment = System.Windows.HorizontalAlignment.Stretch;
        barcodeControl.VerticalAlignment = System.Windows.VerticalAlignment.Stretch;
        barcodeControl.Width = Width; //Width and height value is variant.
        barcodeControl.Height = Height;
        barcodeControl.Margin = new System.Windows.Thickness(5);
        
         if (dp.Flags == Windows.Reports.Designer.ReportItemDrawFlags.Default)
         {
             //Add the custom control to panel of designer
             panel.Children.Clear();
             panel.Children.Add(barcodeControl);
         }
     }
     catch { }
}
{% endhighlight %}

#### Add custom properties to component

New custom properties can be added to the component to include additional features that are not natively supported in RDL or to process the current control specific features. The newly created properties need to be added to the `CustomProperties` collection of report item to serialize within RDL definition. The following code sample describes adding a custom property "BarcodeValue" to set the barcode custom report item value property. 

{% highlight c# %}
[Browsable(true)]
public string BarcodeValue
{
    get
    {
        //Gets the value of a custom property from custom property collection
        return GetCustomProperty("BarcodeValue");
    }
    set
    {
        //Sets the value of a custom property to custom property collection
        SetCustomProperty("BarcodeValue", value);

         if (!isInternalChange)
         {
             //Updates the value of a barcode custom report item.
             UpdateBarcodeValue();
         }
     }
}

public string GetCustomProperty(string propertyname)
{
     if (CustomProperties != null)
     {
         foreach (KeyValuePair<string, string> property in CustomProperties)
         {
             if (property.Key == propertyname)
                 return (string)property.Value;
         }
     }
     return null;
}

public void SetCustomProperty(string propertyname, string value)
{
     if (!this.CustomProperties.ContainsKey(propertyname))
         this.CustomProperties.Add(propertyname, value);
     else
         this.CustomProperties[propertyname] = value;
}
{% endhighlight %}

#### Modifying component properties

You can modify the properties that are exposed by the design-time component by adding the custom properties dialog or property editors.
You can right-click the control in the design environment and select the properties in the shortcut menu to display a custom properties window.
The following code creates a local property to modify the design-time component property of the `CustomData` class.

{% highlight c# %}
[Browsable(true)]
public string DataSetName
{
    get
    {
        return CustomData.DataSetName;
    }
    set
    {
        CustomData.DataSetName = value;
    }
}
{% endhighlight %}

### Custom property editor

The `ComponentEditor` is used to create a custom properties editor dialog box to the design-time component. The custom property editor implementation should inherit from the ComponentEditor class, and it should create an instance of a dialog box that is used for property editing.
The following example shows an implementation of the class that is inherited from the `ComponentEditor` to display the custom property editor dialog box.

{% highlight c# %}
internal sealed class CustomEditor: ComponentEditor
{
     public override bool EditComponent(ITypeDescriptorContext context, object component)
    {
        BarcodeCRIDesigner designer = (BarcodeCRIDesigner)component;
        BarcodeProperties dialog = new BarcodeProperties();  //Custom property dialog
        dialog.DesignerComponent = designer;

         if ((bool)dialog.ShowDialog()) //Which allows you to edit value of custom properties in property dialog.
         {
             designer.Invalidate();
             return true;
         }
         else
         {
             return false;
         }
     }
}
{% endhighlight %}

The custom property editor dialog box invokes the Report Designer `ExpressionEditor` to edit any property as an expression.

{% highlight c# %}
private void Expression_Click(object sender, RoutedEventArgs e)
{
    //Displays expression editor dialog box when expression is clicked in custom property dialog.
    ExpressionEditor editor = new ExpressionEditor();
    objectnewValue = editor.EditValue(this, null, this.oldComboValue);
}
{% endhighlight %}


### Modifying the custom component style

The design-time component related style property changes can be handled and applied to the UIElement by overriding style related methods in the below table.

Method Name	|Description
----------|------------
OnFontChanged()|	Invokes when the font value of custom report item is changed.
OnTextAlignChanged()|	Invokes when the text alignment of custom report item is changed.
OnBackgroundColorChanged()|	Invokes when the background color of custom report item is changed.

In the following example, the change of font family property is handled in the custom component and style is applied to the barcode custom report item.

{% highlight c# %}
public override void OnFontChanged()
{
     if (!string.IsNullOrEmpty(this.Style.FontFamily) && !this.Style.FontFamily.StartsWith("="))
     {
         barcodeControl.FontFamily = (new System.Windows.Media.FontFamilyConverter().ConvertFromInvariantString(this.Style.FontFamily) as System.Windows.Media.FontFamily);
     }
}
{% endhighlight %}


### Build project

You can clean and build the extension project, it will generate the design-time component assembly "Syncfusion.Extensions.BarcodeDesigner.dll" in bin folder of the project. Copy the generated assembly to the Report Designer installed location (C:\Program Files (x86)\Syncfusion\Report Designer\ReportDesigner).

>Note: The installation path refers to the location where Syncfusion ReportDesigner is installed.



## Creating a custom report item run-time component

If you want preview the report in Report Designer means you will create the run-time component. 

The following Links are explain how to create custom report item run-time components.

[Create custom report item run time component](/wpf/ReportViewer/how-to/Add-Custom-Report-Item)
Describes how to create a custom report item run-time component in WPF Platform.

[Create custom report item run time component](/js/ReportViewer/Add-Custom-Report-Item)
Describes how to create a custom report item run-time component in Web ReportViewer Platform.



## Deploy a custom report item

To deploy a custom report item, you must modify the application configuration files or create "ReportExtensions.config" file and copy the design-time(Syncfusion.Extensions.BarcodeDesigner) assembly into the appropriate application folder for Report Designer. The deployment requires configuration to process the extensions, 

1.	The following "configSections" section is mandatory to process the extension inside the control, so add it as same as given in the below.

{% highlight xml %}
<configSections>
    <section name="ReportingExtensions" type="Syncfusion.Reporting.Extensions,  Syncfusion.ReportControls.WPF" allowLocation="true" allowDefinition="Everywhere" />
</configSections>
{% endhighlight %}

2.	We must add the tag `ReportItem` for all the newly added report Item types. It has following attributes.

Attribute Name	|Description
--------------|------------------
Name|	Name of your report Item that going to display in list.
Assembly|	Name of newly created report Item assembly.
Type	|Report Item class name with the namespace.

For report designer we need to replace the newly created assemblies and its dependent assemblies in the following location / appropriate application folders. 

C:\Program Files (x86)\Syncfusion\Report Designer\ReportDesigner

Also need to add the created / modified "ReportExtensions.config" file in above location with custom report item details.

{% highlight xml %}
    <configuration>
        <configSections>
            <section name="ReportingExtensions" type="Syncfusion.Reporting.Extensions,  Syncfusion.ReportControls.WPF" allowLocation="true" allowDefinition="Everywhere" />
        </configSections>

        <ReportingExtensions>
            <ReportItemDesigner>
                <ReportItem Name="Barcode" Assembly="Syncfusion.Extensions.BarcodeDesigner" Type="Syncfusion.Extensions.BarcodeDesigner.BarcodeCRIDesigner" />
            </ReportItemDesigner>
        </ReportingExtensions>
    </configuration>
{% endhighlight %}

Run the application, output with barcode custom report item is rendered as below. 
![](Add-Custom-Report-Item-images/Custom-Report-Item-1.png)

Shows barcode custom report item is added to built-in report item collections of report designer.
   {:.caption}

![](Add-Custom-Report-Item-images/Custom-Report-Item-2.png)

Custom property dialog of barcode custom report item.
   {:.caption}