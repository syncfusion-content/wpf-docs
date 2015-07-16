---
layout: post
title: Sparkline-Types
description: sparkline types
platform: wpf
control: Sparkline
documentation: ug
---

# Sparkline Types

## Line Sparkline

Line sparkline rendered using polyline and the following code is used to create line sparkline,

[XAML]

…

            &lt;Grid.DataContext&gt;

                &lt;local:UsersViewModel/&gt;

            &lt;/Grid.DataContext&gt;

            <Syncfusion:SfLineSparkline 

	                ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

            &lt;/Syncfusion:SfLineSparkline &gt;



The following illustrates the result of the above code sample,

{ ![C:/Users/ApoorvahR/Desktop/1.png](Sparkline-Types_images/Sparkline-Types_img1.png) | markdownify }
{:.image }


## Column Sparkline

Column sparkline used to visualize the raw data as a rectangle and following code is used to create column sparkline,

[XAML]

   &lt;Syncfusion:SfColumnSparkline ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" &gt;

        &lt;/Syncfusion:SfColumnSparkline&gt;

Following is the snapshot for Column Sparkline,

{ ![C:/Users/ApoorvahR/Desktop/2.png](Sparkline-Types_images/Sparkline-Types_img2.png) | markdownify }
{:.image }


## Area sparkline

Following code is used to create area sparkline and all the line sparkline features are applicable for area sparkline,

[XAML]

  <Syncfusion:SfAreaSparkline 

 ItemsSource="{Binding UsersList}"  YBindingPath="NoOfUsers">

  &lt;/Syncfusion:SfAreaSparkline &gt;

Following is the snapshot for area sparkline,

{ ![C:/Users/ApoorvahR/Desktop/3.png](Sparkline-Types_images/Sparkline-Types_img3.png) | markdownify }
{:.image }


## WinLoss Sparkline

WinLoss sparkline render as a column segment and it show the positive, negative and neutral values.

[XAML]

…

  &lt;Page.DataContext&gt;

            &lt;local:MatchDetailsViewModel/&gt;

  &lt;/Page.DataContext&gt;

        &lt;Syncfusion:SfWinLossSparkline x:Name="sparkline" ItemsSource="{Binding Match}" YBindingPath="Result" &gt;

        &lt;/Syncfusion:SfWinLossSparkline&gt;



[C#]

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

Execute the above code to render the following output.


{ ![C:/Users/ApoorvahR/Desktop/4.png](Sparkline-Types_images/Sparkline-Types_img4.png) | markdownify }
{:.image }


