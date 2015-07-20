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

  <Window.Resources>



    <!--Custom object which is defined in the code behind can be accessed through the key logic in XAML-->

    <local:TreeViewHeader x:Key="treeViewHeader"/>

  </Window.Resources>

  <Grid>



    <!-- Adding TreeViewAdv with CustomEditedItemTemplate -->

    <syncfusion:TreeViewAdv Name="treeViewAdv" DataContext="{Binding treeViewHeader}">



     <!-- Adding TreeViewItemAdv -->

      <syncfusion:TreeViewItemAdv Name="treeViewItemAdv1" Header="Marital Status">

        <syncfusion:TreeViewItemAdv Header="{Binding Header1}"/>

        <syncfusion:TreeViewItemAdv Header="{Binding Header2}"/>

      </syncfusion:TreeViewItemAdv>

    </syncfusion:TreeViewAdv>

  </Grid>

</Window>





[C#]



/// <summary>

/// Interaction logic for the class TreeViewHeader

/// </summary>

public class TreeViewHeader

{

    /// <summary>

    /// Initializes a new instance of the <see cref="TreeViewHeader"/> class.

    /// </summary>

    public TreeViewHeader()

    {

        this.Header1 = "Single";

        this.Header2 = "Married";

    }



    /// <summary>

    /// Gets or sets the header1.

    /// </summary>

    /// <value>The header1.</value>

    public string Header1

    {

        get;

        set;

    }



    /// <summary>

    /// Gets or sets the header2.

    /// </summary>

    /// <value>The header2.</value>

    public string Header2

    {

        get;

        set;

    }

}





{{ '![](Data-Binding_images/Data-Binding_img1.jpeg)' | markdownify }}
{:.image }






