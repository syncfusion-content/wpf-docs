---
layout: post
title: Search in WPF DataGrid control | Syncfusion
description: Learn here all about Search support in Syncfusion WPF DataGrid (SfDataGrid) control, its elements and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Search in WPF DataGrid (SfDataGrid)

[WPF DataGrid](https://www.syncfusion.com/wpf-controls/datagrid) control allows you to search the data displayed in the SfDataGrid. You can search the data by using [SearchHelper.Search](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_Search_System_String_) method.

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.Search(TextBox.Text);

{% endhighlight %}
{% endtabs %}

![WPF DataGrid with Search Panel](Search_images/wpf-datagrid-search-panel.png)


### Filtering

You can enable filter based on search by setting [SearchHelper.AllowFiltering](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_AllowFiltering) property to true.

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.AllowFiltering = true;
this.dataGrid.SearchHelper.Search(TextBox.Text);

{% endhighlight %}
{% endtabs %}

![Enabling Filter based on Search in WPF DataGrid](Search_images/wpf-datagrid-filter-based-on-search.png)


You can search the data with the case-sensitivity by setting [SearchHelper.AllowCaseSensitiveSearch](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_AllowCaseSensitiveSearch) property.

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.AllowCaseSensitiveSearch = true;

{% endhighlight %}
{% endtabs %}

### Changing Search Highlight Background

In WPF DataGrid (SfDatagrid), you can change the search text highlighting color by setting [SearchHelper.SearchBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_SearchBrush) property. 

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.SearchBrush = Brushes.Green;
this.dataGrid.SearchHelper.Search(TextBox.Text);

{% endhighlight %}
{% endtabs %}

![Changing Search Text Highlighting Color in WPF DataGrid](Search_images/wpf-datagrid-highlight-search-color.png)

### Changing foreground for search highlight

In WPF DataGrid (SfDatagrid), you can change the foreground color for search text by setting the [SearchHelper.SearchForegroundBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_SearchForegroundBrush) property. 

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.SearchForegroundBrush = Brushes.Red;    

{% endhighlight %}
{% endtabs %}

![Changing Fore Color of Search Text  in WPF DataGrid](Search_images/wpf-datagrid-search-text-fore-color.png)

## Navigating cells based on search text

You can navigate to the cells contains the SearchText using [SearchHelper.FindNext](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_FindNext_System_String_) and [SearchHelper.FindPrevious](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_FindPrevious_System_String_) methods.

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.FindNext("SearchText");
this.dataGrid.SearchHelper.FindPrevious("SearchText");

{% endhighlight %}
{% endtabs %}

You can highlight the currently navigated search text using [SearchHelper.SearchHighlightBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_SearchHighlightBrush) property.

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.SearchHighlightBrush = Brushes.Red;
this.dataGrid.SearchHelper.FindNext("TextBox.Text ");

{% endhighlight %}
{% endtabs %}

![Highlighting Navigated Search Text in WPF DataGrid](Search_images/wpf-datagrid-highlight-navigate-search-text.png)

You can highlight the foreground color of current navigated search text by using the [SearchHelper.SearchForegroundHighlightBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_SearchForegroundHighlightBrush) property.

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.SearchForegroundHighlightBrush = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![Highlighting Current Navigated Search Text Color in WPF DataGrid](Search_images/wpf-datagrid-navigated-search-text-color.png)


## Move CurrentCell when FindNext and FindPrevious

You can move the current cell along with FindNext and FindPrevious operation using [MoveCurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_MoveCurrentCell_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_System_Boolean_) method in selection controller. 


{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.FindNext("BLONP");            
this.dataGrid.SelectionController.MoveCurrentCell(this.dataGrid.SearchHelper.CurrentRowColumnIndex);

{% endhighlight %}
{% endtabs %}

## Clear Search

You can clear the search by calling the [SearchHelper.ClearSearch](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_ClearSearch) method. 

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper.ClearSearch();

{% endhighlight %}
{% endtabs %}

## Search operation on Master-Details View

Master-details view allows you to search the data by using [SearchHelper.Search](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_Search_System_String_) method in the [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid).

{% tabs %}
{% highlight c# %}

(this.datagrid.DetailsViewDefinition[0] as GridViewDefinition).DataGrid.SearchHelper.Search(TextBox.Text);

{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Searched Data](Search_images/wpf-datagrid-search-data.png)


### Navigating cells based on search text in DetailsViewDataGrid

You can navigate to the cells contains the SearchText using [SearchHelper.FindNext](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_FindNext_System_String_) and [SearchHelper.FindPrevious](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html#Syncfusion_UI_Xaml_Grid_SearchHelper_FindPrevious_System_String_) methods in [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid).

{% tabs %}
{% highlight c# %}

(this.datagrid.DetailsViewDefinition[0] as GridViewDefinition).DataGrid.SearchHelper.FindNext(SearchBox.Text);
(this.datagrid.DetailsViewDefinition[0] as GridViewDefinition).DataGrid.SearchHelper.FindPrevious(SearchBox.Text);

{% endhighlight %}
{% endtabs %}
You can get the sample from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/MasterDetailsViewSearch-140489943.zip).

N> It is not possible to Navigate with the two DataGrid at a time.

## Search customization

WPF DataGrid (SfDataGrid) process the search operations in [SearchHelper](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SearchHelper.html) class. You can change the default search behaviors by overriding `SearchHelper` class and set to `SfDataGrid.SearchHelper`.

{% tabs %}
{% highlight c# %}

this.dataGrid.SearchHelper = new SearchHelperExt(this.dataGrid);
public class SearchHelperExt : SearchHelper
{

    public SearchHelperExt(SfDataGrid datagrid)
        : base(datagrid)
    {
    }
}

{% endhighlight %}
{% endtabs %}

### Search only selected columns

You can search only selected columns by overriding `SearchCell` method of `SearchHelper`. In the `SearchCell` method, based on `MappingName` you can skip the columns that you don’t want to search. 

In the below code, except `Quantity` column other columns are gets excluded from search. 

{% tabs %}
{% highlight c# %}

this.sfgrid.SearchHelper = new SearchHelperExt(this.sfgrid);
this.sfgrid.SearchHelper.Search("5");

public class SearchHelperExt : SearchHelper
{

    public SearchHelperExt(SfDataGrid datagrid)
        : base(datagrid)
    {
    }

    protected override bool SearchCell(DataColumnBase column, object record, bool ApplySearchHighlightBrush)
    {

        if (column.GridColumn.MappingName == "Quantity")
            return base.SearchCell(column, record, ApplySearchHighlightBrush);
        return false;
    }
}

{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Search Text only in Selected Column](Search_images/wpf-datagrid-search-text-in-column.png)


### Select the record based on the SearchText

You can select the records which contains the search text by using `GetSearchedRecord` method. 

{% tabs %}
{% highlight c# %}

this.dataGrid.SelectedItems.Clear();
this.dataGrid.SearchHelper.Search("SearchText"); 
var list = this.dataGrid.SearchHelper.GetSearchRecords();
int recordIndex = this.dataGrid.ResolveToRecordIndex(this.dataGrid.ResolveToRowIndex(list[0].Record));
this.dataGrid.SelectedIndex = recordIndex;

{% endhighlight %}
{% endtabs %}

![Select Record based on SearchText in WPF DataGrid](Search_images/wpf-datagrid-select-record-based-on-search.png)


### Search with the GridComboBoxColumn

You can search the data in SfDataGrid with all the GridColumns which loads TextBlock as display element. To perform the search operation in the [GridComboBoxColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridComboBoxColumn.html) you need to customize the `GridComboBoxColumn`.  As it loads the ContentControl in display mode. 

{% tabs %}
{% highlight c# %}
public class ComboBoxColumnExt : GridComboBoxColumn
{

    public ComboBoxColumnExt()
    {
        SetCellType("ComboBoxExt");
    }
    
    protected override Freezable CreateInstanceCore()
    {
        return new ComboBoxColumnExt();
    }
}

{% endhighlight %}
{% endtabs %}

You can change the display element of each column by creating new renderer for the particular column and assign to corresponding cell type in `SfDataGrid.CellRenderers`.

{% tabs %}
{% highlight c# %}
public class ComboBoxRendererExt : GridVirtualizingCellRenderer<TextBlock, ComboBox>
{
 
    public ComboBoxRendererExt()
    {
    }
    
    public override object GetControlValue()
    {
 
        if (!HasCurrentCellState)
            return null;
        return CurrentCellRendererElement.GetValue(IsInEditing ? Selector.SelectedValueProperty : TextBlock.TextProperty);
    }

    // Creates the binding to the Edit-element
 
    private void InitializeEditBinding(ComboBox uiElement, GridColumn column)
    {
        var comboBoxColumn = (GridComboBoxColumn)column;
        var source = comboBoxColumn.ValueBinding as Binding;
 
        // Creates the bind element to the edit-element.
        var bind = new Binding
        {
            Mode = BindingMode.TwoWay,
            Path = source.Path,
            StringFormat = source.StringFormat,
            TargetNullValue = source.TargetNullValue,
            UpdateSourceTrigger = UpdateSourceTrigger.PropertyChanged,
            ValidatesOnExceptions = source.ValidatesOnExceptions,
            AsyncState = source.AsyncState,
            BindingGroupName = source.BindingGroupName,
            IsAsync = source.IsAsync,
            NotifyOnSourceUpdated = source.NotifyOnSourceUpdated,
            NotifyOnTargetUpdated = source.NotifyOnTargetUpdated,
            UpdateSourceExceptionFilter = source.UpdateSourceExceptionFilter,
            XPath = source.XPath
        };
        
        uiElement.SetBinding(ComboBox.SelectedValueProperty, bind);
 
        // Binding the ItemSource to the GridComboBox.
        var itemsSourceBinding = new Binding { Path = new PropertyPath("ItemsSource"), Mode = BindingMode.TwoWay, Source = comboBoxColumn };
        uiElement.SetBinding(ComboBox.ItemsSourceProperty, itemsSourceBinding);
        var displayMemberBinding = new Binding { Path = new PropertyPath("DisplayMemberPath"), Mode = BindingMode.TwoWay, Source = comboBoxColumn };
        uiElement.SetBinding(ComboBox.DisplayMemberPathProperty, displayMemberBinding);
        var selectedValuePathBinding = new Binding { Path = new PropertyPath("SelectedValuePath"), Mode = BindingMode.TwoWay, Source = comboBoxColumn };
        uiElement.SetBinding(ComboBox.SelectedValuePathProperty, selectedValuePathBinding);
        var staysOpenOnEditBinding = new Binding { Path = new PropertyPath("StaysOpenOnEdit"), Mode = BindingMode.TwoWay, Source = comboBoxColumn };
        uiElement.SetBinding(ComboBox.StaysOpenOnEditProperty, staysOpenOnEditBinding);
        var isEditableBinding = new Binding { Path = new PropertyPath("IsEditable"), Mode = BindingMode.TwoWay, Source = comboBoxColumn };
        uiElement.SetBinding(ComboBox.IsEditableProperty, isEditableBinding);                       
        var itemTemplateBinding = new Binding { Path = new PropertyPath("ItemTemplate"), Mode = BindingMode.TwoWay, Source = comboBoxColumn };
        uiElement.SetBinding(ComboBox.ItemTemplateProperty, itemTemplateBinding);
    }

    // This will be invoke when the editing is triggered.
 
    public override void OnInitializeEditElement(DataColumnBase dataColumn, ComboBox uiElement, object dataContext)
    {
        GridColumn column = dataColumn.GridColumn;
        InitializeEditBinding(uiElement, column);
        var textAlignment = new Binding { Path = new PropertyPath("TextAlignment"), Mode = BindingMode.OneWay, Source = column, Converter = new TextAlignmentToHorizontalAlignmentConverter() };
        uiElement.SetBinding(Control.HorizontalContentAlignmentProperty, textAlignment);
        var verticalAlignment = new Binding { Path = new PropertyPath("VerticalAlignment"), Mode = BindingMode.TwoWay, Source = column };
        uiElement.SetBinding(Control.VerticalContentAlignmentProperty, verticalAlignment);           
    }

    // Display Element initialized for required properties

    public override void OnInitializeDisplayElement(Syncfusion.UI.Xaml.Grid.DataColumnBase dataColumn, TextBlock uiElement, object dataContext)
    {
        var column = dataColumn.GridColumn;
        var gridColumn = column as GridComboBoxColumn;
        uiElement.SetBinding(TextBlock.TextProperty, column.DisplayBinding);
        var textAlignment = new Binding { Path = new PropertyPath("TextAlignment"), Mode = BindingMode.OneWay, Source = column, Converter = new TextAlignmentToHorizontalAlignmentConverter() };
        uiElement.SetBinding(Control.HorizontalAlignmentProperty, textAlignment);
        var verticalAlignment = new Binding { Path = new PropertyPath("VerticalAlignment"), Mode = BindingMode.TwoWay, Source = column };
        uiElement.SetBinding(Control.VerticalAlignmentProperty, verticalAlignment);
        uiElement.Margin = new Thickness(3,0,1,0);
    }

    // This Display Binding has to be set with the TextBlock.TextProperty.
 
    private static void SetDisplayBinding(TextBlock element, GridColumn column, object dataContext)
    {
        var customColumn = (ComboBoxColumnExt)column;
        var binding = new Binding
        {
            Path = new PropertyPath(customColumn.MappingName),
            Mode = BindingMode.TwoWay,
            UpdateSourceTrigger = UpdateSourceTrigger.PropertyChanged,
        };
        element.SetBinding(TextBlock.TextProperty, binding);
    }
}

{% endhighlight %}
{% endtabs %}

## See Also

[How to apply search and filter for one column in SfDataGrid?](https://www.syncfusion.com/kb/9297/how-to-apply-search-and-filter-for-one-column-in-wpf-datagrid-sfdatagrid)

[How to filter the records with searching when underlying items source is DataTable in SfDataGrid?](https://www.syncfusion.com/kb/9290/how-to-filter-the-records-with-searching-when-underlying-items-source-is-datatable-in-wpf)

[How to perform incremental search ?](https://www.syncfusion.com/kb/8505/how-to-perform-the-incremental-search-in-wpf-datagrid-sfdatagrid)
