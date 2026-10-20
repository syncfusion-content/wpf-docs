---
layout: post
title: Symbol Search in WPF Diagram | Syncfusion®
description: Search stencil symbols in Syncfusion® WPF Diagram using symbol names, search tags, and the built-in stencil search box.
platform: wpf
control: SfDiagram
documentation: ug
---

# Symbol Search in WPF Diagram

You can search for symbols in the stencil by entering the symbol name (e.g: "rectangle") into the search text box and clicking the search button. The Stencil returns symbols whose `Name` property matches the string entered in the search text box. Use the [`ShowSearchTextBox`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_ShowSearchTextBox) property to show or hide the search text box.

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

The following image shows the search result.

![Symbol](Stencil_images/Stencil_Search_Textbox.GIF) 

## Search Tags

You can add keywords to a symbol so it appears in search results when those keywords are typed. Use the [`SearchTags`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolViewModel_SearchTags) property of [SymbolViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html) to add keywords to a symbol. When the user types a query, the Stencil matches it against the symbol's `Name` and any `SearchTags`; matching is case-insensitive by default. Typing **Process** in the search box returns this symbol because **Process** is one of its `SearchTags`.

{% highlight c# %}

using System.Collections.Generic;
using Syncfusion.UI.Xaml.Diagram.Stencil;

// Define tags to make the symbol easier to find.
var tags = new List<string> { "Process", "Input" };
var symbol1 = new SymbolViewModel()
{
    Name = "Source",
    SymbolTemplate = App.Current.Resources["Source"] as DataTemplate,
    SearchTags = tags
};
(stencil.SymbolSource as SymbolCollection).Add(symbol1);

{% endhighlight %}