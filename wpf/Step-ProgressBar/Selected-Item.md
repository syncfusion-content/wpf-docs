---
layout: post
title: Selected Item in WPF Step ProgressBar control | Syncfusion
description: Learn here all about Selected Item support in Syncfusion WPF Step ProgressBar (SfStepProgressBar) control and more.
platform: WPF
control: Step ProgressBar
 documentation: ug
---

# Selected Item in WPF Step ProgressBar (SfStepProgressBar)
You can customize the status of the StepView item in the following ways.

## SelectedItemStatus
You can change the status of last active (selected) step view item by using the [SelectedItemStatus](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_SelectedItemStatus) property. The default value of this property is [Inactive](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_SelectedItemStatus_Inactive).
{% tabs %}
{% highlight XAML %}      
<Grid x:Name="grid">
    <syncfusion:SfStepProgressBar SelectedIndex="2" SelectedItemStatus="Indeterminate">
        <syncfusion:StepViewItem Content="Ordered" />
        <syncfusion:StepViewItem Content="Shipped" />
        <syncfusion:StepViewItem Content="Packed" />
        <syncfusion:StepViewItem Content="Delivered" />
    </syncfusion:SfStepProgressBar>
</Grid>
{% endhighlight %}
{% highlight C# %}
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
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
        stepProgressBar.SelectedItemStatus = StepStatus.Indeterminate;
           
        grid.Children.Add(stepProgressBar);  
    }
}          
{% endhighlight %}
{% endtabs %}
![Selected item status image](Appearance_images/SelectedItemStatus.png)

## SelectedItemProgress
You can change the progress value of the last active (selected) step view item by using the [SelectedItemProgress](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_SelectedItemProgress) property. The default value of this property is `100.`
{% tabs %}
{% highlight XAML %}      
<Grid x:Name="grid">
    <syncfusion:SfStepProgressBar SelectedIndex="2" SelectedItemProgress="50" SelectedItemStatus="Indeterminate">
        <syncfusion:StepViewItem Content="Ordered" />
        <syncfusion:StepViewItem Content="Shipped" />
        <syncfusion:StepViewItem Content="Packed" />
        <syncfusion:StepViewItem Content="Delivered" />
    </syncfusion:SfStepProgressBar>
</Grid>
{% endhighlight %}
{% highlight C# %}
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
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
        stepProgressBar.SelectedItemStatus = StepStatus.Indeterminate;
        stepProgressBar.SelectedItemProgress = 50;
           
        grid.Children.Add(stepProgressBar); 
    }
}          
{% endhighlight %}
{% endtabs %}
![Selected item progress image](Appearance_images/SelectedItemProgress.png)

## AnimationDuration
You can change the the duration for completing the animation status of step view item by using the [AnimationDuration](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_AnimationDurationProperty) property. The default value of this property is `500ms.`

{% tabs %}
{% highlight XAML %}
<Grid x:Name="grid">
    <syncfusion:SfStepProgressBar SelectedIndex="3" AnimationDuration="0:0:1" Orientation="Vertical">
        <syncfusion:StepViewItem Content="Ordered" />
        <syncfusion:StepViewItem Content="Shipped" />
        <syncfusion:StepViewItem Content="Packed" />
        <syncfusion:StepViewItem Content="Delivered" />
    </syncfusion:SfStepProgressBar>
</Grid>
{% endhighlight %}
{% highlight C# %}
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
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

        stepProgressBar.SelectedIndex = 3;
        stepProgressBar.Orientation = Orientation.Vertical;
        stepProgressBar.AnimationDuration = new TimeSpan(0, 0, 1);

        grid.Children.Add(stepProgressBar);
    }
}
{% endhighlight %}
{% endtabs %}

![Animation duration image](Appearance_images/SelectedIndex.gif)
