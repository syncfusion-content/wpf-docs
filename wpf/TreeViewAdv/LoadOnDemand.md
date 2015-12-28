# LoadOnDemand

The LoadOnDemand feature enables users to load items dynamically when a particular TreeViewItem is expanded. Hence the items are loaded on demand and reduce the loading time.

1. To load items on demand: 
  * LoadOnDemand event is used to load the sub-items when a particular item is expanded.
  * LoadingHeader is used to display the text while sub-items are being loaded.
  * IsLoadOnDemand value has to be set to true if the item is to be loaded on demand.

{% tabs %}

{% highlight XAML %}
<syncfusion:TreeViewAdv x:Name="treeViewAdv" LoadOnDemand="treeViewAdv_LoadOnDemand">

<syncfusion:TreeViewItemAdv Header="Root1" IsLoadOnDemand="True" LoadingHeader="Loading....." />

<syncfusion:TreeViewItemAdv Header="Root2" IsLoadOnDemand="True" LoadingHeader="Loading....." />

</syncfusion:TreeViewAdv>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}
public partial class MainWindow : Window

{

public MainWindow()

{

InitializeComponent();

timer = new DispatcherTimer();

timer.Interval = new TimeSpan(0, 0, 0, 0, 800);

timer.Tick += new EventHandler(timer_Tick);

}

private void timer_Tick(object sender, EventArgs e)

{

if(loadingitem!=null)

{

for (int i = 0; i <= 5; i++)

{

loadingitem.Items.Add(new TreeViewItemAdv() { Header = "Node" + i });

}

loadingitem.IsLoadOnDemand = false;

timer.Stop();

}

}

private DispatcherTimer timer;

private TreeViewItemAdv loadingitem;

private void treeViewAdv_LoadOnDemand(object sender, LoadonDemandEventArgs args)

{

loadingitem = args.TreeViewItem as TreeViewItemAdv;

timer.Start();

}

}

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}  

![](LoadOnDemand_images/LoadOnDemand_img1.jpeg)


