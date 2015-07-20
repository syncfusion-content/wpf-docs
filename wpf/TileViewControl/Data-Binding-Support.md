---
layout: post
title: Data-Binding-Support
description: data binding support
platform: wpf
control: TileView Control
documentation: ug
---

# Data Binding Support

Data Binding is the process of establishing a connection between the application UI and business logic. To bind the business object collection, ItemSource and ItemTemplate properties are used. You can bind the data object to any control and show them in the TileViewItem.

Adding Data Binding to an Application 

Data Binding can be added to an application by using either XAML or C# code.

The following code example illustrates how to add the Data Binding to an application through XAML and C#.



[XAML]



&lt;DataTemplate x:Name="header"&gt;

     &lt;StackPanel Orientation="Horizontal"&gt;

         &lt;Image Source="Images/messages.png"/&gt;

         <TextBlock Text="{Binding Name}" FontFamily="Verdana" 

                    FontSize="18" Foreground="Blue"/>                      

     &lt;/StackPanel&gt;

&lt;/DataTemplate&gt;

<syncfusion:TileViewControl x:Name="TileView1" 

            ItemsSource="{Binding TileViewItemData, ElementName=Cont}"

            Width="600" Height="400"                          

            HeaderTemplate="{Binding Source={StaticResource header}}">        

            &lt;syncfusion:TileViewControl.ItemTemplate&gt;                

                &lt;DataTemplate&gt;            

                    &lt;StackPanel Orientation="Vertical"&gt;

                      &lt;StackPanel Orientation="Horizontal"&gt;

                        <TextBlock Text="Name :" FontFamily="Trebuchet MS" 

                                    Foreground="Brown" FontSize="14"/>

                        &lt;TextBlock Text="{Binding Name}"/&gt;

                      &lt;/StackPanel&gt;

                      &lt;StackPanel Orientation="Horizontal"&gt;

                        <TextBlock Text="Age :" FontFamily="Trebuchet MS" 

                                    Foreground="Brown" FontSize="14"/>

                        &lt;TextBlock Text="{Binding Age}"/&gt;

                      &lt;/StackPanel&gt;

                      &lt;StackPanel Orientation="Horizontal"&gt;

                        <TextBlock Text="Dept :" FontFamily="Trebuchet MS" 

                                   Foreground="Brown" FontSize="14"/>

                        &lt;TextBlock Text="{Binding Dept}" /&gt;

                      &lt;/StackPanel&gt;

                    &lt;/StackPanel&gt;

                &lt;/DataTemplate&gt;

            &lt;/syncfusion:TileViewControl.ItemTemplate&gt;

        &lt;/syncfusion:TileViewControl&gt;







 [C#]

public ObservableCollection<object> TileViewItemData

        {  get;  set;  }



TileViewItemData = new ObservableCollection<object>();

TileViewItemData.Add(new Data(){Name="Jerold", Age=25 , Dept="IT"});

TileViewItemData.Add(new Data(){Name = "Johnson", Age = 22,Dept = "HR" });

TileViewItemData.Add(new Data(){Name = "Thomas", Age = 24,Dept="Network"});

TileViewItemData.Add(new Data(){Name = "Edwin", Age = 24,Dept="Network"});



public class Data

{       

        public Data(){ }                

        public string Name { get; set; }

        public int Age  { get;  set; }

        public string Dept {  get; set; }       

}





{ ![](Data-Binding-Support_images/Data-Binding-Support_img1.png) | markdownify }
{:.image }




Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



