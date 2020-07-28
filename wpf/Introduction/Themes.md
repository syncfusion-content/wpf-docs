---
layout: post
title: Themes overview with SkinManager
description: Learn here about the themes overview and how to apply the themes for Syncfusion Essential WPF controls using SfSkinManager
platform: wpf
control: Introduction
documentation: ug
---

# Themes overview with SkinManager

Syncfusion offers enhanced theme support through SkinManager.

The [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.SfSkinManager.html) framework provides a convenient way to give the appealing appearance to both WPF syncfusion and framework controls.

## Built-in Themes

The built-in themes can applied to both syncfusion controls and framework controls by using [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.SfSkinManager~VisualStyleProperty.html) attached property of the [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.SfSkinManager.html). 

There are 22 built-in themes that can be applied using `SfSkinManager` for rich user interface experience. Some of the built-in themes can be color customized in the [ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio). 

N> For detailed information on supported themes and SkinManager, refer to this [topic](https://help.syncfusion.com/wpf/themes/skin-manager).

## Setting visual style in XAML

The following code example explains how to set the [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.SfSkinManager~VisualStyleProperty.html) property in XAML.

1. Import Syncfusion WPF schema `http://schemas.syncfusion.com/wpf` or the assembly namespace `Syncfusion.SfSkinManager` in XAML page.

{% tabs %}

{% highlight XAML %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" />

{% endhighlight %}

{% endtabs %}

2. Set the `VisualStyle` property for the control as illustrated in the following code example. 
  
{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="DataGrid_Themes.MainWindow"
                             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                             xmlns:local="clr-namespace:DataGrid_Themes"
                             xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
							        xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
							        syncfusionskin:SfSkinManager.VisualStyle="MaterialDark"
                             Icon="App.ico"
                             Title="Getting Started"
                             WindowStartupLocation="CenterScreen">

    <syncfusion:ChromelessWindow.Resources>
        <local:ViewModel x:Key="viewmodel" />
        <local:SelectedImageConverter x:Key="selectedImageConverter"/>
        <local:StatusConverter        x:Key="statusConverter"/>
        <local:TrustImageConverter    x:Key="trustImageConverter"/>
        <Style TargetType="syncfusion:SfRatingItem">
            <Setter Property="Padding" Value="1" />
            <Setter Property="Height" Value="20" />
            <Setter Property="Width" Value="22" />
        </Style> 
        <Style TargetType="syncfusion:SfRating">
            <Setter Property="VerticalAlignment" Value="Center" />
            <Setter Property="HorizontalAlignment" Value="Center" />
        </Style>
    </syncfusion:ChromelessWindow.Resources>

    <Grid DataContext="{StaticResource viewmodel}">
        <syncfusion:SfDataGrid Name="sfgrid" Margin="5"
                                       AutoGenerateColumns="False"
                                       AllowDraggingColumns="True"
                                       AllowEditing="True"
                                       LiveDataUpdateMode="AllowDataShaping"
                                       AllowFiltering="True"
                                       HeaderRowHeight="26"
                                       SelectionMode="Extended"
                                       ColumnSizer="Auto"
                                       ItemsSource="{Binding EmployeeDetails}">
            <syncfusion:SfDataGrid.Columns>
                <syncfusion:GridCheckBoxSelectorColumn  MappingName="Selected" AllowFiltering="False" Width="30"
                                                                AllowSorting="False"   AllowCheckBoxOnHeader="True"/>
                <syncfusion:GridTemplateColumn  MappingName="EmployeeName" Padding="2"
                                                        HeaderText="Employee Name">
                    <syncfusion:GridTemplateColumn.CellTemplate>
                        <DataTemplate>
                            <Grid Margin="3">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition  Width="15"/>
                                    <ColumnDefinition/>
                                </Grid.ColumnDefinitions>
                                <Image Source="{Binding Gender,
                                                                Converter={StaticResource selectedImageConverter}}" 
                                               Height="15"      Width="15"       Grid.Column="0"/>
                                <TextBlock Text="{Binding EmployeeName}" Padding="4" 
                                                   VerticalAlignment="Center"    Grid.Column="1"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:GridTemplateColumn.CellTemplate>
                </syncfusion:GridTemplateColumn>
                <syncfusion:GridTextColumn  MappingName="Designation" HeaderText="Designation"/>
                <syncfusion:GridTextColumn  MappingName="Mail"        HeaderText="Mail"/>
                <syncfusion:GridTemplateColumn MappingName="Location" Width="100"
                                                       HeaderText="Location">
                    <syncfusion:GridTemplateColumn.CellTemplate>
                        <DataTemplate>
                            <Grid Margin="3">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition  Width="15"/>
                                    <ColumnDefinition/>
                                </Grid.ColumnDefinitions>
                                <Image Source="Images/location.png"   Height="15"
                                               Grid.Column="0"                Width="15"/>
                                <TextBlock Text="{Binding Location}"  Padding="4" 
                                                   VerticalAlignment="Center" Grid.Column="1"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:GridTemplateColumn.CellTemplate>
                </syncfusion:GridTemplateColumn>
                <syncfusion:GridTemplateColumn MappingName="Status" Width="90" HeaderText="Status">
                    <syncfusion:GridTemplateColumn.CellTemplate>
                        <DataTemplate>
                            <TextBlock  Foreground="{Binding Status,
                                                                     Converter={StaticResource statusConverter}}"
                                                Padding="3"          Text="{Binding Status}"/>
                        </DataTemplate>
                    </syncfusion:GridTemplateColumn.CellTemplate>
                    <syncfusion:GridTemplateColumn.EditTemplate>
                        <DataTemplate>
                            <syncfusion:ComboBoxAdv SelectedValue="{Binding Status}" ItemsSource="{Binding Status, Source={StaticResource viewmodel}}"/>
                        </DataTemplate>
                    </syncfusion:GridTemplateColumn.EditTemplate>
                </syncfusion:GridTemplateColumn>
                <syncfusion:GridTemplateColumn MappingName="Trustworthiness" HeaderText="Trust Worthiness">
                    <syncfusion:GridTemplateColumn.CellTemplate>
                        <DataTemplate>
                            <Grid Margin="3">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition  Width="15"/>
                                    <ColumnDefinition/>
                                </Grid.ColumnDefinitions>
                                <Image Source="{Binding Trustworthiness,
                                                                Converter={StaticResource trustImageConverter}}"
                                               Height="15"      Width="15"          Grid.Column="0"/>
                                <TextBlock Text="{Binding Trustworthiness}" Padding="4" 
                                                   VerticalAlignment="Center"       Grid.Column="1"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:GridTemplateColumn.CellTemplate>
                    <syncfusion:GridTemplateColumn.EditTemplate>
                        <DataTemplate>
                            <syncfusion:ComboBoxAdv SelectedValue="{Binding Trustworthiness}"  ItemsSource="{Binding Trustworthiness, Source={StaticResource viewmodel}}"/>
                        </DataTemplate>
                    </syncfusion:GridTemplateColumn.EditTemplate>
                </syncfusion:GridTemplateColumn>
                <syncfusion:GridTemplateColumn MappingName="Rating" Width="130">
                    <syncfusion:GridTemplateColumn.CellTemplate>
                        <DataTemplate>
                            <syncfusion:SfRating VerticalAlignment="Center" ItemsCount="5" ShowToolTip="False"
                                                         Value="{Binding Rating, Mode=TwoWay}"/>
                        </DataTemplate>
                    </syncfusion:GridTemplateColumn.CellTemplate>
                </syncfusion:GridTemplateColumn>
                <syncfusion:GridTextColumn  Width="90" DisplayBinding="{Binding Path=Salary,
                                                                             StringFormat='{}{0:C}'}"   
                                                    TextAlignment="Right"    HeaderText="Salary"/>
                <syncfusion:GridTextColumn MappingName="Address" HeaderText="Address"/>
                <syncfusion:GridPercentColumn HeaderText="Software Proficiency" AllowEditing="False"
                                                      MappingName="SoftwareProficiency">
                    <syncfusion:GridPercentColumn.CellTemplate>
                        <DataTemplate>
                            <Grid>
                                <ProgressBar Background="Transparent" BorderThickness="0" Maximum=".99"
                                                     Value="{Binding SoftwareProficiency,StringFormat=P}"/>
                                <TextBlock   HorizontalAlignment="Center" VerticalAlignment="Center"
                                                     Text="{Binding SoftwareProficiency, StringFormat=P}"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:GridPercentColumn.CellTemplate>
                </syncfusion:GridPercentColumn>
            </syncfusion:SfDataGrid.Columns>
        </syncfusion:SfDataGrid>
    </Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight C# %}

SfSkinManager.SetVisualStyle(this, "MaterialDark");

{% endhighlight %}

{% endtabs %}

## Setting VisualStyle in C&#35;                                     

The following code example explains how to set the [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.SfSkinManager~VisualStyleProperty.html) property in C#.

{% tabs %}

{% highlight C# %}

SfSkinManager.SetVisualStyle(this, "MaterialDark");

{% endhighlight %}

{% endtabs %}

The output is displayed as follows.

![Applied skinmanager theme for WPF ChromelessWindow and SfDataGrid control](Themes_images/Themes_DataGrid.jpg)

N> View [sample](https://github.com/SyncfusionExamples/set-visualstyle-using-skinmanager) in GitHub.