---
layout: post
title: Sparkline Types in WPF Sparkline control | Syncfusion
description: Learn here all about Sparkline Types support in Syncfusion WPF Sparkline (SfSparkline) control and more.
platform: wpf
control: SfSparkline
documentation: ug
---

# Sparkline Types in WPF Sparkline (SfSparkline)

## Line sparkline

The line sparkline is rendered using a polyline. The following code is used to create a line sparkline.

{% tabs %}

{% highlight xaml %}

<Grid.DataContext>
    <local:UsersViewModel/>
</Grid.DataContext>

<Syncfusion:SfLineSparkline
    ItemsSource="{Binding UsersList}"
    YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
	ItemsSource = new UsersViewModel().UsersList,
	YBindingPath = "NoOfUsers"
};

{% endhighlight %}

{% endtabs %}

The following illustrates the result of the above code sample.

![Sparkline-Types_img1](Sparkline-Types_images/Sparkline-Types_img1.png)


## Column sparkline

The column sparkline is used to visualize the raw data as rectangles. The following code is used to create a column sparkline.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfColumnSparkline 
    ItemsSource="{Binding UsersList}" 
    YBindingPath="NoOfUsers">
</Syncfusion:SfColumnSparkline>

{% endhighlight  %}

{% highlight c# %}

SfColumnSparkline sparkline = new SfColumnSparkline()
{
	ItemsSource = new UsersViewModel().UsersList,
	YBindingPath = "NoOfUsers"
};

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the column sparkline.

![Sparkline-Types_img2](Sparkline-Types_images/Sparkline-Types_img2.png)

## Area sparkline

The following code is used to create an area sparkline. All line sparkline features are applicable for the area sparkline.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfAreaSparkline 
    ItemsSource="{Binding UsersList}" 
    YBindingPath="NoOfUsers">
</Syncfusion:SfAreaSparkline>

{% endhighlight  %}

{% highlight c# %}

SfAreaSparkline sparkline = new SfAreaSparkline()
{
	ItemsSource = new UsersViewModel().UsersList,
	YBindingPath = "NoOfUsers"
};

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the area sparkline.

![Sparkline-Types_img3](Sparkline-Types_images/Sparkline-Types_img3.png)

## WinLoss sparkline

The WinLoss sparkline renders as column segments and shows the positive, negative, and neutral values.

{% tabs %}

{% highlight xaml %}

<Page.DataContext>
	<local:MatchDetailsViewModel/>
</Page.DataContext>

<Syncfusion:SfWinLossSparkline 
	x:Name="sparkline" 
	ItemsSource="{Binding Match}" 
	YBindingPath="Result">
</Syncfusion:SfWinLossSparkline>

{% endhighlight %}

{% highlight c# %}

SfWinLossSparkline sparkline = new SfWinLossSparkline()
{
    ItemsSource = new MatchDetailsViewModel().Match,
    YBindingPath = "Result"
};

public class MatchDetailsModel
{
    public double Result { get; set; }
    public string Status { get; set; }
}

public class MatchDetailsViewModel
{
    public ObservableCollection<MatchDetailsModel> Match { get; set; }

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
}

{% endhighlight  %}

{% endtabs %}

Execute the above code to render the following output.

![Sparkline-Types_img4](Sparkline-Types_images/Sparkline-Types_img4.png)
