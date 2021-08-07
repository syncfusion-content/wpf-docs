---
layout: post
title: Symbol searching of stencil in WPF Diagram control | Syncfusion
description: Learn here all about searching of stencil symbols in Syncfusion WPF Diagram (SfDiagram) control ports.
platform: wpf
control: SfDiagram
documentation: ug
---

# Browse the symbols from the stencil in WPF Diagram (SfDiagram)

You can search for symbols in the stencil by entering the symbol name (e.g: "rectangle") into the search text box and clicking the search button. The symbols are resulted by matching the value of the `Name` property with the string entered in the search textbox. The [ShowSearchTextBox](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_ShowSearchTextBox) property of the `Stencil` is used to show or hide the search textbox in a stencil. 

{% tabs %}
{% highlight xaml %}

<!--Initialize the stencil-->
<syncfusion:Stencil x:Name="stencil" Width="250" ExpandMode="All"  ShowSearchTextBox="True">
    <!--Initialize the SymbolSource-->
    <syncfusion:Stencil.SymbolSource>               
        <!--Define the SymbolCollection-->
        <syncfusion:SymbolCollection>
            <syncfusion:NodeViewModel Key = "Basic Shapes" Name="Rectangle" OffsetX="100" OffsetY="100" UnitHeight="100" UnitWidth="100"  Shape="{StaticResource Rectangle}">
            </syncfusion:NodeViewModel>
        </syncfusion:SymbolCollection>
    </syncfusion:Stencil.SymbolSource>
    <syncfusion:Stencil.SymbolGroups>
        <syncfusion:SymbolGroups>
            <!--Separate groups based on the key-->
            <syncfusion:SymbolGroupProvider MappingName = "Key" />
        </syncfusion:SymbolGroups>
    </syncfusion:Stencil.SymbolGroups>
</syncfusion:Stencil>
{% endhighlight %}
{% endtabs %}

The following image shows the search result of the symbol.

 ![Symbol](Stencil_images/Stencil_Search_Textbox.GIF) 


## Search Tags

Stencil provides support to add keywords for a symbol that can be used when you search for it. Keywords can be added to the symbols using the [SearchTags](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolViewModel_SearchTags) property of [SymbolViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html) class.

{% highlight C# %}

// Defining tags to a symbol to make search easier.
var tags = new List() { "Process", "Input" };
var symbol1 = new SymbolViewModel()
{
    Name = "Source",
    SymbolTemplate = App.Current.Resources["Source"] as DataTemplate,
    SearchTags = tags
};
(stencil.SymbolSource as SymbolCollection).Add(symbol1);

{% endhighlight %}