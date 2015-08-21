---
layout: post
title: Customizing-Data-Templates
description: customizing data templates
platform: wpf
control: TreeViewAdv
documentation: ug
---

# Customizing Data Templates

This section explains about customizing the TreeViewItemAdv using DataTemplate.

## ItemTemplate 

The user can customize the business object that has to be displayed as TreeViewItemAdv using the ItemTemplate of TreeViewAdv. Since TreeViewAdv displays the hierarchical data, the HierarchicalDataTemplate is used to define the ItemTemplate. In the following example, business object is displayed as CheckBox:



{% highlight xml %}

<HierarchicalDataTemplate ItemsSource="{Binding Models}">



    <CheckBox Content="{Binding Caption}" IsChecked="{Binding 			Path=IsChecked,Mode=TwoWay}"/>



</HierarchicalDataTemplate>

{% endhighlight %}



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img1.png)


The icon in front of the checkbox is created using the LeftImageSource option available in the TreeViewItemADv.



## Item Template Selector

Different templates can be used for items based on specific constraints using the ItemTemplateSelector. 

The following example illustrates this:

1.Create the template selector as shown in the following code snippet:



{% highlight C# %}

public class TreeViewAdvItemTemplateSelector : DataTemplateSelector

    {

 public override DataTemplate SelectTemplate(object item, 			DependencyObject container)

        {

            Window window = Application.Current.MainWindow;



            if (((Model)item).IsCheckable)

            {

                return ((DataTemplate)window.Resources["CheckableTemplate"]);

            }

            else 

            {

                return ((DataTemplate)window.Resources["NormalTemplate"]);

            }     

}

    }



{% endhighlight %}



2.Define the Data templates in the Window’s resources as follows:



{% highlight xml %}

<HierarchicalDataTemplate ItemsSource="{Binding SubItems}" 		x:Key="CheckableTemplate">



     <CheckBox Content="{Binding Header}" />



</HierarchicalDataTemplate>



<HierarchicalDataTemplate ItemsSource="{Binding SubItems}" 						x:Key="NormalTemplate">



    <TextBlock Text="{Binding Header}" />



</HierarchicalDataTemplate>

{% endhighlight %}


3.Create the instance for the template selector in the Window’s resources as follows:



{% highlight xml %}

<local:TreeViewAdvItemTemplateSelector x:Key="treeViewItemTemplateSelector"/>


{% endhighlight %}


4.Use the template selector to choose the template for the TreeViewAdv as follows:



{% highlight xml %}

<syncfusion:TreeViewAdv ItemsSource="{Binding TreeItems}" 		ItemTemplateSelector="{StaticResource treeViewItemTemplateSelector}">           

</syncfusion:TreeViewAdv>

{% endhighlight %}

The TreeVewAdv generates as shown in the following screenshot:



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img2.png)


## Edit Template

The user can modify the template while editing the TreeViewItemAdv. The following example illustrates the process of changing the template:

1.Create the DataTemplate instance for the EditTemplate as follows: 



{% highlight xml %}

<DataTemplate x:Key="EditTemplate">



      <TextBox Text="{Binding Header}" FontStyle="Italic" 				FontWeight="Bold" />



</DataTemplate>


{% endhighlight %}


2.Set the EditedItemTemplate for the TreeViewAdv to the above template as follows:


{% highlight xml %}

<syncfusion:TreeViewAdv EditedItemTemplate="{StaticResource EditTemplate}" ItemsSource="{Binding TreeItems}" >

</syncfusion:TreeViewAdv>


{% endhighlight %}


While editing the TreeViewItemAdv appears as shown in the following screen shot:



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img3.png)




## Edit Template Selector

The user can choose the template at runtime for editing the TreeViewAdv. 

The following example explains how to choose the template at runtime:

1.Create the template selector as given in the following code snippet:



{% highlight C# %}

public class TreeViewAdvEditTemplateSelector : DataTemplateSelector

  {

  public override DataTemplate SelectTemplate(object item, 					DependencyObject container)

    {

      Window window = Application.Current.MainWindow;



      if (((Model)item).IsCheckable)

            {

      	return ((DataTemplate)window.Resources["CheckableEditTemplate"]);

            }

            else

            {

             return ((DataTemplate)window.Resources["NormalEditTemplate"]);

            }

        }

    }

{% endhighlight %}


2.Define the Data templates in the Window’s resources as follows:



{% highlight xml %}

<DataTemplate  x:Key="CheckableEditTemplate">

  <TextBox Text="{Binding Header}" FontStyle="Italic" 		FontWeight="Bold" Foreground="Blue"/>

</DataTemplate>



<DataTemplate  x:Key="NormalEditTemplate">

     <TextBox Text="{Binding Header}" FontStyle="Italic" FontWeight="Bold" 	Foreground="Green"/>

</DataTemplate>

{% endhighlight %}



3.Create the instance for the template selector in the Window’s resources as follows:



{% highlight xml %}

<local:TreeViewAdvEditTemplateSelector x:Key="treeViewAdvEditTemplateSelector"/>

{% endhighlight %}



4.Use the template selector to choose the template for the TreeViewAdv as follows:



{% highlight xml %}

<syncfusion:TreeViewAdv 

EditedItemTemplateSelector="{StaticResource treeViewAdvEditTemplateSelector}"

ItemsSource="{Binding TreeItems}" />           

{% endhighlight %}

The TreeViewAdv generates as shown in the following screenshot:



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img4.png)



