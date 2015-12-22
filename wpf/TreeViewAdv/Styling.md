---
layout: post
title: Styling | TreeViewAdv | wpf | Syncfusion
description: styling
platform: wpf
control: TreeViewAdv
documentation: ug
---

# Styling

The user can apply different styles to the TreeViewAdv. This section list outs the styles that are supported by TreeViewAdv.

## Visual Styles

TreeViewAdv supports the following built-in Visual Styles:

* Office2007Blue
* Office2007Black
* Office2007Silver
* Office2010Blue
* Office2010Black
* Office2010Silver
* Blend
* VS2010
* Metro
* Transparent



The visual style can be applied in XAML as follows:



{% highlight xaml %}

<syncfusion:TreeViewAdv        syncfusion:SkinStorage.VisualStyle="Office2010Blue"/>    

{% endhighlight %}



The TreeViewAdv gets the Office2010Blue look after implementing the above snippet.

Visual styles can be applied in C# as follows:



{% highlight C# %}

SkinStorage.SetVisualStyle(treeviewAdvinstance, "Office2010Blue");


{% endhighlight %}


## ItemContainerStyle

The ItemContainerStyle property of the TreeViewAdv is used to set the style of the TreeViewItemAdv. This style is applied to all the TreeViewItemAdv available in the TreeViewAdv. The following example illustrates how the style can be set using the ItemContainerStyle:

1. Create the Style for TreeViewItemAdv as follows :

   ~~~ css

        <Style TargetType="{x:Type syncfusion:TreeViewItemAdv}" 			x:Key="treeViewAdvItemContainerStyle">

            <Setter Property="IsExpanded" Value="True"/>

            <Setter Property="Foreground" Value="Green"/>

            <Setter Property="IsEditable" Value="False"/>

            <Setter Property="FontStyle" Value="Italic"/>

            <Setter Property="FontWeight" Value="Bold"/>

         </Style>	

   ~~~
   {:.prettyprint }


2. Set the ItemContainerStyle of the TreeViewAdv as follows:

   ~~~ xml

       
       <syncfusion:TreeViewAdv  ItemsSource="{Binding TreeItems}"            

         ItemTemplate="{StaticResource NormalTemplate}"

         ItemContainerStyle="{StaticResource treeViewAdvItemContainerStyle}"

            />

   ~~~
   {:.prettyprint }


The TreeViewAdv will be generated as follows:



![](Styling_images/Styling_img1.png)



##  ItemContainerStyleSelector

The ItemContainerStyleSelector property is used to choose the ItemContainerStyle at runtime base on certain conditions. The following example illustrates how to choose the ItemContainerStyle using the ItemContainerStyleSelector:

1. Create the StyleSelector as given in the following code snippet:

   ~~~ cs

		public class TreeViewAdvItemContainerStyleSelector : StyleSelector

		{
			public override Style SelectStyle(object item, DependencyObject container)

			{
				Window window = Application.Current.MainWindow;


				if (((Model)item).Level == 0)

				{

                return ((Style)window.Resources["RootItemsStyle"]);

				}

				else

				{

					return ((Style)window.Resources["InnerItemsStyle"]);

				}           



			}

		}
		
   ~~~
   {:.prettyprint }




2. Create the style in the Window’s resource as follows:

   ~~~ css

		
       <Style TargetType="{x:Type syncfusion:TreeViewItemAdv}" 		x:Key="RootItemsStyle">

            <Setter Property="IsExpanded" Value="True"/>

            <Setter Property="Foreground" Value="Green"/>

            <Setter Property="IsEditable" Value="False"/>

            <Setter Property="FontStyle" Value="Italic"/>

            <Setter Property="FontWeight" Value="Bold"/>

        </Style>



         <Style TargetType="{x:Type syncfusion:TreeViewItemAdv}" x:Key="InnerItemsStyle">

            <Setter Property="IsExpanded" Value="True"/>

            <Setter Property="Foreground" Value="Blue"/>

            <Setter Property="IsEditable" Value="True"/>

            <Setter Property="FontStyle" Value="Italic"/>           

         </Style>
		
   ~~~
   {:.prettyprint }






3. Define the style selector in the Window’s resource as follows:

   ~~~ xml

       <local:TreeViewAdvItemContainerStyleSelector x:Key="treeViewAdvItemContainerStyleSelector"/>
		
   ~~~
   {:.prettyprint }


4. Set the ItemContainerStyle for the TreeViewAdv as follows:

   ~~~ xml

   
       <syncfusion:TreeViewAdv ItemsSource="{Binding TreeItems}"            

                        ItemTemplate="{StaticResource NormalTemplate}"

                        ItemContainerStyleSelector="{StaticResource treeViewAdvItemContainerStyleSelector}"  />


		
   ~~~
   {:.prettyprint }


The TreeViewAdv generates as shown in the following screen shot:



![](Styling_images/Styling_img2.png)



## Expander Style

The user can customize the style of the expander displayed in the TreeViewAdv using the ExpanderStyle property. The following example illustrates how to customize the style:

1. Create the style for the Expander as given in the following code snippet:

   ~~~ xml
  
       <Style TargetType="{x:Type Expander}" x:Key="expanderStyle">

         <Setter Property="Template" >

         <Setter.Value>
		 
         <ControlTemplate TargetType="{x:Type Expander}">

         <CheckBox IsChecked="{Binding 		Path=IsExpanded,RelativeSource={RelativeSource AncestorType={x:Type 	Expander}}, Mode=TwoWay}"></CheckBox>

         </ControlTemplate>

         </Setter.Value>

         </Setter>

         </Style>
		 
   ~~~
   {:.prettyprint }


2. Set the style to the ExpanderStyle property of the TreeViewAdv.

   ~~~ xml

        <syncfusion:TreeViewAdv ItemsSource="{Binding TreeItems}"            

                        ItemTemplate="{StaticResource NormalTemplate}"

                        ExpanderStyle="{StaticResource expanderStyle}"

                                 />
	
   ~~~
   {:.prettyprint }


The TreeViewAdv generates as shown in the following screenshot:



![](Styling_images/Styling_img3.png)



