---
layout: post
title: Workflows | SfKanban | wpf | Syncfusion
description: The following section describes about the workflows in the Kanban.
platform: wpf
control: SfKanban
documentation: ug
---

# Workflow configuration.

A Kanban workflow is a set of Category and AllowedTransitions that an item moves through its life cycle and typically represents processes within your organization.

* Category – It represents a state of an item at a particular point in a specific workflow.

* AllowedTransitions – It is a list of categories to where the card can be moved from the current category.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfKanban.Workflows>
    
    <syncfusion:KanbanWorkflow Category="Open">
    
        <syncfusion:KanbanWorkflow.AllowedTransitions>
    
            <x:String>In Progress</x:String>
    
        </syncfusion:KanbanWorkflow.AllowedTransitions>
    
    </syncfusion:KanbanWorkflow>

    <syncfusion:KanbanWorkflow Category="In Progress">
    
        <syncfusion:KanbanWorkflow.AllowedTransitions>
    
            <x:String>Review</x:String>
    
            <x:String>Done</x:String>
    
        </syncfusion:KanbanWorkflow.AllowedTransitions>
    
    </syncfusion:KanbanWorkflow>

</syncfusion:SfKanban.Workflows>

{% endhighlight %}

{% highlight c# %}

WorkflowCollection workflows = new WorkflowCollection();

workflows.Add(new KanbanWorkflow()

{

    Category = "Open",

    AllowedTransitions = new List<object>() {"In Progress"}

});

workflows.Add(new KanbanWorkflow()

{

    Category = "In Progress",

    AllowedTransitions = new List<object>() {"Review", "Done"}

});

Kanban.Workflows = workflows;

{% endhighlight %}

{% endtabs %}

![](SfKanban_images/workflow.png)

## Work In-Progress limit

MinimumLimit and MaximumLimit properties are used to limit the minimum and maximum items in the Kanban column. However, this will not restrict moving the items from one column to another column. But the violation of the limit can be indicated by changing the color of the error bar.

Following properties are used to customize the error bar.

* Color – used to set the default color of the error bar.

* MinValidationColor – used to set the color of the error bar when the items count is lesser than MinimumLimit.

* MaxValidationColor – used to set the color of the error bar when the items count is greater than MaximumLimit.

{% tabs %}

{% highlight xaml %}

<syncfusion:KanbanColumn x:Name="column1" Categories="Review,Done"
                         
                         Title="Done"
                         
                         MinimumLimit="1"
                         
                         MaximumLimit="2">
	     
         <syncfusion:KanbanColumn.ErrorBarSettings>
		
        	   <syncfusion:ErrorBarSettings Color="Gray" MaxValidationColor="Red"
        
                                            MinValidationColor="Green">
		
        	   </syncfusion:ErrorBarSettings>
        
         </syncfusion:KanbanColumn.ErrorBarSettings>

</syncfusion:KanbanColumn>

{% endhighlight %}

{% highlight c# %}

column1.MinimumLimit = 1;

column1.MaximumLimit = 2;

column1.ErrorBarSettings = new ErrorBarSettings()

{

    Color = new SolidColorBrush(Colors.Gray),

    MinValidationColor = new SolidColorBrush(Colors.Green),

    MaxValidationColor = new SolidColorBrush(Colors.Red)

};

{% endhighlight %}

{% endtabs %}

![](SfKanban_images/wiplimit.png)