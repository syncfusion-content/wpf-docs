---
layout: post
title: Populating-Data
description: populating data
platform: wpf
control: DomainUpDown
documentation: ug
---

# Populating Data

The DomainUpDown control can be populated with a predefined list of items. 

For example, in the following code, the DomainUpDown populates a list of employees:

{%highlight c#%}





public class Employee

    {

        public string Name { get; set; }



        public string Email { get; set; }

    }



{%endhighlight%}

Create a collection attribute:

{%highlight c#%}





private List<Employee> employees;



     public List<Employee> Employees

     {

         get { return employees; }

         set { employees = value; }

     }


{%endhighlight%}


Populate the collection with items:

{%highlight c#%}





Employees = new List<Employee>();

Employees.Add(new Employee{Name = "Lucas", Email = "lucas@syncfusion.com"});

Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });

Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });


{%endhighlight%}


## ItemsSource

Bind the Employees collection to the ItemsSource property of DomainUpDown:

{%highlight c#%}





<Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf">

    <Grid>

        <editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"

                              ItemsSource="{Binding Employees}" >           

        </editors:SfDomainUpDown>

    </Grid>

</Page>



{%endhighlight%}

> Note: When the ContentTemplate property of the DomainUpDown control is not set, Items will be displayed as business objects in the control.

## ContentTemplate

ContentTemplate helps the user decorate the content with visual elements. At this point, the control is populated with list of employees, and the Employee model contains two properties: Name and Email. In this example, the control is set to display content based on Name.

{%highlight xml%}





<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"

                              ItemsSource="{Binding Employees}">

            <editors:SfDomainUpDown.ContentTemplate>

                <DataTemplate>

                    <StackPanel Orientation="Horizontal">

                        <Image Height="24" Width="24" Source="Image.png"/>

                        <TextBlock Text="{Binding Name}"/>

                    </StackPanel>

                </DataTemplate>

            </editors:SfDomainUpDown.ContentTemplate>

</editors:SfDomainUpDown>

{%endhighlight%}



![](Populating-Data_images/Populating-Data_img1.png)


