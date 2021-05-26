---
layout: post
title: Sparkline Types in WPF Sparkline control | Syncfusion
description: Learn here all about Sparkline Types support in Syncfusion WPF Sparkline (SfSparkline) control and more.
platform: wpf
control: SfSparkline
 documentation: ug
---

# Sparkline Types in WPF Sparkline (SfSparkline)

## Line Sparkline

Line sparkline rendered using polyline and the following code is used to create line sparkline,

{% tabs %}

{% highlight xaml %}

<Grid.DataContext>

	<local:UsersViewModel/>

</Grid.DataContext>

<Syncfusion:SfLineSparkline ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers"

};

{% endhighlight %}

{% endtabs %}

The following illustrates the result of the above code sample,

![Sparkline-Types_img1](Sparkline-Types_images/Sparkline-Types_img1.png)


## Column Sparkline

Column sparkline used to visualize the raw data as a rectangle and following code is used to create column sparkline,

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfColumnSparkline ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

</Syncfusion:SfColumnSparkline>

{% endhighlight  %}

{% highlight c# %}

SfColumnSparkline sparkline = new SfColumnSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers"

};

{% endhighlight %}

{% endtabs %}

Following is the snapshot for Column Sparkline,

![Sparkline-Types_img2](Sparkline-Types_images/Sparkline-Types_img2.png)

## Area sparkline

Following code is used to create area sparkline and all the line sparkline features are applicable for area sparkline,

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfAreaSparkline ItemsSource="{Binding UsersList}"  YBindingPath="NoOfUsers">

</Syncfusion:SfAreaSparkline >

{% endhighlight  %}

{% highlight c# %}

SfAreaSparkline sparkline = new SfAreaSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers"

};

{% endhighlight %}

{% endtabs %}

Following is the snapshot for area sparkline,

![Sparkline-Types_img3](Sparkline-Types_images/Sparkline-Types_img3.png)

## WinLoss Sparkline

WinLoss sparkline render as a column segment and it show the positive, negative and neutral values.

{% tabs %}

{% highlight xaml %}

<Page.DataContext>

	<local:MatchDetailsViewModel/>

</Page.DataContext>

<Syncfusion:SfWinLossSparkline x:Name="sparkline" ItemsSource="{Binding Match}" YBindingPath="Result" >

</Syncfusion:SfWinLossSparkline>

{% endhighlight %}

{% highlight c# %}

SfWinLossSparkline sparkline = new SfWinLossSparkline()
{

	ItemsSource = new SparkViewModel().Match,

	YBindingPath = "Result"

};

public class MatchDetailsModel

{

	public double Result { get; set; }

	public string Status { get; set; }

}

public class MatchDetailsViewModel

{

	public MatchDetailsViewModel()

	{

		this.Match = new ObservableCollection<MatchDetailsModel>();

		this.Match.Add(new MatchDetailsModel() { Result = 1, Status = "Win" });

		this.Match.Add(new MatchDetailsModel() { Result = -1, Status = "Loss" });

		this.Match.Add(new MatchDetailsModel() { Result = 0, Status = "Draw" });

		this.Match.Add(new MatchDetailsModel() { Result = 1, Status = "Win" });

		this.Match.Add(new MatchDetailsModel() { Result = 1, Status = "Win" });

		this.Match.Add(new MatchDetailsModel() { Result = -1, Status = "Loss" });

	}

	public ObservableCollection<MatchDetailsModel> Match { get; set; }

}

{% endhighlight  %}

{% endtabs %}

Execute the above code to render the following output.

![Sparkline-Types_img4](Sparkline-Types_images/Sparkline-Types_img4.png)
