---
layout: post
title: Data-Binding
description: data binding
platform: wpf
control: TreeViewAdv
documentation: ug
---

# Data Binding

This section illustrates how to bind a custom object to the TreeViewAdv Control through Data Context property.

## Binding Custom Object to TreeView Control

You can bind the custom object to the DataContext property of the control, and their corresponding elements to the children of the TreeViewAdv control. When a DataContext is set to a window or to a TreeViewAdv, it gets inherited to all its logical children. The OnInitialized method is used to get the DataContext. As you use DataContext in the template with DataTriggers, you should set that property to active host tab or null.



[XAML]



<Window x:Class="WpfApplication2.Window1"

    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

    xmlns:local="clr-namespace:WpfApplication2"

    Title="Window1" Height="300" Width="300">

  &lt;Window.Resources&gt;



    &lt;!--Custom object which is defined in the code behind can be accessed through the key logic in XAML--&gt;

    &lt;local:TreeViewHeader x:Key="treeViewHeader"/&gt;

  &lt;/Window.Resources&gt;

  &lt;Grid&gt;



    &lt;!-- Adding TreeViewAdv with CustomEditedItemTemplate --&gt;

    &lt;syncfusion:TreeViewAdv Name="treeViewAdv" DataContext="{Binding treeViewHeader}"&gt;



     &lt;!-- Adding TreeViewItemAdv --&gt;

      &lt;syncfusion:TreeViewItemAdv Name="treeViewItemAdv1" Header="Marital Status"&gt;

        &lt;syncfusion:TreeViewItemAdv Header="{Binding Header1}"/&gt;

        &lt;syncfusion:TreeViewItemAdv Header="{Binding Header2}"/&gt;

      &lt;/syncfusion:TreeViewItemAdv&gt;

    &lt;/syncfusion:TreeViewAdv&gt;

  &lt;/Grid&gt;

&lt;/Window&gt;





[C#]



/// &lt;summary&gt;

/// Interaction logic for the class TreeViewHeader

/// &lt;/summary&gt;

public class TreeViewHeader

{

    /// &lt;summary&gt;

    /// Initializes a new instance of the &lt;see cref="TreeViewHeader"/&gt; class.

    /// &lt;/summary&gt;

    public TreeViewHeader()

    {

        this.Header1 = "Single";

        this.Header2 = "Married";

    }



    /// &lt;summary&gt;

    /// Gets or sets the header1.

    /// &lt;/summary&gt;

    /// <value>The header1.&lt;/value&gt;

    public string Header1

    {

        get;

        set;

    }



    /// &lt;summary&gt;

    /// Gets or sets the header2.

    /// &lt;/summary&gt;

    /// <value>The header2.&lt;/value&gt;

    public string Header2

    {

        get;

        set;

    }

}





{ ![](Data-Binding_images/Data-Binding_img1.jpeg) | markdownify }
{:.image }






