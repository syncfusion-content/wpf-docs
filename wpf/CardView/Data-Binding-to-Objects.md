---
layout: post
title: Data-Binding-to-Objects
description: data-binding to objects
platform: wpf
control: CardView
documentation: ug
---

# Data-Binding to Objects

The CardView control can also support data-binding to objects. The following example shows this.

1. Create a class that act as a model for CardViewItem as follows.

[C#]

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

                    if (this.Age &lt; 1 || this.Age &gt; 100)

                    {

                        result = "Invalid Age";

                    }

                }

                return result;

            }

        }



        #endregion

    }







2. Create a ViewModel class and initialize the items as follows.

[C#]

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

            Contacts.Add(new Contact() { Name = "John", Age = 26});

            Contacts.Add(new Contact() { Name = "Mark",  Age = 25 });

            Contacts.Add(new Contact() { Name = "Steven", Age = 26});



        }

    }





3. Create a ViewModel instance and use it as DataContext for the root window.

[XAML]

&lt;Window.DataContext&gt;

   &lt;local:ViewModel/&gt;

&lt;/Window.DataContext&gt;







4. Configure the ItemTemplate and HeaderTemplate for the CardView control.

[XAML]

      &lt;syncfusion:CardView ItemsSource="{Binding Contacts}" &gt;

          &lt;syncfusion:CardView.ItemTemplate&gt;

                    &lt;DataTemplate &gt;

                        &lt;ListBox ScrollViewer.HorizontalScrollBarVisibility="Disabled"&gt;

                            &lt;ListBoxItem&gt;

                                &lt;StackPanel Orientation="Horizontal"&gt;

                                    &lt;TextBlock Text="Name:"/&gt;

                                    &lt;TextBlock Text="{Binding Name}" Margin="5,0,0,0"/&gt;

                                &lt;/StackPanel&gt;

                            &lt;/ListBoxItem&gt;



                            &lt;ListBoxItem&gt;

                                &lt;StackPanel Orientation="Horizontal"&gt;

                                    &lt;TextBlock Text="Age    :"/&gt;

                                    &lt;TextBlock Text="{Binding Age}" Margin="5,0,0,0"/&gt;

                                &lt;/StackPanel&gt;

                            &lt;/ListBoxItem&gt;

                        &lt;/ListBox&gt;

                    &lt;/DataTemplate&gt;

                &lt;/syncfusion:CardView.ItemTemplate&gt;

                 &lt;syncfusion:CardView.HeaderTemplate&gt;

                           &lt;DataTemplate&gt;

                                &lt;TextBlock Text="{Binding Name}"/&gt;

                           &lt;/DataTemplate&gt;

                 &lt;/syncfusion:CardView.HeaderTemplate&gt;

       &lt;/syncfusion:CardView&gt;





This creates the following CardView control.

{ ![](Data-Binding-to-Objects_images/Data-Binding-to-Objects_img1.png) | markdownify }
{:.image }


_CardView with object binding_

