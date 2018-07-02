---
layout: post
title: Interactive feature of SfTreeGrid.
description: Interactive feature of SfTreeGrid | SfTreeGrid | ToolTip 
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Interactive Features

## Tooltip

Tooltip supports showing the pop-up window that displays the information when the mouse hovers over a cell of the SfTreeGrid.

### Record cell tooltip

You can enable tooltip for the TreeGridCell by setting the [SfTreeGrid.ShowToolTip](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~ShowToolTip.html) property to `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="treeGrid" 
                        AutoExpandMode="RootNodesExpanded"
                        AutoGenerateColumns="False"
                        ShowToolTip="True"
                        ChildPropertyName="Children"    ItemsSource="{Binding EmployeeDetails}">	

{% endhighlight %}
{% highlight c# %}

this.treeGrid.ShowToolTip = true;

{% endhighlight %}
{% endtabs %}

You can enable the tooltip of a particular column by setting the [TreeGridColumn.ShowToolTip](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~ShowToolTip.html) property to `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:TreeGridTextColumn HeaderText="First Name" MappingName="FirstName" ShowToolTip="True" />
<syncfusion:TreeGridTextColumn HeaderText="Last Name" MappingName="LastName" ShowToolTip="True" />	

{% endhighlight %}
{% highlight c# %}

this.treeGrid.Columns["FirstName"].ShowToolTip = true;
this.treeGrid.Columns["LastName"].ShowToolTip = true;

{% endhighlight %}
{% endtabs %}

N> It has higher priority than [SfTreeGrid.ShowToolTip](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~ShowToolTip.html).

![](Interactive-Features_images/InteractiveFeatures_img1.png)

### Header tooltip

You can enable the tooltip of a header cell by setting the [TreeGridColumn.ShowHeaderToolTip](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~ShowHeaderToolTip.html) property to `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid.Columns>
    <syncfusion:TreeGridTextColumn HeaderText="First Name" MappingName="FirstName" ShowHeaderToolTip="True" />
</syncfusion:SfTreeGrid.Columns>

{% endhighlight %}
{% highlight c# %}

this.treeGrid.Columns["FirstName"].ShowHeaderToolTip = true;

{% endhighlight %}
{% endtabs %}

![](Interactive-Features_images/InteractiveFeatures_img2.png)

### Tooltip customization

You can change appearance of the tooltip by customizing the style with TargetType as ToolTip.

{% tabs %}
{% highlight xaml %}

<Window.Resources>        
    <Style TargetType="ToolTip">
        <Setter Property="BorderThickness" Value="1,1,1,1" />
        <Setter Property="BorderBrush" Value="Red" />
        <Setter Property="Background" Value="SkyBlue" />
    </Style>
</Window.Resources>

<syncfusion:SfTreeGrid.Columns>
    <syncfusion:TreeGridTextColumn HeaderText="First Name" MappingName="FirstName" ShowToolTip="True" />
</syncfusion:SfTreeGrid.Columns>
	
{% endhighlight %}
{% endtabs %}

![](Interactive-Features_images/InteractiveFeatures_img3.png)

You can customize the template of the tooltip by using the [TreeGridColumn.ToolTipTemplate](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~ToolTipTemplate.html) and [TreeGridColumn.ToolTipTemplateSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~ToolTipTemplateSelector.html) properties. 

#### Customize the tooltip using ToolTipTemplate

You can customize appearance of the tooltip of a particular column by setting the `TreeGridColumn.ToolTipTemplate`. You can also customize appearance of the header tooltip of a particular column by using the [TreeGridColumn.HeaderToolTipTemplate](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~HeaderToolTipTemplate.html) property.

The ToolTipTemplate receives the underlying data object as DataContext by default. You can set the [TreeGridColumn.SetCellBoundToolTip](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~SetCellBoundToolTip.html) to `true` to change the DataContext of the tooltip template where it sets the DataContext as DataContextHelper. The [TreeGridDataContextHelper](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.Cells.TreeGridDataContextHelper.html) has the following properties to reuse the same template for all the columns: 

 <ul>  
 <li><b> [Record](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.Cells.DataContextHelper~Record.html): </b> Gets the underlying data record of a row which has the cell.  </li>
 <li><b> [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.Cells.DataContextHelper~Value.html):  </b> Gets the underlying value of a cell. </li> 
 </ul>

{% tabs %}
{% highlight xaml %}

<Window.Resources>
    <local:StringToImageConverter x:Key="ImageConverter" />
    <DataTemplate x:Key="TemplateToolTip">
        <Grid>
            <Grid.RowDefinitions>
                <RowDefinition Height="*"/>
                <RowDefinition Height="*"/>
            </Grid.RowDefinitions>
            <Image Height="100" Width="100" Source="{Binding LastName,Converter={StaticResource ImageConverter}}" />
            <TextBlock Grid.Row="1" Text="{Binding LastName}" HorizontalAlignment="Center"/>
        </Grid>
    </DataTemplate>
</Window.Resources>

<syncfusion:SfTreeGrid.Columns>    
    <syncfusion:TreeGridTextColumn HeaderText="Last Name" MappingName="LastName" ToolTipTemplate="{StaticResource TemplateToolTip}" ShowToolTip="True" />
</syncfusion:SfTreeGrid.Columns>

{% endhighlight %}
{% highlight c# %}

public class StringToImageConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {
        string imagename = value.ToString();
        return @"..\..\Assets\" + imagename + @".png";
    }

    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {
        return value;
    }
}

{% endhighlight %}
{% endtabs %}

![](Interactive-Features_images/InteractiveFeatures_img4.png)

You can get the sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ToolTipTemplateDemo-1415306479.zip).

#### Customize the ToolTip with ToolTipTemplateSelector

Different tooltip templates can be loaded conditionally in same column based on the data by setting the [TreeGridColumn.ToolTipTemplateSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~ToolTipTemplateSelector.html) property. 

{% tabs %}
{% highlight xaml %}

<Window.Resources>
    <DataTemplate x:Key="ToolTip1">
        <Grid>                
            <TextBlock Text="{Binding Record.Id}" FontWeight="Bold" Foreground="Red" />
        </Grid>
    </DataTemplate>
    <DataTemplate x:Key="ToolTip2">
        <Grid>
            <TextBlock Text="{Binding Record.Id}" FontWeight="Bold" Foreground="Green"/>                
        </Grid>
    </DataTemplate>      
</Window.Resources>

<syncfusion:SfTreeGrid.Columns>
    <syncfusion:TreeGridTextColumn HeaderText="Person ID" MappingName="Id" ShowToolTip="True" >
        <syncfusion:TreeGridTextColumn.ToolTipTemplateSelector>
            <syncfusion:TreeGridTextColumn HeaderText="Person ID" MappingName="Id" 
                                               DisplayBinding="{Binding Path=Id, StringFormat=c}"
                                               ShowToolTip="True" SetCellBoundToolTip="True" >
        </syncfusion:TreeGridTextColumn.ToolTipTemplateSelector>
    </syncfusion:TreeGridTextColumn>
</syncfusion:SfTreeGrid.Columns>

{% endhighlight %}
{% highlight c# %}

public class ToolTipTemplateSelector : DataTemplateSelector
{
    private DataTemplate _defaultTemplate;

    /// <summary>
    /// Gets or sets DefaultTemplate.
    /// </summary>
    public DataTemplate DefaultTemplate
    {
        get { return _defaultTemplate; }
        set { _defaultTemplate = value; }
    }

    private DataTemplate _alternateTemplate;

    /// <summary>
    /// Gets or Sets AlternateTemplate.
    /// </summary>
    public DataTemplate AlternateTemplate
    {
        get { return _alternateTemplate; }
        set { _alternateTemplate = value; }
    }

    public override System.Windows.DataTemplate SelectTemplate(object item, System.Windows.DependencyObject container)
    {
        var treeGridData = item as TreeGridDataContextHelper;
        if (treeGridData == null)
            return this.DefaultTemplate;
        // To see what template needs to be select according to the specified property value.
        if ((treeGridData.Record as Employee).Id == (int)treeGridData.Value && ((int)treeGridData.Value % 2) == 0)
            return this.AlternateTemplate;
        else
            return this.DefaultTemplate;
    }
}

{% endhighlight %}
{% endtabs %}

The following image shows the DefaultTemplate applied through ToolTipTemplateSelector.

![](Interactive-Features_images/InteractiveFeatures_img5.png)

The following image shows the AlternateTemplate applied through ToolTipTemplateSelector.

![](Interactive-Features_images/InteractiveFeatures_img6.png)

You can get the sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ToolTipTemplateSelectorDemo1909534526.zip).

## Events

### CellToolTipOpening event

The [CellToolTipOpening](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~CellToolTipOpening_EV.html) event occurs when any tooltip of the cell is opened. The `CellToolTipOpening` event receives the [TreeGridCellToolTipOpeningEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridCellToolTipOpeningEventArgs.html) as argument which has the following properties:

<ul>
<li> [Column](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs~Column.html): Gets the hovered cell column in the SfTreeGrid.</li>
<li> [Node](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridCellToolTipOpeningEventArgs~Node.html): Gets the hovered cell node.</li>
<li> [Record](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs~Record.html): Gets the data context of hovered cell.</li>
<li> [RowColumnIndex](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs~RowColumnIndex.html): Gets the row and column index of the hovered cell.</li>
<li> [ToolTip](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs~ToolTip.html): Gets the tooltip of the hovered cells.</li>
</ul>

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"  
                        AutoExpandMode="RootNodesExpanded" 
                        CellToolTipOpening="TreeGrid_CellToolTipOpening"
                        AutoGenerateColumns="False"
                        ChildPropertyName="Children"
                        ColumnSizer="Star"
                        ExpanderColumn="Id"
                        ItemsSource="{Binding PersonDetails}">
{% endhighlight %}
{% highlight c# %}
this.treeGrid.CellToolTipOpening += TreeGrid_CellToolTipOpening;

private void TreeGrid_CellToolTipOpening(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridCellToolTipOpeningEventArgs e)
{
           
}
{% endhighlight %}
{% endtabs %}

## Row drag-and-drop

SfTreeGrid have built-in support for the row drag-and-drop. You can drag-and-drop the rows in the SfTreeGrid and between two SfTreeGrid controls by setting the [SfTreeGrid.AllowDraggingRows](https://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.wpf~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~AllowDraggingRows.html) and [AllowDrop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid_members.html#) properties to `true`.  It is also possible to drag-and-drop from the SfTreeGrid to any other control. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="sfTreeGrid" 
					   AllowDraggingRows="True" 
					   AllowDrop="True" 
					   ChildPropertyName="ReportsTo" 
					   ItemsSource="{Binding Employees}">

{% endhighlight %}
{% highlight c# %}
 
sfTreeGrid.AllowDraggingRows = true;
sfTreeGrid.AllowDrop = true;
 
{% endhighlight %}
{% endtabs %}

When dropping, the dragged node(s) can be added above or below or as a child node based on its drop position. For example, if you drop on the bottom of node, it will be added below the node. If dropping over the node, it will be added as a child of that node.

![](Interactive-Features_images/DragandDropDemo.gif)

N> Row drag-and-drop for the SfTreeGrid support is provided from Volume 2 2018 release (v16.2.0.41).

### Dragging multiple nodes

The SfTreeGrid allows you to drag multiple selected nodes by setting the SfTreeGrid.SelectionMode as `Multiple` or `Extended`.

![](Interactive-Features_images/InteractiveFeatures_img8.png)

## Drag-and-drop options

The SfTreeGrid control has the following properties to control the drag-and-drop options manually.

<table>
<tr>
<th>
Properties
</th>
<th>
Description
</th>
</tr>

<tr>
<td>
[SfTreeGrid.AllowDraggingRows](https://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.wpf~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~AllowDraggingRows.html)
</td>
<td>
Gets or sets whether the end user can drag the nodes or not.
</td>
</tr>

<tr>
<td>
[SfTreeGrid.AllowDrop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid_members.html#)
</td>
<td>
Gets or sets whether the end user can drop the nodes or not.
</td>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~RowDragDropTemplate.html)
</td>
<td>
Gets or sets the custom row drag pop-up data template.
</td>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropController.CanAutoExpand](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~CanAutoExpand.html)
</td>
<td>
Gets or sets whether the end user can expand the collapsed nodes while dragging or not. 
</td>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropController.AutoExpandDelay](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~AutoExpandDelay.html)
</td>
<td>
Gets or sets the time delay for expanding the collapsed nodes while dragging. 
</td>
</tr>
</table>

Events for row drag-and-drop operations are as follows.

<table>
<tr>
<th>
Events
</th>
<th>
Description
</th>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropController.DragStart](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragStart_EV.html)
</td>
<td>
Occurs when drag-and-drop operations are started.  
</td>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropController.DragOver](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragOver_EV.html)
</td>
<td>
Occurs continuously when the node is dragged within the drop target (SfTreeGrid) boundary.   
</td>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropController.DragLeave](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragLeave_EV.html)
</td>
<td>
Occurs when the node is dragged out of the drop target (SfTreeGrid) boundary. 
</td>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropController.Drop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Drop_EV.html)
</td>
<td>
Occurs while dropping the record in drop target (SfTreeGrid).
</td>
</tr>

<tr>
<td>
[SfTreeGrid.RowDragDropController.Dropped](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Dropped_EV.html)
</td>
<td>
Occurs when the nodes dropped within the SfTreeGrid. 
</td>
</tr>

</table>

## Drag-and-drop between TreeGrids

The SfTreeGrid provides built-in support for drag-and-drop nodes between the SfTreeGrid controls.  

Follow the steps to implement drag-and-drop between the SfTreeGrid controls: 

1. Add the SfTreeGrid controls to your project.
2. Set the [AllowDraggingRows](https://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.wpf~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~AllowDraggingRows.html) and [AllowDrop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid_members.html#) properties to `true` to enable drag-and-drop functionalities in both the SfTreeGrid controls.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="sfTreeGrid1" 
					   AllowDraggingRows="True" 
					   AllowDrop="True" 
					   Grid.Column="0" 
					   ChildPropertyName="ReportsTo" 
					   ItemsSource="{Binding EmployeesHR}">

<syncfusion:SfTreeGrid Name="sfTreeGrid2" 
					   AllowDraggingRows="True" 
					   AllowDrop="True" 
					   Grid.Column="1" 
					   ChildPropertyName="ReportsTo" 
					   ItemsSource="{Binding EmployeesAccounts}">

{% endhighlight %}
{% endtabs %}

3. Now, you can drag-and-drop nodes between both the SfTreeGrid controls. You can download the sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DRAGAN~1-710537123.zip).

## Customizing row drag-and-drop

### Auto expanding the node on drag over

When dragging over the tree node if the drop position is set as `Drop as child`, the SfTreeGrid can auto expand the corresponding tree node by setting the [TreeGridRowDragDropController.CanAutoExpand](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~CanAutoExpand.html) to `true`. It is also possible to control the delay by expanding the node when dragging over the rows by using the [TreeGridRowDragDropController.AutoExpandDelay](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~AutoExpandDelay.html) property. Its default value is 3 sec.

{% tabs %}
{% highlight c# %}

treeGrid.RowDragDropController.CanAutoExpand = true;
treeGrid.RowDragDropController.AutoExpandDelay = new TimeSpan(0, 0, 2);
					   
{% endhighlight %}
{% endtabs %}

### Customizing default drag UI

You can customize the default drag UI by setting the [SfTreeGrid.RowDragDropTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~RowDragDropTemplate.html) to your customized data template. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="sfTreeGrid" 
					   AllowDraggingRows="True" 
					   AllowDrop="True" 
					   ChildPropertyName="ReportsTo" 
					   ItemsSource="{Binding Employees}" 
					   RowDragDropTemplate="{StaticResource  SampleDragDropTemplate}">
					   
{% endhighlight %}
{% endtabs %}

Resources should have DataTemplate definition as mentioned in the RowDragDropTemplate. 

{% tabs %}
{% highlight xaml %}

<Window.Resources>
        <DataTemplate x:Key="SampleDragDropTemplate ">
            <Border Height="100" Width="300" Background="Red"/>
        </DataTemplate>
</Window.Resources>
					   
{% endhighlight %}
{% endtabs %}

### Disable dragging of certain node

You can disable dragging functionality of some specific nodes by using the [SfTreeGrid.RowDragDropController.DragStart](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragStart_EV.html) event.  

{% tabs %}
{% highlight c# %}

private void RowDragDropController_DragStart(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs e)
{
	ObservableCollection<TreeNode> draggingNodes = e.DraggingNodes;
	var item = draggingNodes[0].Item as EmployeeInfo;
    if(item.FirstName.StartsWith("Andrew"))
    {
		e.Handled = true;
    }
}

{% endhighlight %}
{% endtabs %}

### Disable drop over certain node

You can disable dropping functionality of some specific nodes by using the [SfTreeGrid.RowDragDropController.Drop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Drop_EV.html) event.  

{% tabs %}
{% highlight c# %}

private void RowDragDropController_Drop(object sender, TreeGridRowDropEventArgs e)
{
  TreeNode targetNode = e.TargetNode;
  var item = targetNode.Item as EmployeeInfo;
  if (item.FirstName.StartsWith("Andrew"))
  {
     e.Handled = true;
  }
}

{% endhighlight %}
{% endtabs %}

### Disable default drag UI

You can disable dropping functionality of some specific nodes by using the [SfTreeGrid.RowDragDropController.Drop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Drop_EV.html) event.  

{% tabs %}
{% highlight c# %}

private void RowDragDropController_DragOver(object sender, TreeGridRowDragOverEventArgs e)
{
    e.ShowDragUI = false;
}

{% endhighlight %}
{% endtabs %}