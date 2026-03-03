---
layout: post
title: Customization in WPF SmartDataGrid control | Syncfusion®
description: Learn here all about how to customize behavior and features of Syncfusion® WPF SmartDataGrid (SfSmartDataGrid) control and more.
platform: WPF
control: SfSmartDataGrid
documentation: UG
keywords : WPF datagrid, customization, assistview, prompts, smart actions
---

# Customization in WPF SmartDataGrid (SfSmartDataGrid)

The `SfSmartDataGrid` provides options to customize its behavior and appearance, including predefined suggestions, initial prompts, enabling or disabling smart actions.

## Suggestions

The `Suggestions` property in `SfSmartDataGrid` is used to provide a predefined list of suggestions that appear in the AssistView. These suggestions help users quickly select common actions without typing commands manually.

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfSmartDataGrid x:Name="SmartGrid" Suggestions="{Binding AiSuggestions}"/>
{% endhighlight %}

{% highlight c# %}
public class OrderInfoRepository
{
	public ObservableCollection<string> AiSuggestions { get; } = new ObservableCollection<string>
	{
		"Which orders have a payment status of Not Paid?",
		"What are the top 10 orders with the highest freight cost?",
		"Which customers have placed the most orders?",
		"What are the orders shipped to Brazil?",
		"What is the total quantity of products ordered across all orders?",
	};
}
{% endhighlight %}
{% endtabs %}

<img alt="WPF-smart-datagrid-suggested-prompts" src="Images\Customization\WPF-smart-datagrid-suggested-prompts.png" width="600"/>

## Prompt

The `Prompt` property in `SfSmartDataGrid` defines an initial prompt that is automatically executed when the AssistView opens for the first time. 

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfSmartDataGrid x:Name="SmartGrid" Prompt="Sort the Quantity column"/>
{% endhighlight %}

{% highlight c# %}
SmartGrid.Prompt = "Sort the Quantity column";;
{% endhighlight %}
{% endtabs %}

## EnableSmartActions

The `EnableSmartActions` property in `SfSmartDataGrid` determines whether actions are applied to the DataGrid. By default, this property is set to true, allowing operations such as sorting, grouping, filtering, and highlighting to be executed automatically. Setting it to false restricts these actions from being applied to the grid.

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfSmartDataGrid x:Name="SmartGrid" ItemsSource="{Binding OrderInfoCollection}" EnableSmartActions="True"/>
{% endhighlight %}

{% highlight c# %}
SmartGrid.EnableSmartActions = true;
{% endhighlight %}
{% endtabs %}

## Apply Smart Actions Programmatically

The `ExecutePrompt` method in `SfSmartDataGrid` is used to fetch a response programmatically without opening the AssistView popup. By passing a prompt to this method, the required action is applied directly to the DataGrid. 

{% tabs %}
{% highlight c# %}
SmartGrid.ExecutePrompt("Sort the OrderID by Descending");
{% endhighlight %}
{% endtabs %}


## Events

### AssistViewRequest

The `SfSmartDataGrid.AssistViewRequest` event is triggered whenever a user request is sent. This event provides the Prompt as an argument through `AssistViewRequestEventArgs` and includes a `Cancel` property. Setting Cancel to true prevents the request from being processed.

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfSmartDataGrid ItemsSource="{Binding OrderInfoCollection}" 
                           AssistViewRequest="OnAssistRequest">
    </syncfusion:SfSmartDataGrid>
{% endhighlight %}

{% highlight c# %}
private void OnAssistRequest(object sender, AssistViewRequestEventArgs e)
{
    var prompt = e.Prompt;
    e.Cancel = True;
}
{% endhighlight %}
{% endtabs %}