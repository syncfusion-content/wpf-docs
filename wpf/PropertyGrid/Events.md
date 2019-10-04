---
layout: post
title: Restrict item generation|Dynamic attribute value change| WPF|PropertyGrid
description: Event to notify the generation of PropertyItem and changing attributes value of the property item
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Restrict generation of property items

Properties of SelectedObject has been read and the properties will be added to the property collection of PropertyGrid. From the collection of property grid, property item will be displayed in the grid. 

## Cancelable event

Generation of property items in the property collection of PropertyGrid can be restricted through `AutoGeneratingPropertyGridItem` event by setting `Cancel` property as `true`.  `AutoGeneratingPropertyGridItemEventArgs` provides the information about the property item of PropertyGrid.

<table>
<tr>
<th> S.No </th>
<th> Argument </th>
<th> Data Type </th>
<th> Details </th>
</tr>
<tr>
<td> 1</td>
<td> DisplayName </td>
<td> String </td>
<td> Specifies the display name of the property item and the display name can be modified through this.
</td>
</tr>
</tr>
<tr>
<td> 2</td>
<td> ReadOnly </td>
<td> Boolean </td>
<td> Specifies whether the property value is editable or not. 
</td>
</tr>
</tr>
<tr>
<td> 3</td>
<td> Description </td>
<td> String </td>
<td> Specifies the description about the property item of the PropertyGrid and the description can be modified through this.
</td>
</tr>
</tr>
<tr>
<td> 4</td>
<td> Category </td>
<td> String </td>
<td> Specifies the Category of property item. Based on the category property items will be grouped and the category can be modified through this.
</td>
</tr>
</tr>
<tr>
<td> 5</td>
<td> Order </td>
<td> Nullable int </td>
<td> Specifies the order of the property item. Based on the order property item will be arranged in the property grid and the order of the property item can be modified through this. 
</td>
</tr>
</table>

{% tabs %}

{% highlight C# %}

    [Editor(typeof(ImageSource), typeof(ImageViewer))]
    public class Person
    {
        public Person()
        {
            FirstName = "Carl";
            LastName = "Johnson";
            Age = 30;
            Mobile = 91983467382;
            Email = "carljohnson@gta.com";
            ID = "0005A";
            DOB = new DateTime(1987, 10, 16);
            string path = System.IO.Path.GetDirectoryName(Assembly.GetEntryAssembly().Location);
            Image = new BitmapImage(new Uri(path + @"\carl.png", UriKind.RelativeOrAbsolute));
            Designation = "Team Lead";
        }
        
        public Gender Gender
        {
            get;

            set;
        }

        public Country Country
        {
            get;

            set;
        }

        public string Email
        {
            get;

            set;
        }

        public string FirstName
        {
            get;

            set;
        }

        public string Designation
        {
            get;

            set;
        }

        public string LastName
        {
            get;

            set;
        }

        public string ID
        {
            get;

            set;
        }

        public DateTime DOB
        {
            get;

            set;
        }

        public long Mobile
        {
            get;

            set;
        }

        public int Age
        {
            get;

            set;
        }

        public ImageSource Image
        {
            get;

            set;
        }
    }
{% endhighlight %}  
{% endtabs %}

{% tabs %}

{% highlight XAML %}
<propertyGrid:PropertyGrid BorderThickness="0" x:Name="pgrid"
                                     SearchBoxVisibility="Visible" 
                                     ButtonPanelVisibility="Visible"
                               DescriptionPanelVisibility="Visible"
                                     DefaultPropertyPath="Age"
                                     AutoGeneratingPropertyGridItem="Pgrid_AutoGeneratingPropertyGridItem"
                                     SortDirection="{x:Null}" EnableGrouping="True"
                                     SelectedPropertyItem="{Binding SelectedPropertyItem, Mode=TwoWay}">

            <propertyGrid:PropertyGrid.SelectedObject>
                <local:Person/>                  
            </propertyGrid:PropertyGrid.SelectedObject>

        </propertyGrid:PropertyGrid>
      
{% endhighlight %}

{% highlight C# %}

private void Pgrid_AutoGeneratingPropertyGridItem(object sender, AutoGeneratingPropertyGridItemEventArgs e)
        {
            if (e.DisplayName == "Image")
            {
                e.Cancel = true;
            }

            if(e.DisplayName == "DOB")
            {
                e.Order = 0;
                e.DisplayName = "Date of Birth";
                e.Category = "Itentity";
                e.Description = "Birth date of the employee";
                e.ReadOnly = true;
            }
        }
      
{% endhighlight %} 

{% endtabs %}

The following screenshot illustrates that the `Image` property item is not displayed in the PropertyGrid, since the item was restricted to be added in collection and all the settings of `DOB` has been modified. 

![Properties are grouped based on the value specified in the Category attribute](Event-Images\Event-PropertyItem.png)

Here, the `Date of Birth` property has been grouped under `Itentity` category

![Properties are grouped based on the value specified in the Category attribute](Event-Images\Event-CategoryItemChanged.png)

