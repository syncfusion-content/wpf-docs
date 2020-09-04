---
layout: post
title: Data Binding to Objects | CardView | wpf | Syncfusion
description: This section explains how to configure the Data-Binding in Syncfusion WPF CardView to the object, and more details.
platform: wpf
control: CardView
documentation: ug
---

# Data-Binding to Objects

The [CardView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html) control can also support data-binding to objects. The following example shows this.

1. Create a class that act as a model for [CardViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardViewItem.html) as follows.

   ~~~ csharp
    public class Contact : IDataErrorInfo
    {
        [Required]
        public string Name
        {
            get;
            set;
        }
        [Range(1, 100)]
        public int Age
        {
            get;
            set;
        }
        #region IDataErrorInfo Members
        public string Error
        {
            get { return this[String.Empty]; }
        }
        public string this[string columnName]
        {
            get
            {
                string result = String.Empty;
                if (columnName == "Name")
                {
                    if (string.IsNullOrEmpty(this.Name))
                    {
                        result = "Name is mandatory";
                    }
                }
                if (columnName == "Age")
                {
                    if (this.Age < 1 || this.Age > 100)
                    {
                        result = "Invalid Age";
                    }
                }
                return result;
            }
        }
        #endregion
    }
   ~~~

2. Create a ViewModel class and initialize the items as follows.

   ~~~ csharp
    public class ViewModel
    {
        public ObservableCollection<Contact> Contacts { get; set; }
        public ViewModel()
        {
            Contacts = new ObservableCollection<Contact>();
            PopulateData();
        }
        private void PopulateData()
        {
            Contacts.Add(new Contact() { Name = "John", Age = 26 });
            Contacts.Add(new Contact() { Name = "Mark", Age = 25 });
            Contacts.Add(new Contact() { Name = "Steven", Age = 26 });
        }
    }
   ~~~

3. Create a ViewModel instance and use it as DataContext for the root window.

   ~~~ xaml
    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>
   ~~~

4. Configure the ItemTemplate and [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_HeaderTemplate) for the CardView control.

  ~~~ xaml
<syncfusion:CardView ItemsSource="{Binding Contacts}" >
    <syncfusion:CardView.ItemTemplate>
        <DataTemplate >
            <ListBox>
                <ListBoxItem>
                    <StackPanel Orientation="Horizontal">
                        <TextBlock Text="Name:"/>
                        <TextBlock Text="{Binding Name}" Margin="5,0,0,0"/>
                    </StackPanel>
                </ListBoxItem>
                <ListBoxItem>
                    <StackPanel Orientation="Horizontal">
                        <TextBlock Text="Age    :"/>
                        <TextBlock Text="{Binding Age}" Margin="5,0,0,0"/>
                    </StackPanel>
                </ListBoxItem>
            </ListBox>
        </DataTemplate>
    </syncfusion:CardView.ItemTemplate>
    <syncfusion:CardView.HeaderTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding Name}"/>
        </DataTemplate>
    </syncfusion:CardView.HeaderTemplate>
</syncfusion:CardView>
  ~~~

[View sample in GitHub](https://github.com/SyncfusionExamples/How-to-bind-objects-in-wpf-card-view)

This creates the following CardView control.

![CardView with object binding](Data-Binding-to-Objects_images/Data-Binding-to-Objects_img1.png)

CardView with object binding
{:.caption}