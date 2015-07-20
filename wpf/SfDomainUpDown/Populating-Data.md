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



[C#]



public class Employee

    {

        public string Name { get; set; }



        public string Email { get; set; }

    }





Create a collection attribute:



[C#]



private List<Employee> employees;



     public List<Employee> Employees

     {

         get { return employees; }

         set { employees = value; }

     }





Populate the collection with items:



[C#]



Employees = new List<Employee>();

Employees.Add(new Employee{Name = "Lucas", Email = "lucas@syncfusion.com"});

Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });

Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });





ItemsSource

Bind the Employees collection to the ItemsSource property of DomainUpDown:



[C#]



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





> _Note: When the ContentTemplate property of the DomainUpDown control is not set, Items will be displayed as business objects in the control._

ContentTemplate

ContentTemplate helps the user decorate the content with visual elements. At this point, the control is populated with list of employees, and the Employee model contains two properties: Name and Email. In this example, the control is set to display content based on Name.



[XAML]



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





{{ '![C:/Users/ApoorvahR/Desktop/2.png](Populating-Data_images/Populating-Data_img1.png)' | markdownify }}
{:.image }


