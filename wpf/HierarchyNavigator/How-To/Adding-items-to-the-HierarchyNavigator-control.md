---
layout: post
title: Adding-items-to-the-HierarchyNavigator-control
description: adding items to the hierarchynavigator control
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

### Adding items to the HierarchyNavigator control

The steps to add items to the HierarchyNavigator control through code are as follows:

1. Create a new HierarchyNavigator instance.
2. Specify the item name in the Content property for each item in the hierarchical structure.



C#



HierarchyNavigator hierarchyNavigator1 = new HierarchyNavigator() { Height = 30 };



HierarchyNavigatorItem hierarchyNavigatorItem1 = new HierarchyNavigatorItem();

hierarchyNavigatorItem1.Content = "Syncfusion";



HierarchyNavigatorItem hierarchyNavigatorItem11 = new HierarchyNavigatorItem();

hierarchyNavigatorItem11.Content = "User Interface";



HierarchyNavigatorItem hierarchyNavigatorItem111 = new HierarchyNavigatorItem();

hierarchyNavigatorItem111.Content = "Silverlight";

HierarchyNavigatorItem hierarchyNavigatorItem112 = new HierarchyNavigatorItem();

hierarchyNavigatorItem112.Content = "WPF";

HierarchyNavigatorItem hierarchyNavigatorItem113 = new HierarchyNavigatorItem();

hierarchyNavigatorItem113.Content = "ASP .Net";

HierarchyNavigatorItem hierarchyNavigatorItem114 = new HierarchyNavigatorItem();

hierarchyNavigatorItem114.Content = "MVC";



hierarchyNavigatorItem11.Items.Add(hierarchyNavigatorItem111);

hierarchyNavigatorItem11.Items.Add(hierarchyNavigatorItem112);

hierarchyNavigatorItem11.Items.Add(hierarchyNavigatorItem113);

hierarchyNavigatorItem11.Items.Add(hierarchyNavigatorItem114);



hierarchyNavigatorItem1.Items.Add(hierarchyNavigatorItem11);



hierarchyNavigator1.Items.Add(hierarchyNavigatorItem1);



Or

XAML



&lt;syncfusion:HierarchyNavigator x:Name="hierarchyNavigatorcontrol1"     VerticalAlignment="Top" Height="30" Width="600"&gt;

    &lt;syncfusion:HierarchyNavigator.Items&gt;

        &lt;syncfusion:HierarchyNavigatorItem Content="Syncfusion"&gt;

            &lt;syncfusion:HierarchyNavigatorItem.Items&gt;

                &lt;syncfusion:HierarchyNavigatorItem Content="User Interface"/&gt;

                &lt;syncfusion:HierarchyNavigatorItem Content="Silverlight"&gt;

                    &lt;syncfusion:HierarchyNavigatorItem.Items&gt;

                        &lt;syncfusion:HierarchyNavigatorItem Content="Tools"/&gt;

                    &lt;/syncfusion:HierarchyNavigatorItem.Items&gt;

                &lt;/syncfusion:HierarchyNavigatorItem&gt;

            &lt;/syncfusion:HierarchyNavigatorItem.Items&gt;

        &lt;/syncfusion:HierarchyNavigatorItem&gt;

    &lt;/syncfusion:HierarchyNavigator.Items&gt;

&lt;/syncfusion:HierarchyNavigator&gt;



