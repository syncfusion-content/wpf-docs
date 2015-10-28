---
layout: post
title: Adding custom RibbonTab and RibbonBar
description: Adding custom RibbonTab and RibbonBar
platform: wpf
control: Ribbon
documentation: ug
---
## Add custom RibbonTab and RibbonBar

The following section illustrates how to customize Ribbon at the run time

### QAT Customized Window

This topic illustrates in detail about the [QAT](#_Adding_items_from_1 "") topic.

First, select MoreCommands option from the QAT to open the QAT Customized Window.

QAT can be Customized further by using the following options

1. Add

	In the QAT Customized window, the list of Commands is available. The Commands can be filtered only from the Particluar tab by using **Choose** **commands** **from** option. Then, select the commands to be added to the QAT and add the command to Right Pane of the QAT Dialog by clicking **Add** Button. Finally, Click Ok. Now, the selected command gets added in the QAT.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img1.jpeg)

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img2.jpeg)

2. Remove

	QAT items can be removed at the Run time. In the QAT Customize window, select the Command to be deleted from the QAT Dialog,and then click Remove Button. In the following screenshot, Redo command gets deleted and the output is changed according to it.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img3.jpeg)

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img4.jpeg)

3. Reset

	To restore the QAT to its default content, use this **Reset** option.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb81ba81.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img5.jpeg)

4. Reorder

	QAT also supports to reorder the items by clicking the Up and down arrow at the left of the QAT Dialog. 

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img6.jpeg)

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img7.jpeg)


### Customize Ribbon with RibbonTab and RibbonBar

QAT can also support to customize Ribbon Tab and RibbonBar while running. To customize the **Ribbon**, enable the **ShowCustomizeRibbon** property of the Ribbon to **true** and follow the steps. 

1. Click the Quick Access Toolbar drop-down button and click the **MoreCommands** menu.

2. Then, select the **Customize** **Ribbon** options from the left-side column.

3. You can add **Ribbontab** and **Ribbonbar** by selecting New Tab and New Group Options Respectively.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img8.jpeg)

4. To **move** the tab up and down, select the tab to be moved and click the button at the right-side corner accordingly. Similarly, the group can be moved within the tab.

5. By using the **Rename** option, rename any particular Tab/Group present in the **Ribbon** by selecting it.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb9b87bb.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img9.jpeg)

6. The **visibility** of any particular Tab can be changed by enabling the checkbox of the corresponding selection.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img10.jpeg)

7. By using **Delete** option, the Custom RibbonBar and RibbonTab can be deleted. But, this option does not work in the case of original content.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb9c3957.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img11.jpeg)

8. To delete all the Ribbon Customization, use **Reset** **All** **Customization** from the Reset Drop Down Menu.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb9d29e2.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img12.jpeg)

After customizing the RibbonTab and RibbonBar, RibbonItems can be customized. Customizing Ribbon Item concepts are explained as follows.

### Add items to the customized RibbonTab

The steps to customize the Ribbon Item are as follows

1. The **Choose** **commands** **From** drop-down list is used to filter the commands only from the Particular Tab.

2.  To add the item under the right-side column of a newly added **Ribbonbar** and **Ribbontab**, select the item from left-side column and click the **Add** button.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLba692c1.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img13.jpeg)

3. Also, the Ribbon Item from the RibbonBar can be removed that is added recently by using **Remove** **option**

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLbb23805.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img14.jpeg)

4. The order of the RibbonItem within the RibbonBar can be changed by using **Up** **and** **Down** **arrow**

5. By using the Rename option,the RibbonIrem can be renamed

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLbb2d36a.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img15.jpeg)

6. Click **OK** button. The Changes are reflected in the output window.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img16.jpeg)


### How to disable the customization in Ribbon?

To disable the customization in the Ribbon, set **ShowCustomizeRibbon** property of the Ribbon as "**False**" 

To disable the customization in the Ribbon, set **ShowCustomizeRibbon** property of the Ribbon as "**False**" 

{% highlight xml %}

[XAML]

<syncfusion:Ribbon  VerticalAlignment="Top" x:Name="Ribbon" ShowCustomizeRibbon="False">

<syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:QuickAccessToolBar >



<syncfusion:RibbonButton Label="Undo" SmallIcon="/Resources/Undo16.png" SizeForm="ExtraSmall"   

ToolTip="Undo" syncfusion:RibbonCommandManager.SynchronizedItem="Undo" />

<syncfusion:RibbonButton Label="Redo" SmallIcon="/Resources/Redo16.png" SizeForm="ExtraSmall"

ToolTip="Redo" syncfusion:RibbonCommandManager.SynchronizedItem="Redo"/>



</syncfusion:QuickAccessToolBar>

</syncfusion:Ribbon.QuickAccessToolBar>



<syncfusion:RibbonTab  Caption="HOME" >

<syncfusion:RibbonBar  Header="Respond">

<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>

<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>

<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>

<syncfusion:RibbonButton   Label="Paste" SizeForm="Large" SmallIcon="/Resources/Paste32.png" syncfusion:RibbonCommandManager.SynchronizedItem="Paste" />

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="SEND/RECIEVE"/>

</syncfusion:Ribbon>



In the following screenshot, customizing Ribbon is disabled and it shows only the QAT Customize window

In the following screenshot, customizing Ribbon is disabled and it shows only the QAT Customize window


![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img17.jpeg)

