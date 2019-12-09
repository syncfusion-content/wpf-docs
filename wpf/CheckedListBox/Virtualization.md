---
layout: post
title: Virtualization | CheckListBox | wpf | Syncfusion
description: This section describes how virtualization could be achieved in CheckListBox control.This feature allows the user to load large sets of data without affecting loading or scrolling performance.
platform: wpf
control: CheckListBox
documentation: ug
---

# Virtualization

UI Viratualization is available in CheckListBox, which allows the users to load large sets of data without affecting loading or scrolling performance. This feature allows users to reduce the loading time of CheckListBoxItems regardless of items count.

* **Model.cs**

{% tabs %}
{% highlight C# %}
public class Model
{
    public string Name { get; set; }
    public string GroupName { get; set; }
}
{% endhighlight %}
{% endtabs %}

* **ViewModel.cs**

{% tabs %}
{% highlight C# %}
    public class ViewModel
    {
        private ObservableCollection<Model> collection = new ObservableCollection<Model>();

        public ObservableCollection<Model> Collection
        {
            get
            {
                return collection;
            }
            set
            {
                collection = value;
            }
        }
        public ViewModel()
        {
            Collection = new ObservableCollection<Model>();
            for (int i = 0; i < 10000; i++)
            {
                for (int j = 0; j < 10; j++)
                {
                    Model myitem = new Model() { Name = "Module " + i.ToString(), GroupName = "Group" + j.ToString() };
                    Collection.Add(myitem);
                }
            }
        }
    }
{% endhighlight %}
{% endtabs %}

* **MainWindow.Xaml.cs**
{% tabs %}
{% highlight C# %}

    public class Groups : ObservableCollection<GroupDescription>
    {

    }

{% endhighlight %}
{% endtabs %}

* **MainWindow.Xaml**

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>

<syncfusion:CheckListBox ItemsSource="{Binding Collection}" 
                                 Grid.Row="1" DisplayMemberPath="Name"
                                 IsSelectAllEnabled="False">
            <syncfusion:CheckListBox.GroupDescriptions>
                <local:Groups>
                    <PropertyGroupDescription PropertyName="GroupName"/>
                </local:Groups>
            </syncfusion:CheckListBox.GroupDescriptions>
</syncfusion:CheckListBox>

{% endhighlight %}
{% endtabs %}

![Virtualization](Virtualization_images/Virtualization.png)