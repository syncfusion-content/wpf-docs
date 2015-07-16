---
layout: post
title: Styles-and-Templates
description: styles and templates
platform: wpf
control: TreeViewAdv
documentation: ug
---

# Styles and Templates

This section deals with the following Styles and Templates supported by TreeViewAdv control. 

## Setting Drag Indicator Style

You can customize the style of the Drag Indicator which is used to indicate the drag-and-drop operation in progress by using the DragIndicatorStyle property. The following code example illustrates how to set this property.



[XAML]



<Window x:Class="WpfApplication2.Window1"

    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

    Title="Window1" Height="300" Width="300">

    &lt;Window.Resources&gt;



        &lt;!-- Creating the style for DragIndicator --&gt;

        &lt;Style x:Key="Drag_Marker" TargetType="{x:Type syncfusion:TemplatedAdornerInternalControl}"&gt;

            &lt;Setter Property="HorizontalAlignment" Value="Left"/&gt;

            &lt;Setter Property="VerticalAlignment" Value="Top"/&gt;

            &lt;Setter Property="SnapsToDevicePixels" Value="False"/&gt;

            &lt;Setter Property="Template"&gt;

                &lt;Setter.Value&gt;

                    &lt;ControlTemplate TargetType="{x:Type syncfusion:TemplatedAdornerInternalControl}"&gt;

                        &lt;Grid&gt;

                            &lt;Grid.ColumnDefinitions&gt;

                                &lt;ColumnDefinition Width="*"/&gt;

                            &lt;/Grid.ColumnDefinitions&gt;

                            &lt;Rectangle Grid.Column="0" Height="4" Fill="Red"/&gt;

                        &lt;/Grid&gt;

                    &lt;/ControlTemplate&gt;

                &lt;/Setter.Value&gt;

            &lt;/Setter&gt;

        &lt;/Style&gt;

    &lt;/Window.Resources&gt;

    &lt;Grid&gt;



        &lt;!-- Adding TreeViewAdv with DragIndicatorStyle --&gt;

        &lt;syncfusion:TreeViewAdv DragIndicatorStyle="{StaticResource Drag_Marker}"  Name="treeViewAdv"&gt;



            &lt;!-- Adding TreeViewItemAdv --&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Marital Status"&gt;

                &lt;syncfusion:TreeViewItemAdv Header="Single"/&gt;

                &lt;syncfusion:TreeViewItemAdv Header="Married"/&gt;

                &lt;syncfusion:TreeViewItemAdv Header="Married with Children"/&gt;

            &lt;/syncfusion:TreeViewItemAdv&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Baby Vaccines"&gt;

                &lt;syncfusion:TreeViewItemAdv Header="Hepatitis B"/&gt;

                &lt;syncfusion:TreeViewItemAdv Header="Tetanus"/&gt;

                &lt;syncfusion:TreeViewItemAdv Header="Polio"/&gt;

                &lt;syncfusion:TreeViewItemAdv Header="Measles"/&gt;

            &lt;/syncfusion:TreeViewItemAdv&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Country Information"/&gt;

        &lt;/syncfusion:TreeViewAdv&gt;

    &lt;/Grid&gt;

&lt;/Window&gt;



{ ![](Styles-and-Templates_images/Styles-and-Templates_img1.jpeg) | markdownify }
{:.image }




## Setting Header Template

User can customize the header of the treeview item by using HeaderTemplate using the below code snippet.



[XAML]



<Window x:Class="WpfApplication2.Window1"

    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

    Title="Window1" Height="300" Width="300">

  &lt;Window.Resources&gt;

    &lt;DataTemplate x:Key="HD1"&gt;

      &lt;StackPanel Orientation="Horizontal"&gt;

        &lt;TextBlock FontWeight="Bold" Text="Marital Status" /&gt;

      &lt;/StackPanel&gt;

    &lt;/DataTemplate&gt;

  &lt;/Window.Resources&gt;



  &lt;Grid&gt;



    &lt;!-- Adding TreeViewAdv with HeaderTemplate --&gt;

    &lt;syncfusion:TreeViewAdv Name="treeViewAdv"&gt;



      &lt;!-- Adding TreeViewItemAdv --&gt;

      &lt;syncfusion:TreeViewItemAdv Name="treeViewItemAdv1" HeaderTemplate="{StaticResource HD1}"&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Single"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Married"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Married with Children"/&gt;

      &lt;/syncfusion:TreeViewItemAdv&gt;

    &lt;/syncfusion:TreeViewAdv&gt;

  &lt;/Grid&gt;

&lt;/Window&gt;



{ ![](Styles-and-Templates_images/Styles-and-Templates_img2.jpeg) | markdownify }
{:.image }




## Setting Expand Style

The ExpanderStyle property enables to customize the appearance and style of expansion of the TreeViewAdv during the Expand or Collapse operation. The following code example illustrates how to set this property.



[XAML]



&lt;Window.Resources&gt;



    &lt;!-- Template for TreeViewAdvExpander --&gt;

    &lt;ControlTemplate x:Key="MyFxExpanderTemplateKey" TargetType="{x:Type Expander}"&gt;

        &lt;ToggleButton Name="Expander" ClickMode="Press" IsChecked="{Binding Path=IsExpanded, RelativeSource={RelativeSource TemplatedParent}}"&gt;

            &lt;ToggleButton.Style&gt;

                &lt;Style TargetType="ToggleButton"&gt;

                    &lt;Setter Property="FrameworkElement.Focusable" Value="False"/&gt;

                    &lt;Setter Property="FrameworkElement.Width" Value="19"/&gt;

                    &lt;Setter Property="FrameworkElement.Height" Value="13"/&gt;

                    &lt;Setter Property="Control.Template"&gt;

                        &lt;Setter.Value&gt;

                            &lt;ControlTemplate TargetType="ToggleButton"&gt;

                                &lt;Border Height="10" Width="10" BorderBrush="Black" BorderThickness="1"&gt;

                                    &lt;Border Name="BackgroundBorder"  Background="Blue"/&gt;

                                &lt;/Border&gt;

                                &lt;ControlTemplate.Triggers&gt;

                                    &lt;Trigger Property="ToggleButton.IsChecked" Value="True"&gt;

                                        &lt;Setter Property="Background" TargetName="BackgroundBorder" Value="Red"/&gt;

                                    &lt;/Trigger&gt;

                                &lt;/ControlTemplate.Triggers&gt;

                            &lt;/ControlTemplate&gt;

                        &lt;/Setter.Value&gt;

                    &lt;/Setter&gt;

                &lt;/Style&gt;

            &lt;/ToggleButton.Style&gt;

        &lt;/ToggleButton&gt;

    &lt;/ControlTemplate&gt;



    &lt;!-- Style for TreeViewAdvExpander --&gt;

    &lt;Style x:Key="MyEStyle" TargetType="{x:Type Expander}"&gt;

        &lt;Setter Property="Template" Value="{StaticResource MyFxExpanderTemplateKey}"/&gt;

    &lt;/Style&gt;

&lt;/Window.Resources&gt;

&lt;Grid&gt;



    &lt;!-- Adding TreeViewAdv with expand animation --&gt;

    &lt;syncfusion:TreeViewAdv Name="treeViewAdv" ExpanderStyle="{DynamicResource MyEStyle}"&gt;



        &lt;!-- Adding TreeViewItemAdv --&gt;

        &lt;syncfusion:TreeViewItemAdv Name="treeViewItemAdv" Header="Marital Status"&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Single"/&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Married"/&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Married with Children"/&gt;

        &lt;/syncfusion:TreeViewItemAdv&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Baby Vaccines"&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Hepatitis B"/&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Tetanus"/&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Polio"/&gt;

            &lt;syncfusion:TreeViewItemAdv Header="Measles"/&gt;

        &lt;/syncfusion:TreeViewItemAdv&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Country Information"/&gt;

    &lt;/syncfusion:TreeViewAdv&gt;

&lt;/Grid&gt;





{ ![](Styles-and-Templates_images/Styles-and-Templates_img3.jpeg) | markdownify }
{:.image }




## Setting Cell Template

You can customize the items under a column header by defining a cell template for the TreeViewColumns. To create a cell template use the below code



[XAML]



&lt;!-- Adding TreeViewAdv with Enabling multiple column --&gt;

&lt;syncfusion:TreeViewAdv Name="treeViewAdv" MultiColumnEnable="True"&gt;



  &lt;!-- Adding TreeViewItemAdv --&gt;

  &lt;syncfusion:TreeViewItemAdv Name="treeViewItemAdv" Header="Marital Status"&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Single"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Married"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Married with Children"/&gt;

  &lt;/syncfusion:TreeViewItemAdv&gt;

  &lt;syncfusion:TreeViewItemAdv Header="Baby Vaccines"&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Hepatitis B"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Tetanus"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Polio"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Measles"/&gt;

  &lt;/syncfusion:TreeViewItemAdv&gt;

  &lt;syncfusion:TreeViewItemAdv Header="Country Information"&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Canada"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="France"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="Germany"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="UK"/&gt;

    &lt;syncfusion:TreeViewItemAdv Header="USA"/&gt;

  &lt;/syncfusion:TreeViewItemAdv&gt;



  &lt;!-- Adding header --&gt;

  &lt;syncfusion:TreeViewAdv.Columns&gt;

    &lt;syncfusion:TreeViewColumnCollection&gt;

      <syncfusion:TreeViewColumn Width="150" Header="Status"

       DisplayMemberBinding="{Binding Path=Header, RelativeSource={RelativeSource AncestorType={x:Type 			syncfusion:TreeViewItemAdv}}}"/>

      <syncfusion:TreeViewColumn Width="100" Header="Vaccines"

       DisplayMemberBinding="{Binding Path=Header, RelativeSource={RelativeSource AncestorType={x:Type 			syncfusion:TreeViewItemAdv}}}"/>

      &lt;syncfusion:TreeViewColumn Width="50" Header="Country"&gt;



        &lt;!-- Cell Template --&gt;

        &lt;syncfusion:TreeViewColumn.CellTemplate&gt;

          &lt;DataTemplate&gt;

            &lt;Border Margin="1" Width="150" BorderBrush="Red" BorderThickness="1"&gt;

              &lt;TextBlock Margin="2" Text="{Binding Path=Header, RelativeSource={RelativeSource 					AncestorType={x:Type syncfusion:TreeViewItemAdv}}}"/&gt;

            &lt;/Border&gt;

          &lt;/DataTemplate&gt;

        &lt;/syncfusion:TreeViewColumn.CellTemplate&gt;

      &lt;/syncfusion:TreeViewColumn&gt;

    &lt;/syncfusion:TreeViewColumnCollection&gt;

  &lt;/syncfusion:TreeViewAdv.Columns&gt;

&lt;/syncfusion:TreeViewAdv&gt;





{ ![](Styles-and-Templates_images/Styles-and-Templates_img4.jpeg) | markdownify }
{:.image }




## Setting Item Container Style

To set the style for the item container, use ItemContainerStyle property. This dependency property can be applied to TreeViewAdv, as well as TreeViewItemAdv. 

The following example can be used to set this property.



[XAML]



&lt;Grid&gt;

     &lt;Grid.Resources&gt;

           &lt;Style x:Key="TreeViewItemStyle2" TargetType="{x:Type syncfusion:TreeViewItemAdv}"&gt;

               &lt;Setter Property="LeftImageSource" Value="Resources/App.ico" /&gt;

               &lt;Setter Property="ImageHeight" Value="16" /&gt;

               &lt;Setter Property="ImageWidth" Value="16" /&gt;

            &lt;/Style&gt;

            &lt;Style TargetType="{x:Type syncfusion:TreeViewItemAdv}"&gt;

                &lt;Setter Property="ItemContainerStyle" Value="{StaticResource TreeViewItemStyle2}"/&gt;

            &lt;/Style&gt;

     &lt;/Grid.Resources&gt;

     &lt;syncfusion:TreeViewAdv&gt;

         &lt;syncfusion:TreeViewItemAdv Header="Root" IsExpanded="True"&gt;

          &lt;syncfusion:TreeViewItemAdv Header="sub-1"/&gt;

          &lt;syncfusion:TreeViewItemAdv Header="sub-2"/&gt;

          &lt;syncfusion:TreeViewItemAdv Header="sub-3"/&gt;

          &lt;syncfusion:TreeViewItemAdv Header="sub-4"/&gt;

          &lt;syncfusion:TreeViewItemAdv Header="sub-5"/&gt;

          &lt;/syncfusion:TreeViewItemAdv&gt;

     &lt;/syncfusion:TreeViewAdv&gt;

&lt;/Grid&gt;



The following screen shot shows how the TreeViewAdv looks after applying ItemContainerStyle property.



{ ![](Styles-and-Templates_images/Styles-and-Templates_img5.jpeg) | markdownify }
{:.image }




## Using Edit Item Template in TreeViewAdv

User can customize the edited item by using the EditedItemTemplate property, which gets or sets the DataTemplate that is used to display each item in edit mode. 



[XAML]



<Window x:Class="WpfApplication2.Window1"

    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

    Title="Window1" Height="300" Width="300">

  &lt;Window.Resources&gt;



    &lt;!-- CustomEditedItemTemplate --&gt;

    &lt;DataTemplate x:Key="CustomEditedItemTemplate" DataType="{x:Type syncfusion:TreeViewItemAdv}"&gt;

      &lt;Border BorderBrush="Red" Background="Orange"  BorderThickness="1" Margin="1" Padding="2"&gt;

        &lt;TextBox Foreground="Green" Text="{Binding Path=(syncfusion:TreeViewItemAdv.Header), Mode=TwoWay, RelativeSource={RelativeSource AncestorType={x:Type syncfusion:TreeViewItemAdv}}}"/&gt;

      &lt;/Border&gt;

    &lt;/DataTemplate&gt;

  &lt;/Window.Resources&gt;

  &lt;Grid&gt;



    &lt;!-- Adding TreeViewAdv with CustomEditedItemTemplate --&gt;

    &lt;syncfusion:TreeViewAdv Name="treeViewAdv" EditedItemTemplate="{StaticResource CustomEditedItemTemplate}"&gt;



      &lt;!-- Adding TreeViewItemAdv --&gt;

      &lt;syncfusion:TreeViewItemAdv Name="treeViewItemAdv1" Header="Marital Status"&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Single"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Married"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Married with Children"/&gt;

      &lt;/syncfusion:TreeViewItemAdv&gt;

      &lt;syncfusion:TreeViewItemAdv Name="treeViewItemAdv2" Header="Baby Vaccines"&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Hepatitis B"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Tetanus"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Polio"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Measles"/&gt;

      &lt;/syncfusion:TreeViewItemAdv&gt;

      &lt;syncfusion:TreeViewItemAdv Header="Country Information"&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Canada"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="France"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="Germany"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="UK"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="USA"/&gt;

      &lt;/syncfusion:TreeViewItemAdv&gt;

    &lt;/syncfusion:TreeViewAdv&gt;

  &lt;/Grid&gt;

&lt;/Window&gt;





{ ![](Styles-and-Templates_images/Styles-and-Templates_img6.jpeg) | markdownify }
{:.image }




EditedItemTemplateSelector

Allows the application writer to provide custom logic for choosing a template that is used to display each item in edit mode. It is a custom DataTemplateSelector object that provides logic and returns a DataTemplate. The default value is null reference.



[C#]



/// &lt;StackPanel Name="stackPanel"&gt;

/// &lt;local:TreeViewAdv Name="myTreeview"&gt;

///     <local:TreeViewItemAdv Header="Employee1"

///      EditedItemTemplateSelector="{StaticResource auctionItemDataTemplateSelector}">

///         &lt;local:TreeViewItemAdv Header="Jesper"/&gt;

///         &lt;local:TreeViewItemAdv Header="Aaberg"/&gt;

///         &lt;local:TreeViewItemAdv Header="12345"/&gt;

///     &lt;/local:TreeViewItemAdv&gt;

///     &lt;local:TreeViewItemAdv Header="Employee2"&gt;

///         &lt;local:TreeViewItemAdv Header="Dominik"/&gt;

///         &lt;local:TreeViewItemAdv Header="Paiha"/&gt;

///         &lt;local:TreeViewItemAdv Header="98765"/&gt;

///     &lt;/local:TreeViewItemAdv&gt;

/// &lt;/local:TreeViewAdv&gt;

/// &lt;/StackPanel&gt;

/// &lt;/Window&gt;

/// ]]>

/// &lt;/code&gt;

///

/// <para/>The following example shows the implementation 

/// of the <I>AuctionItemDataTemplateSelector</I> class with 

/// an override of the SelectTemplate method:

/// &lt;code language="C#"&gt;

/// using System.Windows;

/// using System.Windows.Controls;

/// 

/// namespace SDKSample

/// {

///     public class AuctionItemDataTemplateSelector : DataTemplateSelector

///     {

///         public override DataTemplate 

///             SelectTemplate(object item, DependencyObject container)

///         {

///             if (item != null && item is AuctionItem)

///             {

///                 AuctionItem auctionItem = item as AuctionItem;

///                 Window window = Application.Current.MainWindow;

/// 

///                 switch (auctionItem.SpecialFeatures)

///                 {

///                     case SpecialFeatures.None:

///                     return window.FindResource("AuctionItem_None") as DataTemplate;

///                     case SpecialFeatures.Color:

///                     return window.FindResource("AuctionItem_Color") as DataTemplate;

///                 }

///             }

/// 

///             return null;

///         }

///     }

/// }



