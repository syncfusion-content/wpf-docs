---
layout: post
title: Getting Started | SfKanban | WPF| Syncfusion
description: Learn here about getting started with simple application using WPF Kanban (SfKanban) control and more details.
platform: wpf
control: SfKanban
documentation: ug
---
# Getting Started with WPF Kanban(SfKanban)

The following section provides an assistance to create a simple Kanban application and to configure it. 

## Adding assembly reference

1. Open the Add Reference window from your project
2. Choose Assemblies -> Extensions -> Syncfusion.SfKanban.WPF

![Reference Manager Dialog Windows in Visual Studio](sfkanban_images/wpf-kanban-board-assembly-reference.png)

N> This window differs for the Visual Basic project.

## Create a simple Kanban Board

In this section, we'll demonstrate how to build a new WPF application that integrates the `SfKanban` control.

### Adding SfKanban

1. Add the required assembly references to the project as discussed in the Reference Essential Studio Components in your Solution section.
2. Add the “Syncfusion.UI.Xaml.Kanban” namespace to the application as shown below.

{% capture codesnippet1 %}
{% tabs %}

{% highlight xaml %}
xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Kanban;assembly=Syncfusion.SfKanban.WPF"
{% endhighlight %}

{% highlight c# %}
using Syncfusion.UI.Xaml.Kanban;
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

3. Create an instance of SfKanban control.

{% capture codesnippet2 %}
{% tabs %}

{% highlight xaml %}
<syncfusion:SfKanban>

</syncfusion:SfKanban>
{% endhighlight %}

{% highlight c# %}

SfKanban kanban = new SfKanban();

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

### Adding SfKanban from toolbox

Drag and drop the Kanban control from the toolbox to your application.

![Adding SfKanban from toolbox](sfkanban_images/wpf-kanban-board-toolbox.png)

Now the Syncfusion.SfKanban.WPF reference is added to the application references and the xmlns namespace code is generated in MainWindow.xaml as below.

![Adding SfKanban from toolbox Assembly Included](sfkanban_images/wpf-kanban-board-assembly-included.png)

![Adding SfKanban from toolbox Xaml Reference](sfkanban_images/wpf-kanban-board-xaml-reference.png)

## Populate WPF Kanban item source

This section explains how to populate the WPF Kanban control's `ItemSource` by creating and binding both default and custom task data models.

### Creating the default model tasks

* **Define the View Model:** Create a view model class to set values for the properties listed in the [`KanbanModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanModel.html) class as shown in the following example code. Each [`KanbanModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanModel.html) instance represent a card in Kanban control.

* **Bind item source for Kanban:** To populate the kanban card items, utilize the [`ItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ItemsSource) property of [`SfKanban`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html).

* **Defining columns in the Kanban Board:** The columns are generated automatically based on the different values of the [`Category`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_Category) in the [`KanbanModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanModel.html) class from the [`ItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ItemsSource). However, you can manually define the columns by setting the [`AutoGenerateColumns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_AutoGenerateColumns) property to `false` and adding [`KanbanColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumn.html) instances to the [`Columns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_Columns) property of [`SfKanban`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html). You can define the column categories using the [`Categories`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumn.html#Syncfusion_UI_Xaml_Kanban_KanbanColumn_Categories) property of [`KanbanColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumn.html), and the cards will be added to their respective columns.

The following sample code demonstrates this process in action:

{% tabs %}
{% highlight XAML hl_lines="3 4 8 9 10 11 12 13" %}

<Grid x:Name="grid">
    <syncfusion:SfKanban x:Name="kanban"
                         ItemsSource="{Binding Tasks}"
                         AutoGenerateColumns="False">
        <syncfusion:SfKanban.DataContext>
            <local:ViewModel />
        </syncfusion:SfKanban.DataContext>
        <syncfusion:KanbanColumn Categories="Open"
                                 Title="To Do"/>
        <syncfusion:KanbanColumn Categories="In Progress"
                                 Title="In Progress"/>
        <syncfusion:KanbanColumn Categories="Review,Done"
                                 Title="Done"/>
    </syncfusion:SfKanban>
</Grid>

{% endhighlight %}
{% highlight C# hl_lines="1 2 3 4 5 7 8 9 10 11 13 14 15 16 17 19 20 21 22 23 24 25" %}

SfKanban kanban = new SfKanban()
{
    AutoGenerateColumns = false,
    ItemsSource = new ViewModel().Tasks
};

kanban.Columns.Add(new KanbanColumn()
{
    Categories = "Open",
    Title = "To Do"
});

kanban.Columns.Add(new KanbanColumn()
{
    Categories = "In Progress",
    Title = "In Progress"
});

kanban.Columns.Add(new KanbanColumn()
{
    Categories = "Review,Done",
    Title = "Done"
});

this.grid.Children.Add(kanban);

{% endhighlight %}
{% highlight C# tabtitle="ViewModel" %}

using Syncfusion.UI.Xaml.Kanban;

public class ViewModel
{
    public ObservableCollection<KanbanModel> Tasks { get; set; }
    public ViewModel()
    {
        Tasks = new ObservableCollection<KanbanModel>();
        Tasks.Add(new KanbanModel()
        {
            Title = "Universal App",
            ID = "27654",
            Description = "Incorporate feedback into functional specifications",
            Category = "Open",
            ColorKey = "Low",
            Tags = new string[] { "Deployment" },
        });

        Tasks.Add(new KanbanModel()
        {
            Title = "Universal App",
            ID = "29477",
            Description = "Design functional specifications",
            Category = "In Progress",
            ColorKey = "Normal",
            Tags = new string[] { "Design" },
        });

        Tasks.Add(new KanbanModel()
        {
            Title = "Universal App",
            ID = "25678",
            Description = "Review preliminary software specifications",
            Category = "Done",
            ColorKey = "Low",
            Tags = new string[] { "Analysis" },
        });

        Tasks.Add(new KanbanModel()
        {
            Title = "Universal App",
            ID = "6593",
            Description = "Draft preliminary software specifications",
            Category = "Review",
            ColorKey = "High",
            Tags = new string[] { "Analysis" },
        });
    }
}

{% endhighlight %}
{% endtabs %}

![wpf-kanban-board-column-using-default-model](sfkanban_images/wpf-kanban-board-column-using-default-model.png)

N> View the sample in [`GitHub`](https://github.com/SyncfusionExamples/Getting-started-in-SfKanban-WPF).

### Creating the custom model tasks with data mapping

You can also map custom data model to our Kanban control. The following steps demonstrate how to render tasks using the [WPF Kanban](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html) control with respective custom data properties.

* **Create a data model for kanban:** Create a simple data model in a new class file as shown in the following example code.

* **Create view model:** Create a view model class to set values for the properties listed in the model class as shown in the following example code.

* **Bind item source for Kanban:** To populate the Kanban card items, utilize the [`ItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ItemsSource) property of [`SfKanban`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html) control. Additionally, ensure that the following property of `SfKanban` are mapped from corresponding properties in the `ItemsSource` while initializing the kanban control.

The [ColumnMappingPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ColumnMappingPath) specifies the name of the property within the data object that is used to generate columns in the Kanban control when [`AutoGenerateColumns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_AutoGenerateColumns) is set to `true`.

* **Defining columns in the Kanban Board:** The [`Columns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_Columns) in the Kanban board are mapped based on the values of a specified property (e.g., "Status") from your custom data model. The [`ColumnMappingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ColumnMappingPath) specifies the name of the property within the data object that is used to generate columns in the Kanban control when [`AutoGenerateColumns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_AutoGenerateColumns) is set to `true`.

Alternatively, you can manually define columns by setting [`AutoGenerateColumns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_AutoGenerateColumns) to `false` and adding instances of [`KanbanColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumn.html) to the [`Columns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_Columns) collection of the [`SfKanban`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html) control. Based on the property specified in [ColumnMappingPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_ColumnMappingPath), the Kanban control will generate the columns and render the corresponding cards accordingly.

Let’s look at the practical code example:

{% tabs %}
{% highlight XAML hl_lines="2 3 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26" %}

<syncfusion:SfKanban x:Name="kanban"
                     ColumnMappingPath="Status"
                     ItemsSource="{Binding Tasks}">
    <syncfusion:SfKanban.DataContext>
        <local:ViewModel />
    </syncfusion:SfKanban.DataContext>
    <syncfusion:SfKanban.CardTemplate>
        <DataTemplate>
            <Border BorderBrush="Black"
                    BorderThickness="1"
                    CornerRadius="3"
                    Background="#F3CFCE">
                <StackPanel Margin="10">
                    <TextBlock Text="{Binding Title}"
                               TextAlignment="Center"
                               FontWeight="Bold"
                               FontSize="14" />
                    <TextBlock Text="{Binding Description}"
                               TextAlignment="Center"
                               FontSize="12"
                               TextWrapping="Wrap"
                               Margin="5" />
                </StackPanel>
            </Border>
        </DataTemplate>
    </syncfusion:SfKanban.CardTemplate>
</syncfusion:SfKanban>

{% endhighlight %}
{% highlight C# hl_lines="1 2" %}

this.kanban.ItemsSource = new ViewModel().Tasks;
this.kanban.ColumnMappingPath = "Status";

{% endhighlight %}
{% highlight C# tabtitle="TaskDetails.cs" %}

public class TaskDetails
{
    public string Title { get; set; }
    public string Description { get; set; }
    public object Status { get; set; }
}

{% endhighlight %}

{% highlight C# tabtitle="ViewModel.cs" %}

public class ViewModel
{
    public ObservableCollection<TaskDetails> Tasks { get; set; }
    public ViewModel()
    {
        Tasks = new ObservableCollection<TaskDetails>();
        Tasks.Add(new TaskDetails()
        {
            Title = "Universal App",
            Description = "Incorporate feedback into functional specifications",
            Status = "Open",
        });

        Tasks.Add(new TaskDetails()
        {
            Title = "Universal App",
            Description = "Design functional specifications",
            Status = "In Progress",
        });

        Tasks.Add(new TaskDetails()
        {
            Title = "Universal App",
            Description = "Review preliminary software specifications",
            Status = "Done",
        });

        Tasks.Add(new TaskDetails()
        {
            Title = "Universal App",
            Description = "Draft preliminary software specifications",
            Status = "Review",
        });
    }
}

{% endhighlight %}
{% endtabs %}

![wpf-kanban-board-column-using-custom-model](sfkanban_images/wpf-kanban-board-column-using-custom-model.png)

You can also set [`AutoGenerateColumns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_AutoGenerateColumns) property to true in which you don’t need to define the columns as mentioned in the above example. This will create columns depending on the ColumnMappingPath property for all the distinct values in ItemsSource.

N> 
* When the columns are auto-generated, you can handle the ColumnsGenerated event to customize the columns.
* When using a custom data model, the default card UI is not applicable. You must define a custom `DataTemplate` using the [`CardTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_CardTemplate) property to render the card content appropriately.

## Theme

Kanban control supports various built-in themes. Refer to the below links to apply themes for the Kanban control,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF SfKanban](sfkanban_images/wpf-kanban-board-theme.jpg)