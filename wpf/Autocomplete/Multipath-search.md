---
layout: post
title: Perform multi-path search in WPF Autocomplete | Syncfusion
description: Learn here all about Perform multi-path search in Syncfusion WPF Autocomplete (SfTextBoxExt) control, its elements and more.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Perform multi-path search in WPF Autocomplete

Multi-path search can be achieved using the custom search feature by setting the [SuggestionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SuggestionMode) property as `Custom`. Users can define a custom filter and can be assigned to the [Filter](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_Filter) property.

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

**View model**

{% highlight c# %}

    public class Viewmodel
    {
        public ICommand ControlLoaded
        {
            get;
            set;
        }

        private ObservableCollection<Model> employees;
        public ObservableCollection<Model> Employees
        {
            get { return employees; }
            set { employees = value; }
        }
        public ViewModel()
        {
            ControlLoaded = new DelegateCommand(Loaded);
            Employees = new ObservableCollection<Model>();
            Employees.Add(new Model() { ID = 1, Name = "Eric" });
            Employees.Add(new Model() { ID = 2, Name = "James" });
            Employees.Add(new Model() { ID = 3, Name = "Jacob" });
            Employees.Add(new Model() { ID = 4, Name = "Lucas" });
            Employees.Add(new Model() { ID = 5, Name = "Mark" });
            Employees.Add(new Model() { ID = 6, Name = "Aldan" });
            Employees.Add(new Model() { ID = 7, Name = "Aldrin" });
            Employees.Add(new Model() { ID = 8, Name = "Alan" });
            Employees.Add(new Model() { ID = 9, Name = "Aaron" });
        }
        private void Loaded(object obj)
        {
            var autocomplete = obj as SfTextBoxExt;
            if (autocomplete != null)
            {
                autocomplete.Filter = Filtering;
            }
        }
        public bool Filtering(string search, object item)
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
    }
	
{% endhighlight %}

{% tabs %}

{% highlight xaml %}

    <Window.DataContext>
        <local:ViewModel />
    </Window.DataContext>
    <StackPanel Margin="10" VerticalAlignment="Center">
        <editors:SfTextBoxExt
            x:Name="autocomplete"
            AutoCompleteMode="Suggest"
            AutoCompleteSource="{Binding Employees}"
            SearchItemPath="Name"
            SuggestionMode="Custom">
            <editors:SfTextBoxExt.AutoCompleteItemTemplate>
                <DataTemplate>
                    <Grid HorizontalAlignment="Stretch">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="20" />
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
                        <TextBlock
                            Grid.Column="1"
                            Padding="10,8,0,8"
                            VerticalAlignment="Center"
                            FontFamily="SegoeUI"
                            FontSize="12"
                            FontWeight="Normal"
                            Text="{Binding Name}" />
                    </Grid>
                </DataTemplate>
            </editors:SfTextBoxExt.AutoCompleteItemTemplate>
            <interaction:Interaction.Triggers>
                <interaction:EventTrigger EventName="Loaded">
                    <interaction:InvokeCommandAction Command="{Binding ControlLoaded}" CommandParameter="{Binding ElementName=autocomplete}" />
                </interaction:EventTrigger>
            </interaction:Interaction.Triggers>
        </editors:SfTextBoxExt>
    </StackPanel>

{% endhighlight %}


{% highlight c# %}

            Viewmodel viewmodel = new Viewmodel();
            this.DataContext = viewmodel;
            StackPanel stackPanel = new StackPanel()
            {
                Margin = new Thickness(10),
                VerticalAlignment = VerticalAlignment.Center
            };

            SfTextBoxExt autocomplete = new SfTextBoxExt()
            {
                Width = 200,
                Height = 40,
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                AutoCompleteSource = viewmodel.Employees,
                Filter= viewmodel.Filtering,
                SearchItemPath = "Name",
                SuggestionMode = SuggestionMode.Custom
            };

            FrameworkElementFactory grid = new FrameworkElementFactory(typeof(Grid));
            grid.SetValue(Grid.HorizontalAlignmentProperty, HorizontalAlignment.Stretch);

            FrameworkElementFactory firstColumn = new FrameworkElementFactory(typeof(ColumnDefinition));
            firstColumn.SetValue(ColumnDefinition.WidthProperty, new GridLength(20.0));

            FrameworkElementFactory secondColumn = new FrameworkElementFactory(typeof(ColumnDefinition));
            secondColumn.SetValue(ColumnDefinition.WidthProperty, new GridLength(0.0, GridUnitType.Auto));

            FrameworkElementFactory textBlockID = new FrameworkElementFactory(typeof(TextBlock));
            textBlockID.SetBinding(TextBlock.TextProperty, new Binding("ID"));

            FrameworkElementFactory textBlockName = new FrameworkElementFactory(typeof(TextBlock));
            textBlockName.SetValue(TextBlock.TextProperty, new Binding("Name"));

            grid.AppendChild(textBlockID);
            grid.AppendChild(textBlockName);
            DataTemplate template = new DataTemplate { VisualTree = grid };
            autoComplete.AutoCompleteItemTemplate = template;
            stackPanel.Children.Add(autocomplete);
            this.Content = stackPanel;

{% endhighlight %}

{% endtabs %}


**Search the items with ID:**

![Multi-path Search ID](Multipath_Search/Multipath_Search.png)


**Search the items with Name:**

![Multi-path Search Name](Multipath_Search/Multipath_Search_Name.png)


N> View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Multipath_Search) in GitHub.
