---
layout: post
title: Appearance | CheckListBox | wpf | Syncfusion
description: This section describes about various themes and item customization that are available in CheckListBox control.
platform: wpf
control: CheckListBox
documentation: ug
---

# Appearance

## Item Template

The Item template is used set DataTemplate which is used to display each item.

{% tabs %}
{% highlight XAML %}

<syncfusion:CheckListBox  Grid.Row="1" 
            IsSelectAllEnabled="True" 
            Width="200" Height="180"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            x:Name="ListBox" ItemsSource="{Binding Country}"/>

<syncfusion:CheckListBox.ItemTemplate>
    <DataTemplate>
        <StackPanel Orientation="Horizontal">
            <Image Source="{Binding Image}" Width="20" Height="20"></Image>
            <TextBlock Text="{Binding Name}" Margin="5"></TextBlock>
        </StackPanel>
    </DataTemplate>
</syncfusion:CheckListBox.ItemTemplate>

</syncfusion:CheckListBox>

{% endhighlight %}
{% endtabs %}

![ItemTemplate](Appearance_images/style.png)

## GroupTemplate

The GroupTemplate is used to set DataTemplate for the group header.

{% tabs %}
{% highlight XAML %}

<syncfusion:CheckListBox 
            Grid.Row="1"
            DisplayMemberPath="Name"
            Width="300" Height="400"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            Margin="10" 
            ItemsSource="{Binding Vegetables}"/>

<syncfusion:CheckListBox.GroupTemplate>
    <DataTemplate>
        <TextBlock Text="{Binding Name}" FontWeight="Bold">
        </TextBlock>
    </DataTemplate>
</syncfusion:CheckListBox.GroupTemplate>

</syncfusion:CheckListBox>

{% endhighlight %}
{% endtabs %}

![GroupTemplate](Appearance_images/group_template.png)

## SelectAllTemplate

The SelectAllTemplate is used to set DataTemplate for the SelectAll item.

{% tabs %}
{% highlight XAML %}

<syncfusion:CheckListBox 
            Grid.Row="1"
            DisplayMemberPath="Name"
            Width="300" Height="400"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            Margin="10" 
            ItemsSource="{Binding Vegetables}"/>

<syncfusion:CheckListBox.SelectAllTemplate>
    <DataTemplate>
        <TextBlock Text="Select All" FontStyle="Italic"></TextBlock>
    </DataTemplate>
</syncfusion:CheckListBox.SelectAllTemplate>

{% endhighlight %}
{% endtabs %}

![SelectAllTemplate](Appearance_images/select_all.png)

{% endhighlight %}
{% endtabs %}

## ItemContainerStyle

The ItemContainerStyle is the style that is applied to the container element generated for each item. Its default value is null.

{% tabs %}
{% highlight XAML %}

<Window.Resources>
        <Style TargetType="syncfusion:CheckListBoxItem" x:Key="ItemStyle">
            <Style.Triggers>
                <Trigger Property="IsSelected" Value="True">
                    <Setter Property="FontWeight" Value="Bold"></Setter>
                </Trigger>
            </Style.Triggers>
        </Style>
</Window.Resources>

<syncfusion:CheckListBox 
            Grid.Row="1"
            Width="300" 
            Height="400"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            Margin="10" 
            ItemsSource="{Binding Vegetables}" 
            ItemContainerStyle="{StaticResource ItemStyle}"
            x:Name="ListBox"/>

{% endhighlight %}
{% endtabs %}

![ItemContainerStyle](Appearance_images/ItemContainerStyle.png)

## ItemTemplateSelector

The ItemTemplateSelector is used to return a DataTemplate based on the provided logic.

{% tabs %}
{% highlight XAML %}

<Window.Resources>
       <local:MyTemplateSelector x:Key="Mytemplate">
            <local:MyTemplateSelector.groupTemplate>
                <DataTemplate>
                    <TextBlock Text="{Binding Name}"></TextBlock>
                </DataTemplate>
            </local:MyTemplateSelector.groupTemplate>
            <local:MyTemplateSelector.itemTemplate>
                <DataTemplate>
                    <TextBlock Text="{Binding Name}" FontStyle="Italic"></TextBlock>
                </DataTemplate>
            </local:MyTemplateSelector.itemTemplate>
        </local:MyTemplateSelector>
</Window.Resources>

{% endhighlight %}

{% highlight C# %}

public class MyTemplateSelector : DataTemplateSelector
{
    public DataTemplate Template { get; set; }
    public DataTemplate itemTemplate { get; set; }

    public override DataTemplate SelectTemplate(object item, DependencyObject container)
    {
        if (item is Vegetable && (item as Vegetable).Category== "Leafy and Salad")
            return itemTemplate;
        else
            return Template;
    }

}

{% endhighlight %}
{% endtabs %}  

![ItemTemplateSelector](Appearance_images/ItemTemplateSelector.png)

## ItemContainerStyleSelection

The ItemContainerStyleSelector is used to choose the style to use as ItemContainerStyle based on the provided logic.

{% tabs %}
{% highlight XAML %}

<Style TargetType="syncfusion:CheckListBoxItem" x:Key="Groupstyle">
   <Setter Property="Foreground" Value="Red"></Setter>
</Style>
<Style TargetType="syncfusion:CheckListBoxItem" x:Key="ItemStyle">
    <Setter Property="Foreground" Value="Blue"></Setter>
</Style>
<local:VegetableStyleSelector x:Key="StyleSelector" GroupStyle="{StaticResource Groupstyle}" ItemStyle="{StaticResource ItemStyle}">
</local:VegetableStyleSelector>

<syncfusion:CheckListBox 
            Grid.Row="1"
            DisplayMemberPath="Name"
            Width="300" Height="400"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            Margin="10" 
            ItemsSource="{Binding Vegetables}" 
            ItemContainerStyleSelector="{StaticResource StyleSelector}"/>

{% endhighlight %}

{% highlight C# %}
    public class VegetableStyleSelector : StyleSelector
    {
        private Style groupStyle;
        private Style itemStyle;
        public override Style SelectStyle(object item, DependencyObject container)
        {
            if (item is Vegetable)
                return ItemStyle;
            else
                return GroupStyle;
        }

        public Style GroupStyle
        {
            get
            {
                return groupStyle;
            }
            set
            {
                groupStyle = value;
            }
        }

        public Style ItemStyle
        {
            get
            {
                return itemStyle;
            }
            set
            {
                itemStyle = value;
            }
        }
    }

{% endhighlight %}
{% endtabs %}

![ItemContainerStyleSelection](Appearance_images/ItemContainerStyleSelection.png)

## Right to Left

The CheckListBox controls provides RTL support for users working in languages such as Hebrew, Arabic, or Persian. This support aligns the control in right-to-left direction.

{% tabs %}
{% highlight XAML %}

<syncfusion:CheckListBox  Grid.Row="1" 
            IsSelectAllEnabled="True" 
            Width="200" Height="180"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            x:Name="ListBox" FlowDirection="RightToLeft">
           
</syncfusion:CheckListBox>

{% endhighlight %}
{% endtabs %}

![RTL](Appearance_images/rtl.png)


## Set VisualStyle for CheckListBox

The appearance of the CheckListBox control is customized by applying a suitable style using the VisualStyle property.

Property table

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the CheckListBox control. The options provided are as follows.
<ul>
<li>BlendOffice2003</li>
<li>Office2007Blue</li>
<li>Office2007Black</li>
<li>Office2007Silver</li>
<li>ShinyBlue</li>
<li>ShinyRed</li>
<li>SyncOrange</li>
<li>VS2010</li>
<li>Metro</li>
<li>Transparent</li>
</ul>
</td></tr>
</table>

For setting Blend style, refer the below code snippet.

{% tabs %}
{%highlight xaml%}

<!-- Adding CheckListBox with Visual Style as Blend -->
<syncfusion:CheckListBox 
            Grid.Row="1"
            DisplayMemberPath="Name"
            Width="300" Height="400"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            Margin="10" 
            ItemsSource="{Binding Vegetables}"
            syncfusion:SkinStorage.VisualStyle="Blend">
 
{%endhighlight%}

{%highlight c#%}

// Setting the visual style as Blend.
SkinStorage.SetVisualStyle(checkListBox, "Blend"); 

{%endhighlight%}
{% endtabs %}

![Blend visual style](Appearance_images/blend.png)

CheckListBox with "Blend" Visual Style

![Default visual style](Appearance_images/default.png)

CheckListBox with "Default" Visual Style
{:.caption}

![Office2007Black visual style](Appearance_images/Office2007_Black.png)

CheckListBox with "Office2007Black" Visual Style
{:.caption}

![Office2003 visual style](Appearance_images/Office2003.png)

CheckListBox with "Office2003" Visual Style
{:.caption}

![Metro visual style](Appearance_images/Metro.png)

CheckListBox with "Metro" Visual Style
{:.caption}

![Transparent visual style](Appearance_images/Transparent.png)

CheckListBox with "Transparent" Visual Style
{:.caption}



