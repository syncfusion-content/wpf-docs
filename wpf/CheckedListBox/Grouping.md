---
layout: post
title: Grouping | CheckListBox | wpf | Syncfusion
description: This section describes how to group the Checklistbox items present in the CheckListBox and its basic features.
platform: wpf
control: CheckListBox
documentation: ug
---

# Grouping

In CheckListBox, grouping is possible, and CheckListBoxItems can be grouped using the [GroupDescriptions](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~GroupDescriptions.html) property. The selection state of Group header varies based on the checked or unchecked state of the child items. Group can be expanded or collapsed and the child items present in the group can be checked or unchecked based on the user’s perspective. The CheckListBox also allows nested grouping.

{% tabs %}
{%highlight xaml%}
        <syncfusion:CheckListBox.GroupDescriptions>
            <local:Groups>
                <PropertyGroupDescription PropertyName="Category"></PropertyGroupDescription>
            </local:Groups>
        </syncfusion:CheckListBox.GroupDescriptions>
{%endhighlight%}

{% highlight c#%}

ObservableCollection<GroupDescription> groupDescriptors = new ObservableCollection<GroupDescription>
            {
                new PropertyGroupDescription{PropertyName="Category"}
            };
this.checkListBox.GroupDescriptions = groupDescriptors;

{%endhighlight%}
{% endtabs %}

![Grouping](Grouping-Sorting_images/Grouping_image.png)