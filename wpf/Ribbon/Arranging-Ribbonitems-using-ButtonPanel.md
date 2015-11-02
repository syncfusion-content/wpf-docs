---
layout: post
title: Arranging Ribbon items using ButtonPanel
description: Arranging Ribbon items using ButtonPanel
platform: wpf
control: Ribbon
documentation: ug
---
## Arranging Ribbon items using ButtonPanel

Button Panel represents a panel control that can display horizontal row of Ribbon Items in a single border.It is used to manage the place for the controls.

### Adding items to ButtonPanel in XAML

Use the below code to create ButtonPanel in XAML

{% highlight xml %}

[XAML]

<syncfusion:Ribbon VerticalAlignment="Top" x:Name="Ribbon">  

<syncfusion:RibbonTab Caption="RIBBON CONTROLS" >

<syncfusion:RibbonBar Header="Drop Split Buttons">

<syncfusion:ButtonPanel>

<syncfusion:DropDownButton Label=" Drop "

SizeForm="Small"

SmallIcon="Images/Gray.png" />

<syncfusion:SplitButton Label=" Split "

SizeForm="Small"

SmallIcon="Images/Yellow.png" />

</syncfusion:ButtonPanel  >

<syncfusion:ButtonPanel SeparatorVisibility="Collapsed">

<syncfusion:RibbonButton Label="Simple"

SizeForm="ExtraSmall"

SmallIcon="Images/Gray.png" />

<syncfusion:RibbonButton IsToggle="True"

Label="Toggle"

SizeForm="ExtraSmall"

SmallIcon="Images/Red.png" />

<syncfusion:RibbonButton Label="Simple"

SizeForm="ExtraSmall"

SmallIcon="Images/Yellow.png" />

<syncfusion:RibbonButton IsToggle="True"

Label="Toggle"

SizeForm="ExtraSmall"

SmallIcon="Images/Blue.png" />

<syncfusion:RibbonButton IsToggle="True"

Label="Toggle"

SizeForm="ExtraSmall"

SmallIcon="Images/Orange.png" />

</syncfusion:ButtonPanel>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>



{% endhighlight %}

![](ArrangingRibbonitemsusingButtonPanel_images/ArrangingRibbonitemsusingButtonPanel_img1.jpeg)


### Adding items to ButtonPanel in code behind



To create the ButtonPanel control in Code Behind, use the below code.

{% highlight c# %}

[C#]

DropDownButton DropDownButton = new DropDownButton() { Label = "Drop", SizeForm = Syncfusion.Windows.Tools.SizeForm.Small, SmallIcon = new BitmapImage(new Uri("/Resources/Gray.png", UriKind.Relative)) };

SplitButton SplitButton = new SplitButton() { Label = "Split", SizeForm = Syncfusion.Windows.Tools.SizeForm.Small, SmallIcon = new BitmapImage(new Uri("/Resources/Yellow.png", UriKind.Relative)) };

ButtonPanel ButtonPanel=new ButtonPanel();

ButtonPanel.Items.Add(DropDownButton);

ButtonPanel.Items.Add(SplitButton);



{% endhighlight %}

![](ArrangingRibbonitemsusingButtonPanel_images/ArrangingRibbonitemsusingButtonPanel_img2.jpeg)


