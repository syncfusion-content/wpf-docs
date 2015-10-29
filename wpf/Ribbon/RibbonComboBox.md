---
layout: post
title: RibbonComboBox
description: RibbonComboBox
platform: wpf
control: Ribbon
documentation: ug
---
## RibbonComboBox

**RibbonComboBox** control is used to display the list of items, as drop-down menu in **Ribbon** instance **RibbonComboBox** accepts any number of items to the **RibbonComboBox**.

### Creating control in XAML

You can use RibbonComboBox in Ribbon by add it inside the RibbonBar element.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_RibbonTab1" Caption="HOME"  >

<syncfusion:RibbonBar Name="_RibbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

<syncfusion:RibbonButton   Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Name="_RibbonBar2" Width="150" Header="RibbonBar2">     

<WrapPanel>

<syncfusion:RibbonComboBox SelectedItem="Arial" Width="80">

<ComboBoxItem>Arial</ComboBoxItem>

<ComboBoxItem>Tahoma</ComboBoxItem>

<ComboBoxItem>Calibri</ComboBoxItem>

</syncfusion:RibbonComboBox>

<syncfusion:RibbonComboBox SelectedItem="12" Width="50">

<ComboBoxItem>11</ComboBoxItem>

<ComboBoxItem>12</ComboBoxItem>

<ComboBoxItem>13</ComboBoxItem>

</syncfusion:RibbonComboBox>

</WrapPanel>

</syncfusion:RibbonBar>         

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>

</syncfusion:Ribbon>



{% endhighlight %}

### Creating control in code behind			

Create instance of **RibbonComboBox** and add it to **RibbonBar** Items.

{% highlight c# %}

[C#]

WrapPanel _WrapPanel = new WrapPanel();

RibbonComboBox _RibbonComboBox = new RibbonComboBox() { Width=80};

RibbonComboBox _RibbonComboBox1 = new RibbonComboBox() { Width=50};

RibbonComboBoxItem ComboItem1 = new RibbonComboBoxItem() { Content = "Arial" };

RibbonComboBoxItem ComboItem2 = new RibbonComboBoxItem() { Content = "Calibri" };

RibbonComboBoxItem ComboItem3 = new RibbonComboBoxItem() { Content = "Tahoma" };

RibbonComboBoxItem ComboItem4 = new RibbonComboBoxItem() { Content = "11" };

RibbonComboBoxItem ComboItem5 = new RibbonComboBoxItem() { Content = "12" };

RibbonComboBoxItem ComboItem6 = new RibbonComboBoxItem() { Content = "13" };     

_RibbonComboBox.Items.Add(ComboItem1);

_RibbonComboBox.Items.Add(ComboItem2);

_RibbonComboBox.Items.Add(ComboItem3);

_RibbonComboBox1.Items.Add(ComboItem4);

_RibbonComboBox1.Items.Add(ComboItem5);

_RibbonComboBox1.Items.Add(ComboItem6);

_WrapPanel.Children.Add(_RibbonComboBox);

_WrapPanel.Children.Add(_RibbonComboBox1);

_RibbonBar2.Items.Add(_WrapPanel);



{% endhighlight %}

![](RibbonComboBox_images/RibbonComboBox_img1.jpeg)


