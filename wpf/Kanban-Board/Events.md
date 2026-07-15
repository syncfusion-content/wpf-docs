---
layout: post
title: Events | SfKanban | WPF | Syncfusion
description: This section contains the detailed information about the Kanban dragging and column generated events.
platform: wpf
control: SfKanban
documentation: ug
---

# Events in WPF Kanban (SfKanban) Control

This section describes the events raised by the [`SfKanban`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html) control for card interactions, drag-and-drop operations, and column generation.

N> The snippets in this document use the `kanban:` prefix for the Syncfusion namespace. Make sure the following namespace mappings are declared on the root element: `xmlns:kanban="clr-namespace:Syncfusion.UI.Xaml.Kanban;assembly=Syncfusion.SfKanban.WPF"` and `xmlns:local="clr-namespace:YourNamespace"`.

## CardTapped

This event is triggered when you click (or tap) on a card. The [`KanbanDragEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html) argument contains the following information:

* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) - Used to get the column of the selected card.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard) - Used to get the selected card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex) - Used to get the index of the card in a column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of the dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of the dragging card's row.

### Command

The [`CardTappedCommand`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_CardTappedCommand) property is used to associate a command with an instance of `SfKanban`. This property is most often set with the MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The [`CardTappedCommandParameter`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_CardTappedCommandParameter) property is used to set the parameter reference, based on which the event argument is shown.

N> The default value of `CardTappedCommandParameter` is `null`.

## CardDoubleTapped

The [`CardDoubleTapped`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html) event is triggered when you double-click (or double-tap) on a card. The [`KanbanDoubleTappedEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs.html) argument contains the following information:

* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDoubleTappedEventArgs_SelectedCard) - Used to get the selected card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDoubleTappedEventArgs_SelectedCardIndex) - Used to get the index of the dragging card in a column.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDoubleTappedEventArgs_SelectedColumn) - Used to get the column of the selected card.

## ColumnDragStarting

The [`ColumnDragStarting`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ColumnDragStarting) event occurs when a column begins to be dragged. The [`KanbanColumnDragStartingEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragStartingEventArgs.html) argument contains the following details:

* [`Column`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragStartingEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDragStartingEventArgs_Column) - Returns the source column that is being dragged.
* [`ColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragStartingEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDragStartingEventArgs_ColumnIndex) - Returns the index of the dragged column within the Kanban column collection.
* [`Cancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragStartingEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDragStartingEventArgs_Cancel) - Determines whether the column drag operation should be canceled.

{% tabs %}
{% highlight XAML hl_lines="5" %}

<kanban:SfKanban x:Name="kanban"
                 ItemsSource="{Binding TaskDetails}"
                 AutoGenerateColumns="False"
                 AllowColumnReorder="True"
                 ColumnDragStarting="OnKanbanColumnDragStarting">
    <kanban:KanbanColumn Title="To Do" Categories="Open" />
    <kanban:KanbanColumn Title="In Progress" Categories="In Progress" />
    <kanban:KanbanColumn Title="Done" Categories="Done" />
    <kanban:SfKanban.DataContext>
        <local:ViewModel />
    </kanban:SfKanban.DataContext>
</kanban:SfKanban>

{% endhighlight %}
{% highlight C# hl_lines="3" %}

this.kanban.ItemsSource = new ViewModel().TaskDetails;
this.kanban.AutoGenerateColumns = false;
this.kanban.ColumnDragStarting += this.OnKanbanColumnDragStarting;
this.kanban.AllowColumnReorder = true;
this.kanban.Columns.Add(new KanbanColumn() { Title = "To Do", Categories = "Open" });
this.kanban.Columns.Add(new KanbanColumn() { Title = "In Progress", Categories = "In Progress" });
this.kanban.Columns.Add(new KanbanColumn() { Title = "Done", Categories = "Done" });

{% endhighlight %}
{% highlight C# tabtitle="MainWindow.xaml.cs" %}

using Syncfusion.UI.Xaml.Kanban;

private void OnKanbanColumnDragStarting(object sender, KanbanColumnDragStartingEventArgs e)
{
    var column = e.Column;
    int columnIndex = e.ColumnIndex;
}

{% endhighlight %}
{% highlight C# tabtitle="ViewModel.cs" %}

using System.Collections.ObjectModel;
using Syncfusion.UI.Xaml.Kanban;

namespace GettingStarted
{
    public class ViewModel
    {
        public ObservableCollection<KanbanModel> TaskDetails { get; set; }

        public ViewModel()
        {
            this.TaskDetails = new ObservableCollection<KanbanModel>();
            this.GetTaskDetails();
        }

        private void GetTaskDetails()
        {
            this.TaskDetails.Add(new KanbanModel() { Title = "WPF Issue", Description = "Crosshair label template not visible in WPF", Category = "Open", ColorKey = "High", Tags = new string[] { "Bug Fixing" } });
            this.TaskDetails.Add(new KanbanModel() { Title = "Kanban Feature", Description = "Provide drag and drop support", Category = "In Progress", ColorKey = "Low", Tags = new string[] { "New control" } });
            this.TaskDetails.Add(new KanbanModel() { Title = "WPF Issue", Description = "HorizontalAlignment for tooltip is not working", Category = "Done", ColorKey = "High", Tags = new string[] { "Bug Fixing" } });
        }
    }
}

{% endhighlight %}
{% endtabs %}

## ColumnDragOver

The [`ColumnDragOver`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ColumnDragOver) event occurs when a column is being dragged over another column. The [`KanbanColumnDragOverEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragOverEventArgs.html) argument contains the following details:

* [`SourceColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDragOverEventArgs_SourceColumn) - Returns the column where the drag operation originated.
* [`CurrentColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDragOverEventArgs_CurrentColumn) - Returns the current column over which the dragged column is positioned.
* [`PreviousColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDragOverEventArgs_PreviousColumnIndex) - Returns the previous column index before entering the current column.
* [`CurrentColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDragOverEventArgs_CurrentColumnIndex) - Returns the current column index over which the dragged column is positioned.

{% tabs %}
{% highlight XAML hl_lines="5" %}

<kanban:SfKanban x:Name="kanban"
                 ItemsSource="{Binding TaskDetails}"
                 AutoGenerateColumns="False"
                 AllowColumnReorder="True"
                 ColumnDragOver="OnKanbanColumnDragOver">
    <kanban:KanbanColumn Title="To Do" Categories="Open" />
    <kanban:KanbanColumn Title="In Progress" Categories="In Progress" />
    <kanban:KanbanColumn Title="Done" Categories="Done" />
    <kanban:SfKanban.DataContext>
        <local:ViewModel />
    </kanban:SfKanban.DataContext>
</kanban:SfKanban>

{% endhighlight %}
{% highlight C# hl_lines="3" %}

this.kanban.ItemsSource = new ViewModel().TaskDetails;
this.kanban.AutoGenerateColumns = false;
this.kanban.ColumnDragOver += this.OnKanbanColumnDragOver;
this.kanban.AllowColumnReorder = true;
this.kanban.Columns.Add(new KanbanColumn() { Title = "To Do", Categories = "Open" });
this.kanban.Columns.Add(new KanbanColumn() { Title = "In Progress", Categories = "In Progress" });
this.kanban.Columns.Add(new KanbanColumn() { Title = "Done", Categories = "Done" });

{% endhighlight %}
{% highlight C# tabtitle="MainWindow.xaml.cs" %}

using Syncfusion.UI.Xaml.Kanban;

private void OnKanbanColumnDragOver(object sender, KanbanColumnDragOverEventArgs e)
{
    var sourceColumn = e.SourceColumn;
    var currentColumn = e.CurrentColumn;
    int previousColumnIndex = e.PreviousColumnIndex;
    int currentColumnIndex = e.CurrentColumnIndex;
}

{% endhighlight %}
{% highlight C# tabtitle="ViewModel.cs" %}

using System.Collections.ObjectModel;
using Syncfusion.UI.Xaml.Kanban;

namespace GettingStarted
{
    public class ViewModel
    {
        public ObservableCollection<KanbanModel> TaskDetails { get; set; }

        public ViewModel()
        {
            this.TaskDetails = new ObservableCollection<KanbanModel>();
            this.GetTaskDetails();
        }

        private void GetTaskDetails()
        {
            this.TaskDetails.Add(new KanbanModel() { Title = "WPF Issue", Description = "Crosshair label template not visible in WPF", Category = "Open", ColorKey = "High", Tags = new string[] { "Bug Fixing" } });
            this.TaskDetails.Add(new KanbanModel() { Title = "Kanban Feature", Description = "Provide drag and drop support", Category = "In Progress", ColorKey = "Low", Tags = new string[] { "New control" } });
            this.TaskDetails.Add(new KanbanModel() { Title = "WPF Issue", Description = "HorizontalAlignment for tooltip is not working", Category = "Done", ColorKey = "High", Tags = new string[] { "Bug Fixing" } });
        }
    }
}

{% endhighlight %}
{% endtabs %}

## ColumnDrop

The [`ColumnDrop`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ColumnDrop) event occurs when a dragged column is dropped into a new position. The [`KanbanColumnDropEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDropEventArgs.html) argument contains the following details:

* [`SourceColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDropEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDropEventArgs_SourceColumn) - Returns the column from which the drag operation originated.
* [`PreviousColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDropEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDropEventArgs_PreviousColumnIndex) - Returns the column index before the drop.
* [`TargetColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDropEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDropEventArgs_TargetColumnIndex) - Returns the index where the column is dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDropEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnDropEventArgs_TargetColumn) - Returns the column into which the dragged column is dropped.

{% tabs %}
{% highlight XAML hl_lines="5" %}

<kanban:SfKanban x:Name="kanban"
                 ItemsSource="{Binding TaskDetails}"
                 AutoGenerateColumns="False"
                 AllowColumnReorder="True"
                 ColumnDrop="OnKanbanColumnDrop">
    <kanban:KanbanColumn Title="To Do" Categories="Open" />
    <kanban:KanbanColumn Title="In Progress" Categories="In Progress" />
    <kanban:KanbanColumn Title="Done" Categories="Done" />
    <kanban:SfKanban.DataContext>
        <local:ViewModel />
    </kanban:SfKanban.DataContext>
</kanban:SfKanban>

{% endhighlight %}
{% highlight C# hl_lines="3" %}

this.kanban.ItemsSource = new ViewModel().TaskDetails;
this.kanban.AutoGenerateColumns = false;
this.kanban.ColumnDrop += this.OnKanbanColumnDrop;
this.kanban.AllowColumnReorder = true;
this.kanban.Columns.Add(new KanbanColumn() { Title = "To Do", Categories = "Open" });
this.kanban.Columns.Add(new KanbanColumn() { Title = "In Progress", Categories = "In Progress" });
this.kanban.Columns.Add(new KanbanColumn() { Title = "Done", Categories = "Done" });

{% endhighlight %}
{% highlight C# tabtitle="MainWindow.xaml.cs" %}

using Syncfusion.UI.Xaml.Kanban;

private void OnKanbanColumnDrop(object sender, KanbanColumnDropEventArgs e)
{
    var sourceColumn = e.SourceColumn;
    int previousColumnIndex = e.PreviousColumnIndex;
    int targetColumnIndex = e.TargetColumnIndex;
    var targetColumn = e.TargetColumn;
}

{% endhighlight %}
{% highlight C# tabtitle="ViewModel.cs" %}

using System.Collections.ObjectModel;
using Syncfusion.UI.Xaml.Kanban;

namespace GettingStarted
{
    public class ViewModel
    {
        public ObservableCollection<KanbanModel> TaskDetails { get; set; }

        public ViewModel()
        {
            this.TaskDetails = new ObservableCollection<KanbanModel>();
            this.GetTaskDetails();
        }

        private void GetTaskDetails()
        {
            this.TaskDetails.Add(new KanbanModel() { Title = "WPF Issue", Description = "Crosshair label template not visible in WPF", Category = "Open", ColorKey = "High", Tags = new string[] { "Bug Fixing" } });
            this.TaskDetails.Add(new KanbanModel() { Title = "Kanban Feature", Description = "Provide drag and drop support", Category = "In Progress", ColorKey = "Low", Tags = new string[] { "New control" } });
            this.TaskDetails.Add(new KanbanModel() { Title = "WPF Issue", Description = "HorizontalAlignment for tooltip is not working", Category = "Done", ColorKey = "High", Tags = new string[] { "Bug Fixing" } });
        }
    }
}

{% endhighlight %}
{% endtabs %}

## CardDragStart

This event is triggered when you start to drag a card. The [`KanbanDragStartEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragStartEventArgs.html) argument contains the following information:

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragStartEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragStartEventArgs_IsCancel) - Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard) - Used to get the underlying model of the card.
* [`KeepCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragStartEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragStartEventArgs_KeepCard) - Determines whether to keep the dragged card in the source location until it is dropped in a new location. When it is `true`, the preview of the card will be created for dragging.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex) - Used to get the index of the card in the source column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of the dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of the dragging card's row.

## CardDragEnd

This event is triggered when the card drag operation is completed. The [`KanbanDragEndEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html) argument contains the following information:

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_IsCancel) - Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard) - Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex) - Used to get the index of the card in the source column.
* [`TargetKey`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetKey) - Used to get the category of the column where the card is going to be dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetColumn) - Used to get the current column which is the drop target for the card.
* [`TargetCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetCardIndex) - Used to get the index of the card in the target column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of the dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of the dragging card's row.
* [`TargetRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetRowIndex) - Used to get the target row index where the card is going to be inserted.
* [`TargetColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetColumnIndex) - Used to get the target column index where the card is going to be inserted.

## CardDragEnter

This event is triggered when a card enters a column while dragging. The [`KanbanDragEnterEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html) argument contains the following information:

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_IsCancel) - Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard) - Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex) - Used to get the index of the card in the source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentColumn) - Used to get the column into which the card enters.
* [`CurrentIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentIndex) - Used to get the index of the card in the current column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of the dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of the dragging card's row.
* [`CurrentRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentRowIndex) - Used to get the current index of the card's row.
* [`CurrentColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentColumnIndex) - Used to get the current index of the card's column.

## CardDragLeave

This event is triggered when a card leaves a column while dragging. The [`KanbanDragLeaveEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html) argument contains the following information:

* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard) - Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex) - Used to get the index of the card in the source column.
* [`LeftColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_LeftColumn) - Used to get the column from which the card leaves.
* [`PreviousCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_PreviousCardIndex) - Used to get the index of the card that was left.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of the dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of the dragging card's row.
* [`PreviousRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_PreviousRowIndex) - Used to get the previous card's row index when the card enters the next column.
* [`PreviousColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_PreviousColumnIndex) - Used to get the previous card's column index when the card enters the next column.

## CardDragOver

This event is triggered when a card is dragged to a new index within a column. The [`KanbanDragOverEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html) argument contains the following information:

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_IsCancel) - Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard) - Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex) - Used to get the index of the card in the source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentColumn) - Used to get the current column which is the drop target for the card.
* [`CurrentIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentIndex) - Used to get the new index of the card in the current column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of the dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of the dragging card's row.
* [`CurrentRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentRowIndex) - Used to get the current index of the card's row.
* [`CurrentColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentColumnIndex) - Used to get the current index of the card's column.

## ColumnsGenerated

This event is raised after the columns are generated automatically. You can access the auto-generated columns using the [`ActualColumns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ActualColumns) property of [`SfKanban`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html).

## ColumnGenerated

This event is triggered for each column as it is generated. The [`KanbanColumnGeneratedEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnGeneratedEventArgs.html) argument contains the following information:

* [`Columns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnsGeneratedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnsGeneratedEventArgs_Columns) - Used to get the generated columns.
* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnGeneratedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnGeneratedEventArgs_IsCancel) - Used to cancel the generated column from being added to the `SfKanban`.
* [`CurrentColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnGeneratedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnGeneratedEventArgs_CurrentColumn) - Used to get the current generated column.

## See Also

* [SfKanban API Reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html)
* [KanbanDragEventArgs API Reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html)
* [KanbanColumnDragStartingEventArgs API Reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragStartingEventArgs.html)
* [KanbanColumnDragOverEventArgs API Reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDragOverEventArgs.html)
* [KanbanColumnDropEventArgs API Reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnDropEventArgs.html)
* [Getting Started with WPF Kanban](Getting-started.md)
* [Cards in WPF Kanban](Cards.md)
* [Columns in WPF Kanban](Column.md)
