---
layout: post
title: Adding items to the ComboBoxAdv | wpf | Syncfusion
description: adding items to comboboxadv 
platform: wpf
control: ComboBoxAdv
documentation: ug
---

## ComboBoxItemAdv 

It can be added inside the ComboBoxAdv control. It is originally derived from the ComboBoxItem.

## Sample link

To view samples:

1. Run samples from installed location.
   Example: C:\Program Files (x86)\Syncfusion\Essential Studio\XX.X.X.XX\Samples
2. Now move to WPF folder in which WPF samples has been present.
4. Choose ComboBox from Tools.WPF to run ComboBoxAdv demo.

## Adding items using DataBinding  

You can use the `DisplayMemberPath` property to set the value for items that needs to be displayed in the drop-down list.The below code snippet will be used to bind the DataSource to the ComboBoxAdv.

{% tabs %}
{% highlight xaml %}

<syncfusion:ComboBoxAdv Name="comboBoxAdv" ItemsSource="{Binding Products}"               DisplayMemberPath="Name"                                                         SelectedValue="{Binding SelectedItems, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}" />

{% endhighlight %}

{% highlight c# %}

public class Model
{ 
    public string Name { get; set; }
}
    public class ViewModel : INotifyPropertyChanged
    {
        private string selectedItems;
        public string SelectedItems
        {
            get
            {
                return selectedItems;
            }
            set
            {
                selectedItems = value;
                RaisePropertyChanged("SelectedItems");
            }
        }
        private ObservableCollection<Model> products;
        public ObservableCollection<Model> Products
        {
            get 
            { 
                return products; 
            }
            set 
            {
                products = value;
                RaisePropertyChanged("Products");
            }
        }
        public ViewModel()
        {
            Products = new ObservableCollection<Model1>();

            Products.Add(new Model() { Name = "UK" });
            Products.Add(new Model() { Name = "CA " });
            Products.Add(new Model() { Name = "DE" });
            Products.Add(new Model() { Name = "IN" });
            Products.Add(new Model() { Name = "UA" });
        }
        public event PropertyChangedEventHandler PropertyChanged;
        public void RaisePropertyChanged(string propertyName)
        {
            var property = PropertyChanged;
            if (property != null)
             property(this, new PropertyChangedEventArgs(propertyName));
        }
    }
{% endhighlight %}
{% endtabs %}
