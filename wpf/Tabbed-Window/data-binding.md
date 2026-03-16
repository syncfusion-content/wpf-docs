---
layout: post
title: Data Binding in WPF Tabbed Window | Syncfusion
description: Bind tabs to collections using ItemsSource for MVVM-based tabbed window scenarios.
platform: WPF
control: TabbedWindow
documentation: ug
---

# WPF Tabbed Window - Data Binding

## Overview

The Tabbed Window provides full MVVM support through data binding. You can bind tabs to a collection using the `ItemsSource` property, enabling data-driven tab creation and dynamic content updates.

## ItemsSource Binding

Bind the `ItemsSource` property to a collection in your ViewModel. Each item automatically generates a corresponding tab:

```xaml
<syncfusion:SfTabControl 
    ItemsSource="{Binding Documents}" 
    SelectedItem="{Binding SelectedDocument}">
    <syncfusion:SfTabControl.ItemTemplate>
        <DataTemplate>
            <syncfusion:SfTabItem Header="{Binding Title}">
                <ContentControl Content="{Binding Content}" />
            </syncfusion:SfTabItem>
        </DataTemplate>
    </syncfusion:SfTabControl.ItemTemplate>
</syncfusion:SfTabControl>
```

## ViewModel Example

```csharp
public class DocumentViewModel : INotifyPropertyChanged
{
    public ObservableCollection<Document> Documents { get; set; }
    
    private Document _selectedDocument;
    public Document SelectedDocument
    {
        get { return _selectedDocument; }
        set 
        { 
            if (_selectedDocument != value)
            {
                _selectedDocument = value;
                OnPropertyChanged(nameof(SelectedDocument));
            }
        }
    }

    public DocumentViewModel()
    {
        Documents = new ObservableCollection<Document>
        {
            new Document { Title = "Document 1", Content = "Content 1" },
            new Document { Title = "Document 2", Content = "Content 2" }
        };
        SelectedDocument = Documents[0];
    }

    public event PropertyChangedEventHandler PropertyChanged;

    private void OnPropertyChanged(string propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
}
```

## Model Example

```csharp
public class Document : INotifyPropertyChanged
{
    private string _title;
    public string Title
    {
        get { return _title; }
        set 
        { 
            if (_title != value)
            {
                _title = value;
                OnPropertyChanged(nameof(Title));
            }
        }
    }

    private string _content;
    public string Content
    {
        get { return _content; }
        set 
        { 
            if (_content != value)
            {
                _content = value;
                OnPropertyChanged(nameof(Content));
            }
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    private void OnPropertyChanged(string propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
}
```

## ItemTemplate Customization

Use `ItemTemplate` to customize how each tab item is displayed:

```xaml
<syncfusion:SfTabControl ItemsSource="{Binding Projects}">
    <syncfusion:SfTabControl.ItemTemplate>
        <DataTemplate>
            <syncfusion:SfTabItem 
                Header="{Binding ProjectName}" 
                CloseButtonVisibility="Visible">
                <Grid>
                    <StackPanel Padding="10">
                        <TextBlock Text="{Binding Description}" FontSize="14" />
                        <TextBlock Text="{Binding Status}" Foreground="Gray" Margin="0,5,0,0" />
                    </StackPanel>
                </Grid>
            </syncfusion:SfTabItem>
        </DataTemplate>
    </syncfusion:SfTabControl.ItemTemplate>
</syncfusion:SfTabControl>
```

## ContentTemplate Support

Separate header and content templates for flexible UI composition:

```xaml
<syncfusion:SfTabControl 
    ItemsSource="{Binding Tabs}"
    SelectedItem="{Binding SelectedTab}">
    
    <!-- Header Template -->
    <syncfusion:SfTabControl.HeaderTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal" Margin="5">
                <Image Source="{Binding Icon}" Width="16" Height="16" Margin="0,0,5,0" />
                <TextBlock Text="{Binding Name}" />
            </StackPanel>
        </DataTemplate>
    </syncfusion:SfTabControl.HeaderTemplate>
    
    <!-- Content Template -->
    <syncfusion:SfTabControl.ContentTemplate>
        <DataTemplate>
            <local:TabContentView DataContext="{Binding}" />
        </DataTemplate>
    </syncfusion:SfTabControl.ContentTemplate>
</syncfusion:SfTabControl>
```


