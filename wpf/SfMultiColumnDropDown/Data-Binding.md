---
layout: post
title: Data-Binding
description: data binding
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

## Data Binding

In order to display the data in the SfMultiColumnDropDown control, bind the data into the control by using ItemsSource property.

The following code example illustrates how bind the itemsSource to the SfMulticolumnDropDownControl in XAML.
{% highlight xml %}




<Window.DataContext>

<local:Viewmodel/>

</Window.DataContext>



<syncfusion:SfMultiColumnDropDownControl x:Name="sfmulticolumn"

ItemsSource="{Binding EmpDetails}"

DisplayMember="Name"

ValueMember="Designation"                                             

>
										   {% endhighlight %}

The following screenshot illustrates the output of the above code.

![](Features_images/Features_img1.png)



### Binding Collection in CodeBehind

The following code example illustrates how to bind itemsSource to the SfMultiColumnDropDownControl in codebehind.

{% highlight C# %}
 

public MainWindow()

{

  InitializeComponent();  

 sfmulticolumn.ItemsSource = new ObservableCollection<Data>

{

new Data(){Name="Stephen", Designation="Softwareengineer"},City="Washington",Country="USA"



new Data(){Name="Michael", Designation= "AccountsManager"}, City="Parris",Country="France"



new Data(){Name="Mike", Designation= "Senior AccountsManager "}, City="Rom",Country="Italy"



new Data(){Name="Maxwell", Designation= "WebDesigner"}, City="CapeTown",Country="SouthAfrica"

};    

 sfmulticolumn.DisplayMember="Name";

 sfmulticolumn.ValueMember="Designation";

}
{% endhighlight %}


The following screenshot illustrates the output for SfMultiColumnDropDownControl.

![](Features_images/Features_img2.png)



### Complex Property Binding

SfMultiColumnDropDownControl allows you to bind the Complex property to its column. For example, Data class contains “customerDetails” as Customer class type. It also contains Name and Designation property. The column for the complex property is defined in the format of “Property.Member”.

The following code example illustrate how to bind Complex property in SfMultiColumnDropDownControl,

{% tabs %}
{% highlight C# %}



public class Data:INotifyPropertyChanged

    {

       public string name;

       public string designation;

       public string city;

       public string country;

       Customer customer = new Customer();

       public event PropertyChangedEventHandler PropertyChanged;



       public Customer customerDetails

       {

           get { return customer; }

           set { customer = value; }



       }



       public string Name

       {

           get { return name; }

           set { name = value; RaisePropertyChanged("Name"); 

           }

       }

       public string Designation

       {

           get { return designation; }

           set { designation = value;RaisePropertyChanged("Designation"); 

           }

       }

        public string City

        {

            get { return city; }

            set { city = value; RaisePropertyChanged("City"); }

        }



        public string Country

        {

            get { return country; }

            set { country = value; RaisePropertyChanged("Country"); }

        }



        protected virtual void RaisePropertyChanged(string propertyName)

        {

            var handler = PropertyChanged;

            if (handler != null)

                handler(this, new PropertyChangedEventArgs(propertyName));

        }



     public Data(string _name,string _designation,string _city,string _country)

       {

           this.Name = _name;

           this.customerDetails.Name = _name;

           this.customerDetails.Designation = _designation;

           this.City = _city;

           this.Country = _country;

       }



    }
{% endhighlight %}


{% highlight xml %}




	<syncfusion:SfMultiColumnDropDownControl x:Name="sfmulticolumn"

	   SelectedIndex="1"

	   AutoGenerateColumns="False"

	   ItemsSource="{Binding EmpDetails}"

	   DisplayMember="Name"

	   ValueMember="City"                                                                                           

			 >

	<syncfusion:SfMultiColumnDropDownControl.Columns>

	<syncfusion:Columns>

	<syncfusion:GridTextColumn MappingName="Name" />

	<syncfusion:GridTextColumn MappingName="customerDetails.Designation" />

	<syncfusion:GridTextColumn MappingName="City" />

	<syncfusion:GridTextColumn MappingName="Country" />

	</syncfusion:Columns>

	</syncfusion:SfMultiColumnDropDownControl.Columns>

</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% endtabs %}
The following screenshot illustrates the output for Complex property binding in SfMultiColumnDropDownControl.

![](Features_images/Features_img3.png)



