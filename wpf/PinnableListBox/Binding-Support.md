---
layout: post
title: Binding Support | PinnableListBox | wpf | Syncfusion
description: binding support
platform: wpf
control: PinnableListBox 
 documentation: ug
---

# Binding Support

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source to target) or bidirectional (source to target and target to source). You can bind the data to the integer textbox through the Value property.

The following example shows a simple binding between the value of the PinnableListBox and another PinnableListBox value that reflects the typed value:

{% highlight xaml %}

 <syncfusion:PinnableListBox DisplayMemberPath="Header" ItemsSource="{Binding Collection}" Header="fhghshdf" 
                    PinItemsSortDescription="SubHeader" UnPinItemsSortDescription="SubHeader" 
                    UnPinnedSortDirection="Ascending" PinnedSortDirection="Descending"
                    HorizontalAlignment="Left"  Name="pinnableListBox1"  Width="218">
 </syncfusion:PinnableListBox>

{% endhighlight %}

{% tabs %}

{% highlight C# %}

public class Model

{

    private string header;

    public string Header
    {
        get { return header; }
        set { header = value; }
    }

    private string subHeader;

    public string SubHeader
    {
        get { return subHeader; }
        set { subHeader = value; }
    }

    private bool isPinned;

    public bool IsPinned
    {
        get { return isPinned; }
        set { isPinned = value; }
    }

}


  public MainWindow()

  {

        InitializeComponent();
        Collection = new ObservableCollection<Model>();
        Collection.Add(new Model { Header = "PivotGrid", SubHeader = "9", IsPinned = false });
        Collection.Add(new Model { Header = "DoubleTextBox", SubHeader = "8", IsPinned = true });
        Collection.Add(new Model { Header = "UpDown", SubHeader = "7", IsPinned = false });
        Collection.Add(new Model { Header = "MaskedTextBox", SubHeader = "6", IsPinned = true });
        Collection.Add(new Model { Header = "AutoComplete", SubHeader = "5", IsPinned = false });
        this.DataContext = this;

  }

  private ObservableCollection<Model> collection;

  public ObservableCollection<Model> Collection
  
  {
  
        get { return collection; }
  
        set { collection = value; }
  
  }


{% endhighlight %}

{% endtabs %}

![](Binding-Support_images/Binding-Support_img1.png)


