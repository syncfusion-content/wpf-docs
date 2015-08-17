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

{% highlight C# %}

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


{% endhighlight %}




2. Create a ViewModel class and initialize the items as follows.

{% highlight C# %}

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


{% endhighlight %}


3. Create a ViewModel instance and use it as DataContext for the root window.

{% highlight xml %}

<Window.DataContext>

   <local:ViewModel/>

</Window.DataContext>


{% endhighlight %}




4. Configure the ItemTemplate and HeaderTemplate for the CardView control.

{% highlight xml %}

      <syncfusion:CardView ItemsSource="{Binding Contacts}" >

          <syncfusion:CardView.ItemTemplate>

                    <DataTemplate >

                        <ListBox ScrollViewer.HorizontalScrollBarVisibility="Disabled">

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


{% endhighlight %}


This creates the following CardView control.

![](Data-Binding-to-Objects_images/Data-Binding-to-Objects_img1.png)

_CardView with object binding_

