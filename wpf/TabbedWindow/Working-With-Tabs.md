---
layout: post
title: Working With Tabs — TabbedWindow | Syncfusion®
description: Add, remove, and manage tabs in a TabbedWindow; using the updated `AddingNewTab` event.
platform: WPF
control: TabbedWindow
documentation: ug
---
# Working With Tabs

This page explains common tab operations for `TabbedWindow`: adding, creating via the new‑tab flow, closing, selecting, and lifecycle management.

## Adding tabs

You can add tabs declaratively in XAML or at runtime in code. When using MVVM prefer `ItemsSource` with a view model collection.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTabControl x:Name="MainTabControl">
  <syncfusion:SfTabItem Header="Home"> <TextBlock Text="Home"/> </syncfusion:SfTabItem>
</syncfusion:SfTabControl>
{% endhighlight %}

{% highlight C# %}

var tab = new SfTabItem { Header = "Notes", Content = new NotesView() };
MainTabControl.Items.Add(tab);
MainTabControl.SelectedItem = tab;
{% endhighlight %}
{% endtabs %}

Use `ItemsSource` to bind a collection of tab view models and provide `ItemTemplate`/`ContentTemplate` to render headers and content.

{% tabs %}
{% highlight XAML %}
<syncfusion:SfTabControl ItemsSource="{Binding OpenTabs}"
             ItemTemplate="{StaticResource TabHeaderTemplate}"
             ContentTemplate="{StaticResource TabContentTemplate}"
             SelectedItem="{Binding ActiveTab, Mode=TwoWay}" />
{% endhighlight %}
{% highlight C# %}
// ViewModel (simplified)
public class MainViewModel
{
  public ObservableCollection<TabViewModel> OpenTabs { get; } = new ObservableCollection<TabViewModel>();
  public TabViewModel ActiveTab { get; set; }
}

// Add a tab in view model
OpenTabs.Add(new TabViewModel { Title = "Notes", Content = new NotesViewModel() });
{% endhighlight %}
{% endtabs %}

## Creating new tabs (AddingNewTab)

The control raises `AddingNewTab` (type `AddingNewTabEventArgs`) when the user invokes the new‑tab action (new‑tab button or programmatic request). Handle this event to supply default content, set headers, or cancel creation.

{% tabs %}
{% highlight C# %}
MainTabControl.AddingNewTab += MainTabControl_AddingNewTab;

private void MainTabControl_AddingNewTab(object sender, AddingNewTabEventArgs e)
{
  e.Item = new SfTabItem { Header = "Untitled", Content = new TextBlock { Text = "New" } };
}
{% endhighlight %}
{% endtabs %}

![WPF New Tab](Working-with-tabs/wpf_newtab.gif)

## Closing tabs

Tabs are closed by removing the corresponding `SfTabItem` from `SfTabControl.Items`. You can expose close UI in headers or use built‑in close affordances.

### Example: Programmatic close and per‑item close control

{% tabs %}
{% highlight C# %}
// close programmatically
MainTabControl.Items.Remove(tabToClose);

// hide close affordance on a specific tab
tabToClose.CloseButtonVisibility = false;
{% endhighlight %}
{% endtabs %}

## Selection and events

Use `SelectedItem` / `SelectedIndex` to set selection in code. Handle selection change events to lazy‑load content or save state.

{% tabs %}
{% highlight C# %}

MainTabControl.SelectedItemChanged += MainTabControl_SelectedItemChanged;

private void MainTabControl_SelectedItemChanged(object sender, SelectedItemChangedEventArgs e)
{
  // e.OldSelectedItem and e.NewSelectedItem available
}
{% endhighlight %}
{% endtabs %}
