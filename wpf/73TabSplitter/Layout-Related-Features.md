---
layout: post
title: Layout-Related-Features
description: layout related features
platform: wpf
control: TabSplitter
documentation: ug
---

# Layout Related Features

This section illustrates the following Layout-related feature of TabSplitter control.

## Customizing the Appearance of TabSplitter

The appearance of the TabSplitter control is customized by using the appearance properties available in the control. You can set the color for the MouseOver Background, MouseOver Foreground, Selected Foreground and Selected Background of the TabSplitter control. Here is the code snippet.



[XAML]



&lt;!-- Adding TabSplitter With Selected Brush --&gt;

&lt;syncfusion:TabSplitter Name="tabsplitter" MouseOverBackground="Green" MouseOverForeground="Yellow" SelectedBackground="Red" SelectedForeground="YellowGreen"&gt;



    &lt;!-- Adding TabSplitterItem --&gt;

    &lt;syncfusion:TabSplitterItem Header="Window1.xaml"  Name="tabSplitterItem1"&gt;



        &lt;!-- Adding TopPanelItems --&gt;

        &lt;syncfusion:TabSplitterItem.TopPanelItems&gt; 

            &lt;!-- Adding SplitterPage --&gt;

            &lt;syncfusion:SplitterPage Name="splitterPage1" Header="XAML"&gt;

            &lt;/syncfusion:SplitterPage&gt;

        &lt;/syncfusion:TabSplitterItem.TopPanelItems&gt;



        &lt;!-- Adding BottomPanelItems --&gt;

        &lt;syncfusion:TabSplitterItem.BottomPanelItems&gt; 

            &lt;!-- Adding SplitterPage --&gt;

            &lt;syncfusion:SplitterPage Name="splitterPage2" Header="Design"&gt;

            &lt;/syncfusion:SplitterPage&gt;

        &lt;/syncfusion:TabSplitterItem.BottomPanelItems&gt;



    &lt;/syncfusion:TabSplitterItem&gt;



&lt;/syncfusion:TabSplitter&gt;



[C#]



// Set the selected background.

tabsplitter.SelectedBackground = Brushes.Red;



// Set the selected foreground.

tabsplitter.SelectedForeground = Brushes.YellowGreen;



// Set the MouseOverBackground.

tabsplitter.MouseOverBackground = Brushes.Green;



// Set the MouseOverForeground.

tabsplitter.MouseOverForeground = Brushes.Yellow;





{ ![](Layout-Related-Features_images/Layout-Related-Features_img1.png) | markdownify }
{:.image }






