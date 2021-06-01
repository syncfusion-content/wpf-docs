---
layout: post
title: Styles and Templates in WPF TreeGrid control | Syncfusion
description: Learn here all about Styles and Templates support in Syncfusion WPF TreeGrid (SfTreeGrid) control and more.
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Styles and Templates in WPF TreeGrid (SfTreeGrid)

## Styling Column Header

The header cell can be customized by writing style of TargetType [TreeGridHeaderCellControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridHeaderCell.html). You can set to particular SfTreeGrid by setting [SfTreeGrid.HeaderStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_HeaderStyle) property and the particular column can be styled by setting [TreeGridColumn.HeaderStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_HeaderStyleProperty) property.

N> `TreeGridColumn.HeaderStyle` takes higher priority than `SfTreeGrid.HeaderStyle` property.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <Style TargetType="syncfusion:TreeGridHeaderCell" x:Key="headerStyle">
        <Setter Property="FontWeight" Value="Bold"/>
        <Setter Property="FontSize" Value="14"/>
        <Setter Property="Background" Value="LightPink"/>
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
</Window.Resources>

<syncfusion:SfTreeGrid Name="treeGrid" Grid.Column="1" Grid.Row="1"
                                HeaderStyle="{StaticResource headerStyle}"
                                AutoExpandMode="RootNodesExpanded"
                                AutoGenerateColumns="False"
                                ChildPropertyName="Children"
                                ItemsSource="{Binding EmployeeDetails}"
                                LiveNodeUpdateMode="AllowDataShaping">
{% endhighlight %}
{% endtabs %}

![Customizing Header Cell in WPF TreeGrid Column](Styles-and-Templates_images/wpf-treegrid-header-cell-customization.png)

### Styling Stacked Headers

The appearance of stacked header can be customized by writing style of TargetType [TreeGridStackedHeaderCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridStackedHeaderCell.html).

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <Style TargetType="syncfusion:TreeGridStackedHeaderCell">
        <Setter Property="FontWeight" Value="Bold"/>
        <Setter Property="FontSize" Value="14"/>
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
</Window.Resources>
{% endhighlight %}
{% endtabs %}

![Customizing Stacked Header in WPF TreeGrid Column](Styles-and-Templates_images/wpf-treegrid-stacked-headers.png)

### Setting Different Style for Each Stacked Header

You can apply the different style to stacked header by overriding the [default renderer](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Cells.TreeGridCellRendererCollection.html#Syncfusion_UI_Xaml_TreeGrid_Cells_TreeGridCellRendererCollection_ContainsValue_Syncfusion_UI_Xaml_TreeGrid_Cells_TreeGridCellRendererBase_) of StackedHeader.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style x:Key="style1" TargetType="syncfusion:TreeGridStackedHeaderCell">
        <Setter Property="Background" Value="LightBlue" />
        <Setter Property="FontFamily" Value="Segoe UI" />
        <Setter Property="FontStyle" Value="Italic" />
        <Setter Property="FontWeight" Value="Bold"/>
    </Style>
    <Style x:Key="style2" TargetType="syncfusion:TreeGridStackedHeaderCell">
        <Setter Property="Background" Value="Bisque" />
        <Setter Property="FontFamily" Value="Courier New" />
        <Setter Property="FontStyle" Value="Oblique" />
        <Setter Property="FontWeight" Value="Bold"/>
    </Style>
    <Style x:Key="style3" TargetType="syncfusion:TreeGridStackedHeaderCell">
        <Setter Property="Background" Value="LightPink" />
        <Setter Property="FontFamily" Value="Segoe UI" />
        <Setter Property="FontStyle" Value="Oblique" />
        <Setter Property="FontWeight" Value="Bold"/>
    </Style>
</Application.Resources>
{% endhighlight %}
{% highlight c# %}
//Default TreeGridStackedCellRenderer is removed.
this.treeGrid.CellRenderers.Remove("StackedHeader");
//Customized TreeGridStackedCellRenderer is added.
this.treeGrid.CellRenderers.Add("StackedHeader", new TreeGridCustomStackedRenderer());

public class TreeGridCustomStackedRenderer : TreeGridStackedHeaderCellRenderer
{
    public TreeGridCustomStackedRenderer()
    {
    }
    public override void OnInitializeEditElement(TreeDataColumnBase dataColumn, TreeGridStackedHeaderCell uiElement, object dataContext)
    {
        if (dataColumn.ColumnIndex == 0)
            uiElement.Style = App.Current.Resources["style1"] as Style;
        else if (dataColumn.ColumnIndex == 2)
            uiElement.Style = App.Current.Resources["style2"] as Style;
        else 
            uiElement.Style = App.Current.Resources["style3"] as Style;
        base.OnInitializeEditElement(dataColumn, uiElement, dataContext);
    }        
}
{% endhighlight %}
{% endtabs %}

![Changing Stacked Header Text Style in WPF TreeGrid Column](Styles-and-Templates_images/wpf-treegrid-stacked-header-text-style.png)
