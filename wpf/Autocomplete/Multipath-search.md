---
layout: post
title: Multipath search of AutoComplete in Syncfusion SfTextBoxExt.
description: This section provides details about how to perform Multipath search from AutoCompleteSource in Syncfusion AutoComplete control.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Multi path search with AutoComplete

AutoComplete control already supports the custom search. So, it can be used for the MultiPath search. When using the object list AutoCompleteSource, the
control search is based on the SearchItemPath. It’s performed the single path search. But using the custom search and perform the MultiPath search in AutoComplete.

**Model**

{% highlight c# %}

    public class Model
    {
        private int id;
        public int ID
        {
            get { return id; }
            set { id = value; }
        }
        private string name;
        public string Name
        {
            get { return name; }
            set { name = value; }
        }
    }
	
{% endhighlight %}

**ViewModel**

{% highlight c# %}

    public class ViewModel
    {
        private ObservableCollection<Model> employeeCollection;
        public ObservableCollection<Model> EmployeeCollection
        {
            get { return employeeCollection; }
            set { employeeCollection = value; }
        }
        public ViewModel()
        {
            employeeCollection = new ObservableCollection<Model>();
            employeeCollection.Add(new Model() { ID = 1, Name = "Eric" });
            employeeCollection.Add(new Model() { ID = 2, Name = "James" });
            employeeCollection.Add(new Model() { ID = 3, Name = "Jacob" });
            employeeCollection.Add(new Model() { ID = 4, Name = "Lucas" });
            employeeCollection.Add(new Model() { ID = 5, Name = "Mark" });
            employeeCollection.Add(new Model() { ID = 6, Name = "Aldan" });
            employeeCollection.Add(new Model() { ID = 7, Name = "Aldrin" });
            employeeCollection.Add(new Model() { ID = 8, Name = "Alan" });
            employeeCollection.Add(new Model() { ID = 9, Name = "Aaron" });
        }
    }
	
{% endhighlight %}

{% tabs %}

{% highlight xaml %}

 <editors:SfTextBoxExt
            x:Name="autoComplete"
            Width="200"
            Height="40"
            HorizontalAlignment="Center"
            VerticalAlignment="Center"
            AutoCompleteMode="Suggest"
            AutoCompleteSource="{Binding EmployeeCollection}"
            SearchItemPath="Name"
            SuggestionMode="Custom">
            <editors:SfTextBoxExt.AutoCompleteItemTemplate>
                <DataTemplate>
                    <Grid HorizontalAlignment="Stretch">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="20" />
                            <ColumnDefinition Width="1" />
                            <ColumnDefinition Width="Auto" />
                        </Grid.ColumnDefinitions>
                        <TextBlock
                            Grid.Column="0"
                            Padding="2,8,0,8"
                            VerticalAlignment="Center"
                            FontFamily="SegoeUI"
                            FontSize="12"
                            FontWeight="Normal"
                            Text="{Binding ID}" />
                        <Border
                            Grid.Column="1"
                            Width="1"
                            Margin="0,-15"
                            BorderBrush="#D8D8D8"
                            BorderThickness="1" />
                        <TextBlock
                            Grid.Column="2"
                            Padding="10,8,0,8"
                            VerticalAlignment="Center"
                            FontFamily="SegoeUI"
                            FontSize="12"
                            FontWeight="Normal"
                            Text="{Binding Name}" />
                    </Grid>
                </DataTemplate>
            </editors:SfTextBoxExt.AutoCompleteItemTemplate>
        </editors:SfTextBoxExt>

{% endhighlight %}


{% highlight c# %}

 autoComplete.Filter = CustomFilter;

 private bool CustomFilter(string search, object item)
        {
            var model = item as Model;
            if (model != null)
            {
                if ((model.Name.ToLower().Contains(search.ToLower())) || ((model.ID).ToString().ToLower().Contains(search.ToLower())))
                {
                    return true;
                }
            }
            return false;
        }

{% endhighlight %}

{% endtabs %}


![Multipath Search ID](Multipath_Search/Multipath_Search.png)

![Multipath Search Name](Multipath_Search/Multipath_Search_Name.png)

N> View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Multipath_Search) in GitHub.
