---
layout: post
title: Layout alignment of the WPF Step ProgressBar control | Syncfusion
description: Learn about layout options of the Syncfusion WPF Step ProgressBar (SfStepProgressBar) control and more details.
platform: WPF
control: Step ProgressBar
documentation: ug
---

# Layout Customization
You can customize the layout of the Step progressbar in the following ways.

## ItemsStretch
Represents how the item size is increased to fill the unused space. The default value of [ItemsStretch](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_ItemsStretch) property is `None`.

### Types
* None
* Fill

### None
The step view items retains its natural size.You can change the spacing between the adjacent step view items using the [ItemSpacing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_ItemSpacing) property. The default value of this property is 80.

N> The single step size is calculated using ItemSpacing and MarkerWidth or MarkerHeight based on Orientation. The ItemSpacing applies between the current step view item and previous step view item.

{% tabs %}
{% highlight XAML %}
<Grid x:Name="grid">
            <syncfusion:SfStepProgressBar SelectedIndex="2" ItemSpacing="150">
                <syncfusion:StepViewItem Content="Ordered" />
                <syncfusion:StepViewItem Content="Shipped" />
                <syncfusion:StepViewItem Content="Packed" />
                <syncfusion:StepViewItem Content="Delivered" />
            </syncfusion:SfStepProgressBar>
</Grid>
{% endhighlight %}
{% highlight C# %}
            SfStepProgressBar stepProgressBar = new SfStepProgressBar();
            StepViewItem orderedStepViewItem = new StepViewItem();
            StepViewItem shippedStepViewItem = new StepViewItem();
            StepViewItem packedStepViewItem = new StepViewItem();
            StepViewItem deliveredStepViewItem = new StepViewItem();

            orderedStepViewItem.Content = "Ordered";
            shippedStepViewItem.Content = "Shipped";
            packedStepViewItem.Content = "Packed";
            deliveredStepViewItem.Content = "Delivered";

            stepProgressBar.Items.Add(orderedStepViewItem);
            stepProgressBar.Items.Add(shippedStepViewItem);
            stepProgressBar.Items.Add(packedStepViewItem);
            stepProgressBar.Items.Add(deliveredStepViewItem);

            stepProgressBar.SelectedIndex = 2;
            stepProgressBar.ItemSpacing = 150;

            grid.Children.Add(stepProgressBar);
{% endhighlight %}
{% endtabs %}

![Item spacing image](Layout_images/ItemSpacing.png)

### Fill
The step view items are sized to fill the available space.
{% tabs %}
{% highlight XAML %}      
<Grid x:Name="grid">
            <syncfusion:SfStepProgressBar SelectedIndex="2" ItemsStretch="Fill">
                <syncfusion:StepViewItem Content="Ordered" />
                <syncfusion:StepViewItem Content="Shipped" />
                <syncfusion:StepViewItem Content="Packed" />
                <syncfusion:StepViewItem Content="Delivered" />
            </syncfusion:SfStepProgressBar>
</Grid>
{% endhighlight %}
{% highlight C# %}
SfStepProgressBar stepProgressBar = new SfStepProgressBar();
            StepViewItem orderedStepViewItem = new StepViewItem();
            StepViewItem shippedStepViewItem = new StepViewItem();
            StepViewItem packedStepViewItem = new StepViewItem();
            StepViewItem deliveredStepViewItem = new StepViewItem();

            orderedStepViewItem.Content = "Ordered";
            shippedStepViewItem.Content = "Shipped";
            packedStepViewItem.Content = "Packed";
            deliveredStepViewItem.Content = "Delivered";

            stepProgressBar.Items.Add(orderedStepViewItem);
            stepProgressBar.Items.Add(shippedStepViewItem);
            stepProgressBar.Items.Add(packedStepViewItem);
            stepProgressBar.Items.Add(deliveredStepViewItem);

            stepProgressBar.SelectedIndex = 2;
            stepProgressBar.ItemsStretch = ItemsStretch.Fill;

            grid.Children.Add(stepProgressBar);           
            {% endhighlight %}
{% endtabs %}
![Items stretch image](Layout_images/ItemsStretch.png)