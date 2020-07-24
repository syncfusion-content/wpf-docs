---
layout: post
title: RibbonTextBox for Syncfusion's Ribbon control for WPF
description: This section briefly describes the functionalities of RibbonTextBox for Syncfusion's Ribbon control for WPF
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonTextBox in WPF Ribbon

`RibbonTextBox` control provide similar set of functionalities like normal TextBox control in Ribbon Instance. 

## Add TextBox to the RibbonBar

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">
<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="_ribbonBar2" Header="RibbonBar1">
<syncfusion:RibbonButton   Label="Cut"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar  Name="_ribbonBar2" Width="150" Header="RibbonBar2">
<syncfusion:RibbonTextBox  Width="140" Text="RibbonTextBox"></syncfusion:RibbonTextBox>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of RibbonTextBox and add it to RibbonBar through code behind.

{% tabs %}

{% highlight C# %}

RibbonTextBox _ribbonTextBox = new RibbonTextBox(){Text = "RibbonTextBox"};
_ribbonBar2.Items.Add(_ribbonTextBox);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonTextBox As New RibbonTextBox() With {.Text = "RibbonTextBox"}
_ribbonBar2.Items.Add(_ribbonTextBox)

{% endhighlight %}
 
{% endtabs %}

![Adding text box to the ribbon](RibbonTextBox_images/RibbonTextBox_img1.jpg)

## Add TextBox to the simplified layout

When the simplified layout is enabled, the RibbonTextBox can be added and displayed in a single line as shown below. To know more about the simplified layout, refer [here](https://help.syncfusion.com/wpf/ribbon/simplifiedlayout).

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow x:Class="RibbonButton_IconTemp.Window1"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:RibbonButton_IconTemp" xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        skin:SfSkinManager.VisualStyle="MaterialLight"
        Title="Untitled 1 - Ribbon Control" Height="450" Width="800">
    <Grid x:Name="grid">
        <syncfusion:Ribbon VerticalAlignment="Top" EnableSimplifiedLayoutMode="True" LayoutMode="Simplified">
            <syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
                <syncfusion:RibbonBar Header="Font">
                    <syncfusion:RibbonTextBox  Width="140" Text="RibbonTextBox"></syncfusion:RibbonTextBox>
                </syncfusion:RibbonBar>
            </syncfusion:RibbonTab>
        </syncfusion:Ribbon>
    </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% highlight C# %}

Ribbon ribbon = new Ribbon();
ribbon.VerticalAlignment = VerticalAlignment.Top;
ribbon.EnableSimplifiedLayoutMode = true;
ribbon.LayoutMode = LayoutMode.Simplified;
// Creating new tabs
RibbonTab homeTab = new RibbonTab();
homeTab.Caption = "Home";
homeTab.IsChecked = true;

// Creating new bar
RibbonBar fontBar = new RibbonBar();
fontBar.Header = "Font";

// Creating items
RibbonTextBox ribbonTextBox = new RibbonTextBox() { Text = "RibbonTextBox" };

// Adding items to bar
fontBar.Items.Add(ribbonTextBox);

// Adding bars to the tabs
homeTab.Items.Add(fontBar);

// Adding tabs to ribbon
ribbon.Items.Add(homeTab);
grid.Children.Add(ribbon);
SfSkinManager.SetVisualStyle(this, VisualStyles.MaterialLight);

{% endhighlight %}

{% endtabs %}

![RibbonTextBox during simplified layout](RibbonTextBox_images/RibbonTextBox_Simplified.png)

When arranging in simplified layout alone, the **Margin**, **Width** and **Height** values of the RibbonTextBox can be ignored as it will be resized automatically to the standard width and height. If the RibbonTextBox is to be shown in both normal and simplified layout, the **Margin**, **Width** and **Height** properties can be set for normal layout alone using triggers.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonTextBox Text="Enter text" syncfusion:SimplifiedLayoutSettings.DisplayMode="Normal,Simplified" >
    <syncfusion:RibbonTextBox.Style>
        <Style TargetType="syncfusion:RibbonTextBox" BasedOn="{StaticResource SyncfusionRibbonTextBoxStyle}">
            <Style.Triggers>
                <Trigger Property="syncfusion:SimplifiedLayoutSettings.LayoutMode" Value="Normal">
                    <Setter Property="Height" Value="25"/>
                    <Setter Property="Width" Value="48"/>
                    <Setter Property="Margin" Value="2"/>
                </Trigger>
            </Style.Triggers>
        </Style>
    </syncfusion:RibbonTextBox.Style>
</syncfusion:RibbonTextBox >

{% endhighlight %}

{% endtabs %}

