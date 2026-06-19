---
layout: post
title: Single and Multiple Selection in WPF Autocomplete | Syncfusion®
description: Explore support for single and multiple selection in Syncfusion® WPF Autocomplete (SfTextBoxExt) control, and more.
platform: WPF
control: SfTextBoxExt
documentation: ug
---

# Single and Multiple Selection in WPF Autocomplete (SfTextBoxExt)

In AutoComplete, selection can be managed using either single or multi-selection modes. This is controlled by the [MultiSelectMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_MultiSelectMode) property. The default value of `MultiSelectMode` is `None`, which enables single selection.

## Single Selection

Single selection is achieved by setting the [MultiSelectMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_MultiSelectMode) property to `None`. In this mode, you can set and retrieve the selected item using the [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectedItem) property.

## Multi-selection

For multi-selection, there are two ways to represent selections within the control:

* Token 

* Delimiter

## Multiple Selection Using Tokens

Each selected item can be displayed as a token, with a close button for each token.

In token representation, the arrangement of items is determined by the [TokensWrapMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_TokensWrapMode) property:

* `Wrap` - Selected items wrap to the next line.
* `None` - Selected items display in a single horizontal line.

Use the [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectedItems) property to set and retrieve items in `MultiSelectMode`.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Left"
                      AutoCompleteMode="Suggest"
                      SearchItemPath="Name"
                      MultiSelectMode="Token"
                      Height="40"
                      AutoCompleteSource="{Binding Employees}"
                      VerticalAlignment="Center"
                      Width="200"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.MultiSelectMode = MultiSelectMode.Token;

{% endhighlight %}

{% endtabs %}

![Token Representation](Single_and_multiple_selection_images/Token.png)


### Customization of Tokens

Customize tokens by overriding the default style, targeting the `TokenItem` class.


{% tabs %}

{% highlight xaml %}

      <Window.Resources>
        <Style  TargetType="editors:TokenItem">
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="editors:TokenItem">
                        <Border x:Name="TokenBorder" Margin="4,4,2,4"  Background="Black"  CornerRadius="10"  Height="{TemplateBinding Height}" >
                            <Grid Margin="2" x:Name="TokenGrid">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="auto"/>
                                    <ColumnDefinition Width="*"/>
                                    <ColumnDefinition Width="auto"/>
                                </Grid.ColumnDefinitions>
                                    <TextBlock x:Name="TokenTextBlock" Text="{TemplateBinding Text}" Foreground="White" Grid.Column="1" Margin="2,0,2,3" VerticalAlignment="Center" Padding="4,0,0,0" />
                                    <Button Grid.Column="2" Margin="2"  x:Name="TokenCloseButton" IsTabStop="False" Background="White"  CommandParameter="{Binding RelativeSource={RelativeSource Mode=TemplatedParent}}" >
                                        <Button.Content>
                                            <TextBlock x:Name="TokenButtonContent" Text="&#xE711;" VerticalAlignment="Center" FontSize="10"  Foreground="Black" FontFamily="Segoe MDL2 Assets" />
                                        </Button.Content>
                                    <Button.Resources>
                                        <Style TargetType="{x:Type Border}">
                                            <Setter Property="CornerRadius" Value="13"/>
                                        </Style>
                                    </Button.Resources>
                                </Button>
                            </Grid>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </Window.Resources>
        <editors:SfTextBoxExt HorizontalAlignment="Left"
                                  AutoCompleteMode="Suggest"
                                  SearchItemPath="Name"
                                  MultiSelectMode="Token" 
                                  Height="40"
                                  AutoCompleteSource="{Binding Employees}"
                                  VerticalAlignment="Center"
                                  Width="200"/>
     
{% endhighlight %}

{% endtabs %}

![Token_Customization](Single_and_multiple_selection_images/Token_Customization.png)

### Enable Auto-size in Token Mode

When using `Wrap` mode, enabling the [EnableAutoSize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_EnableAutoSize) property re-renders the control height based on the number of lines tokens wrap inside the control.

To use this feature, set the `MultiSelectMode` as `Token` and `TokensWrapMode` as `Wrap`. By default, this feature is disabled.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Left"
                      AutoCompleteMode="Suggest"
                      SearchItemPath="Name"
                      MultiSelectMode="Token" 
                      TokensWrapMode="Wrap"
                      EnableAutoSize="True"
                      AutoCompleteSource="{Binding Employees}"
                      VerticalAlignment="Center"
                      Width="200"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.MultiSelectMode = MultiSelectMode.Token;
textBoxExt.TokensWrapMode = TokensWrapMode.Wrap;
textBoxExt.EnableAutoSize = true;

{% endhighlight %}

{% endtabs %}

![EnableAutoSize](Single_and_multiple_selection_images/EnableAutoSize.png)

### ShowClearButton

This feature allows showing or hiding the clear button in Token mode for the AutoComplete control using the [ShowClearButton](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_ShowClearButton) property.

{% tabs %}

{% highlight xaml %}

        <editors:SfTextBoxExt
            x:Name="textBoxExt"
            Width="200"
            HorizontalAlignment="Center"
            VerticalAlignment="Center"
            AutoCompleteMode="Suggest"
            AutoCompleteSource="{Binding Employees}"
            MultiSelectMode="Token"
            SearchItemPath="Name"
            ShowClearButton="True" />

{% endhighlight %}

{% highlight c# %}

textBoxExt.ShowClearButton = true; 

{% endhighlight %}

{% endtabs %}

![ShowClearButton](Single_and_multiple_selection_images/ShowClearButton.png)

> Note: The default `ShowClearButton` property value is false. It applies only when `MultiSelectMode` is `Token`.

See also the [Multiple selection using tokens](https://help.syncfusion.com/wpf/autocomplete/single-and-multiple-selection#multiple-selection-using-tokens) topic in AutoComplete.

## Multiple Selection Using Delimiter

In `Delimiter` mode, each item is separated by a character specified in the [Delimiter](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_Delimiter) property. By default, items are separated by a comma (`,`).

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="300"
                      Height="40"
                      MultiSelectMode="Delimiter"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% highlight c# %}

textBoxExt.MultiSelectMode = MultiSelectMode.Delimiter;

{% endhighlight %}

{% endtabs %}

![Delimiter](Single_and_multiple_selection_images/Delimiter.png)

## Setting and Retrieving SelectedItem

The [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectedItem) property selects or retrieves a particular item from the suggestion list. It is used for single selection when `MultiSelectMode` is `None`. For multi-selection, where `MultiSelectMode` is set to either `Token` or `Delimiter`, use the [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectedItems) property.

The `SelectedItem` and `SelectedItems` contain custom data objects, and the item displayed in the text field can be retrieved using the `SearchItemPath` property.
### Model Class:

{% tabs %}
{% highlight c# %}


public class Employee
{
        string name;
        string email;

        public string Name
        {
            get { return name; }
            set { name = value; }
        }

        public string Email
        {
            get { return email; }
            set { email = value; }
        }
}

{% endhighlight %}
{% endtabs %}

In the `EmployeeViewModel` class, the [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectedItem) is initially updated from the Employees collection.

{% tabs %}
{% highlight c# %}

public class EmployeeViewModel
{
        private List<Employee> employees;
        public List<Employee> Employees
        {
            get { return employees; }

            set { employees = value; }
        }

        private object selectedItem;
        public object SelectedItem
        {
            get { return selectedItem; }

            set { selectedItem = value; }
        }

        public EmployeeViewModel()
        {
            Employees = new List<Employee>();
            Employees.Add(new Employee() { Name = "Eric", Email = "Eric@syncfusion.com" });
            Employees.Add(new Employee() { Name = "James", Email = "James@syncfusion.com" });
            Employees.Add(new Employee() { Name = "Jacob", Email = "Jacob@syncfusion.com" });
            Employees.Add(new Employee() { Name = "Jackson", Email = "Jackson@syncfusion.com" });
            Employees.Add(new Employee() { Name = "Lucas", Email = "Lucas@syncfusion.com" });
            SelectedItem = Employees[0];
        }
}

{% endhighlight %}

{% endtabs %}


{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center"                                
                      x:Name="autoComplete"
                      MaxDropDownHeight="100"
                      MultiSelectMode="None"  
                      AutoCompleteMode="Suggest"                                                          
                      SearchItemPath="Name"
                      SelectedItem="{Binding SelectedItem}"
                      AutoCompleteSource="{Binding Employees}"
                      VerticalAlignment="Center"                 
                      Height="40" 
                      Width="200"/>

{% endhighlight %}

{% endtabs %}


![selected item](Single_and_multiple_selection_images/Set_SelectedItem.png)


{% tabs %}

{% highlight c# %}


private void TextBoxExt_SelectedItemChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
         SfTextBoxExt textBoxExt = d as SfTextBoxExt;
         string selectedItem = "";
         if (textBoxExt.SelectedItem != null)
         {
            selectedItem =((textBoxExt.SelectedItem as Employee).Name).ToString();
         }

         MessageBox.Show(selectedItem, "SelectedItem", MessageBoxButton.OK, MessageBoxImage.None);
}

{% endhighlight %}

{% endtabs %}

### Model Class:

{% tabs %}
{% highlight c# %}

public class Employee
{
        string name;
        string email;

        public string Name
        {
            get { return name; }
            set { name = value; }
        }

        public string Email
        {
            get { return email; }
            set { email = value; }
        }
}

{% endhighlight %}
{% endtabs %}

In the `EmployeeViewModel` class, the [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectedItems) is initially updated from the Employees collection.

{% tabs %}
{% highlight c# %}

public class EmployeeViewModel
{
        private List<Employee> employees;
        public List<Employee> Employees
        {
            get { return employees; }

            set { employees = value; }
        }

        private ObservableCollection<object> selectedItems;
        public ObservableCollection<object> SelectedItems
        {
            get { return selectedItems; }

            set { selectedItems = value; }
        }

        public EmployeeViewModel()
        {
            Employees = new List<Employee>();
            SelectedItems = new ObservableCollection<object>();
            Employees.Add(new Employee() { Name = "Eric", Email = "Eric@syncfusion.com" });
            Employees.Add(new Employee() { Name = "James", Email = "James@syncfusion.com" });
            Employees.Add(new Employee() { Name = "Jacob", Email = "Jacob@syncfusion.com" });
            Employees.Add(new Employee() { Name = "Jackson", Email = "Jackson@syncfusion.com" });
            Employees.Add(new Employee() { Name = "Lucas", Email = "Lucas@syncfusion.com" });
            SelectedItems.Add(Employees[2]);
            SelectedItems.Add(Employees[0]);
            SelectedItems.Add(Employees[1]);
        }
}

{% endhighlight %}

{% endtabs %}


{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center"                                
                      x:Name="autoComplete"
                      MaxDropDownHeight="100"
                      MultiSelectMode="Token"  
                      AutoCompleteMode="Suggest"                                                          
                      SearchItemPath="Name"
                      SelectedItems="{Binding SelectedItems}"
                      AutoCompleteSource="{Binding Employees}"
                      VerticalAlignment="Center"                 
                      Height="40" 
                      Width="200"/>

{% endhighlight %}

{% endtabs %}


![selected items](Single_and_multiple_selection_images/Set_SelectedItems.png)

## Retrieving SelectedValue 

The [SelectedValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectedValue) property is used to retrieve selected values from the suggestion list. Set the [ValueMemberPath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_ValueMemberPathProperty) property to define which data to retrieve from `SelectedValue` based on the `SelectedItem` object.


{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Left"                                
                      x:Name="autoComplete"
                      MaxDropDownHeight="100"
                      MultiSelectMode="None"  
                      AutoCompleteMode="Suggest"                                                          
                      SearchItemPath="Name"
                      ValueMemberPath="Email"
                      AutoCompleteSource="{Binding Employees}"
                      VerticalAlignment="Center"                                                      
                      SelectedItemChanged="AutoComplete_SelectedItemChanged"
                      Height="40" 
                      Width="200"/>

{% endhighlight %}

{% highlight c# %}


private void AutoComplete_SelectedItemChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
       SfTextBoxExt textBoxExt = d as SfTextBoxExt;
       if (textBoxExt.SelectedValue != null)
       {
          MessageBox.Show(textBoxExt.SelectedValue.ToString(), "SelectedValue", MessageBoxButton.OK, MessageBoxImage.None);
       }
}

{% endhighlight %}

{% endtabs %}


### Retrieving SuggestionIndex

When an item is selected from the suggestion list, its index can be retrieved using the [SuggestionIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SuggestionIndex) property.


{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Left"                                
                      x:Name="autoComplete"
                      MaxDropDownHeight="100"
                      MultiSelectMode="None"  
                      AutoCompleteMode="Suggest"                                                          
                      SearchItemPath="Name"
                      ValueMemberPath="Email"
                      AutoCompleteSource="{Binding Employees}"
                      VerticalAlignment="Center"                                                      
                      SelectedItemChanged="AutoComplete_SelectedItemChanged"
                      Height="40" 
                      Width="200"/>

{% endhighlight %}

{% highlight c# %}


private void AutoComplete_SelectedItemChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
        string suggestionIndex = "";
        suggestionIndex = ((d as SfTextBoxExt).SuggestionIndex).ToString();
        MessageBoxResult messageBoxResult = MessageBox.Show(suggestionIndex, "SuggestionIndex");
}

{% endhighlight %}

{% endtabs %}

## Displaying Images

This feature allows setting a path for images to be displayed in the text box control using the [ImageMemberPath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_ImageMemberPath) property.

> Note: This feature is applicable only with `MultiSelectMode` set to Token mode.

For more details, refer to [Showing image in token and dropdown](https://help.syncfusion.com/wpf/autocomplete/autocomplete-and-filtering#showing-image-in-token-and-drop-down).

> Note: View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Single-and-multiple-selection) on GitHub.
