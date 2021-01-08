---
layout: post
title: Appearance of the WPF Step ProgressBar control | Syncfusion
description: Learn about the appearance and look of the Syncfusion WPF Step ProgressBar (SfStepProgressBar) control and more details.
platform: WPF
control: Step ProgressBar
documentation: ug
---

# Appearance customization in WPF Step ProgressBar
You can highly customize the appearance of the Step progress bar in the following ways.

## Step Shape
You can change the shape of a step marker by using the [MarkerShapeType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_MarkerShapeType) property. The default value of this property is [Circle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_MarkerShapeType_Circle).

{% tabs %}
{% highlight XAML %}
<Grid x:Name="grid">
    <syncfusion:SfStepProgressBar MarkerShapeType="Square" SelectedIndex="3">
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
        stepProgressBar.MarkerShapeType = MarkerShapeType.Square;

        grid.Children.Add(stepProgressBar);
    }
}
{% endhighlight %}
{% endtabs %}

![Marker shape type image](Appearance_images/MarkerShapeType.png)

## Orientation
You can change the orientation of step progressbar by using the [Orientation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_Orientation) property. The default value of this property is [Horizontal](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_Orientation_Horizontal).
{% tabs %}
{% highlight XAML %}      
<Grid x:Name="grid">
    <syncfusion:SfStepProgressBar Orientation="Vertical" SelectedIndex="3">
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

        grid.Children.Add(stepProgressBar); 
    }
}           
{% endhighlight %}
{% endtabs %}
![Orientation image](Appearance_images/Orientation.png)

## Connector Customization
You can customize the color and thickness of the Step progressbar using the following property.

•[ActiveConnectorColor](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_ActiveConnectorColor): Represents the color of the connector for active state.

•[ConnectorColor](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_ConnectorColor): Represents the color of the connector for inactive state.

•[ConnectorThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_ConnectorThickness): Represents the thickness of connector line that connecting neighboring step view items.

{% tabs %}
{% highlight XAML %}      
<syncfusion:SfStepProgressBar SelectedIndex="2" ActiveConnectorColor="Coral" ConnectorColor="Crimson" ConnectorThickness="4">
    <syncfusion:StepViewItem Content="Ordered" />
    <syncfusion:StepViewItem Content="Shipped" />
    <syncfusion:StepViewItem Content="Packed" />
    <syncfusion:StepViewItem Content="Delivered" />
</syncfusion:SfStepProgressBar>
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
        stepProgressBar.ActiveConnectorColor =new SolidColorBrush(Colors.Coral);
        stepProgressBar.ConnectorColor = new SolidColorBrush(Colors.Crimson);
        stepProgressBar.ConnectorThickness = 4;

        grid.Children.Add(stepProgressBar);
    }
}
{% endhighlight %}
{% endtabs %}
![ColorCutomization Image](Appearance_images/ConnectorCustomization.png)

## MarkerClicked Event

You can get the [StepViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.StepViewItem.html) values when the marker of step view item is clicked. The following example shows this.

{% tabs %}
{% highlight xaml %}

<Syncfusion:SfStepProgressBar
    SelectedIndex="2"
    MarkerClicked="SfStepProgressBar_MarkerClicked">
    <Syncfusion:StepViewItem Content="Ordered" />
    <Syncfusion:StepViewItem Content="Packed" />
    <Syncfusion:StepViewItem Content="Shipped" />
    <Syncfusion:StepViewItem Content="Delivered" />
</Syncfusion:SfStepProgressBar>
{% endhighlight %}

{% highlight C# %}
private void SfStepProgressBar_MarkerClicked(object sender, MarkerClickedEventArgs e)
{
    ItemsControl itemsControl = ItemsControl.ItemsControlFromItemContainer(e.StepViewItem);
    int index = itemsControl.ItemContainerGenerator.IndexFromContainer(e.StepViewItem);
    (sender as SfStepProgressBar).SelectedIndex = index;
}
{% endhighlight %}
{% endtabs %}
![MarkerClicked image](Appearance_images/MarkerClicked.png)