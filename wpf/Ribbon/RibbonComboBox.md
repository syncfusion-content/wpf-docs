---
layout: post
title: RibbonComboBox
description: RibbonComboBox
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonComboBox

RibbonComboBox control is used to display the list of items, as ComboBox in Ribbon instance.

## Creating control in XAML

You can use RibbonComboBox in Ribbon by adding it directly to RibbonBar element.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME" IsChecked="True">

<syncfusion:RibbonBar Name="_ribbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton Label="Cut"/>

<syncfusion:RibbonButton Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Name="_ribbonBar2" Width="150" Header="RibbonBar2">     

<ButtonPanel>

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

</ButtonPanel>

</syncfusion:RibbonBar>         

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>

</syncfusion:Ribbon>



{% endhighlight %}

## Creating control in code behind			

Create instance of RibbonComboBox and add it to RibbonBar Items.

{% highlight c# %}

[C#]

ButtonPanel _buttonPanel = new ButtonPanel();

RibbonComboBox _ribbonComboBox1 = new RibbonComboBox() { Width=80};

RibbonComboBox _ribbonComboBox2 = new RibbonComboBox() { Width=50};

RibbonComboBoxItem comboBoxItem1 = new RibbonComboBoxItem() { Content = "Arial" };

RibbonComboBoxItem comboBoxItem2 = new RibbonComboBoxItem() { Content = "Calibri" };

RibbonComboBoxItem comboBoxItem3 = new RibbonComboBoxItem() { Content = "Tahoma" };

RibbonComboBoxItem comboBoxItem4 = new RibbonComboBoxItem() { Content = "11" };

RibbonComboBoxItem comboBoxItem5 = new RibbonComboBoxItem() { Content = "12" };

RibbonComboBoxItem comboBoxItem6 = new RibbonComboBoxItem() { Content = "13" };     

_ribbonComboBox.Items.Add(comboBoxItem1);

_ribbonComboBox.Items.Add(comboBoxItem2);

_ribbonComboBox.Items.Add(comboBoxItem3);

_RibbonComboBox1.Items.Add(comboBoxItem4);

_ribbonComboBox1.Items.Add(comboBoxItem5);

_ribbonComboBox1.Items.Add(comboBoxItem6);

_buttonPanel.Children.Add(_ribbonComboBox1);

_buttonPanel.Children.Add(_ribbonComboBox2);

_ribbonBar2.Items.Add(_buttonPanel);



{% endhighlight %}

![](RibbonComboBox_images/RibbonComboBox_img1.jpeg)


