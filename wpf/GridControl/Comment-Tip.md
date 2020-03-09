---
layout: post
title: CommentTip in WPF GridControl | Syncfusion
description: Learn here about how to set CommentTip of Syncfusion WPF GridControl and specific cell or row and column.
platform: WPF
control: GridControl
documentation: ug
---

# Comment Tip in GridControl

Comment Tip can be added to individual cells, rows and columns to show more information about the particular cell on mouse hover. You can set the comment indicator at any position (TopLeft, TopRight, BottomLeft and BottomRight) in a specific cell or row or column by using [GridCommentStyleInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Grid.Wpf~Syncfusion.Windows.Controls.Grid.GridCommentStyleInfo.html). Comment Tip service can be enabled by setting [GridCommentService.SetShowComment](https://help.syncfusion.com/cr/wpf/Syncfusion.Grid.Wpf~Syncfusion.Windows.Controls.Grid.GridCommentService~SetShowComment.html) attached property to `true`.


## Comment Tip for specific cell

The comment tip can be added to the specific cell by setting the `Comment` property. The comment text will be displayed in the comment tip window.

{% tabs %}

{% highlight C# %}

grid.Model[1, 2].Comment = grid.Model[1, 0].CellValue + ":\nPopulation rate in " + grid.Model[1, 2].ColumnIndex + " is " + grid.Model[1, 2].CellValue;

{% endhighlight %}

{% endtabs %}

![Comment tip for specific cell in WPF GridControl](Commenttip_images/show-commenttip-specific_cell.png)

## Comment Tip for row and column

The comment tip can be added by row or column by setting the `Comment` property. The comment text will be displayed in the comment tip window.

{% tabs %}

{% highlight C# %}

//Add CommentTip for specific row
for (int i = 1; i <= 4; i++)
{
    string comment = grid.Model[1, 0].CellValue + " :\nPopulate rate in " + grid.Model[1, i].ColumnIndex + " is " + grid.Model[1, i].CellValue;
    grid.Model[1, i].Comment = comment;
}

//Add CommentTip for specific column
for (int i = 1; i < 4; i++)
{
    string comment = grid.Model[i, 0].CellValue + " :\nPopulate rate in " + grid.Model[i, 2].RowIndex + " is " + grid.Model[i, 2].CellValue;
    grid.Model[i, 2].Comment = comment;
}

{% endhighlight %}

{% endtabs %}

![CommentTip for specific row or column in WPF GridControl](Commenttip_images/show-commenttip-column.png)

## Change comment indicator position

You can change the comment indicator at any position in a specific cell or row or column by using `GridCommentStyleInfo`. For example, you set the comment indicator at top position in any cell by using [GridCommentStyleInfo.TopLeftComment](https://help.syncfusion.com/cr/wpf/Syncfusion.Grid.Wpf~Syncfusion.Windows.Controls.Grid.GridCommentStyleInfo~TopLeftComment.html) or [GridCommentStyleInfo.TopRightComment](https://help.syncfusion.com/cr/wpf/Syncfusion.Grid.Wpf~Syncfusion.Windows.Controls.Grid.GridCommentStyleInfo~TopRightComment.html) properties.

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/WPF-GridControl-CommentTip/tree/master/commenttip)

{% tabs %}

{% highlight C# %}

GridCommentStyleInfo styleInfo = new GridCommentStyleInfo();

// set the comment for specific cell
grid.Model[1, 2].GridCommentStyleInfo.TopLeftCommentBrush = Brushes.Red;
grid.Model[1, 2].GridCommentStyleInfo.TopLeftCommentBrush = Brushes.Red;
grid.Model[1, 2].GridCommentStyleInfo.TopLeftComment = grid.Model[1, 0].CellValue + ": \nPopulation rate in " + grid.Model[1, 2].ColumnIndex + " is " + grid.Model[1, 2].CellValue;

//Set comment tip for specific row
for (int i = 1; i <= 4; i++)
{
    //Set comment tip for specific row
    if (grid.Model[1, i].RowIndex == 1 && grid.Model[1, i].ColumnIndex > 0)
    {
        grid.Model[1, i].GridCommentStyleInfo.TopLeftCommentBrush = Brushes.Red;
        grid.Model[1, i].GridCommentStyleInfo.TopLeftComment = grid.Model[1, 0].CellValue + ": \nPopulation rate in " + grid.Model[1, i].ColumnIndex + " is " + grid.Model[1, i].CellValue;
    }
}

//Set comment tip for specific column
for (int i = 1; i < 4; i++)
{
    if (grid.Model[i, 2].ColumnIndex == 2 && grid.Model[i, 2].RowIndex > 0)
    {
        grid.Model[i, 2].GridCommentStyleInfo.TopLeftCommentBrush = Brushes.Red;
        grid.Model[i, 2].GridCommentStyleInfo.TopLeftComment = grid.Model[i, 0].CellValue + ": \nPopulation rate in " + grid.Model[i, 2].RowIndex + " is " + grid.Model[i, 2].CellValue;
    }
}

{% endhighlight %}

{% endtabs %}

![Change the comment indicator position in WPF GridControl](Commenttip_images/show-commenttip-indicatorposition.png)

N> Similarly, You can also change the comment indicator as the following position(TopRightComment, BottomLeftComment and BottomRightComment).

## Set CommentTip using QueryCellInfo

You can set the comment tip to a specific cell or row or column by using [QueryCellInfo](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Grid.Wpf~Syncfusion.Windows.Controls.Grid.GridModel~QueryCellInfo_EV.html) event.

{% tabs %}

{% highlight C# %}

private void Model_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{
    GridCommentStyleInfo gridStyleInfo = new GridCommentStyleInfo();

    //Set comment tip for specific cell
    if (e.Style.RowIndex == 1 && e.Style.ColumnIndex == 2)
    {
        e.Style.GridCommentStyleInfo.TopLeftCommentBrush = Brushes.Red;
        e.Style.GridCommentStyleInfo.TopLeftComment = e.Style.GridModel[1, 0].CellValue + ": \nPopulation rate in " + e.Style.ColumnIndex + " is " + e.Style.CellValue.ToString();
    }

    //set comment tip for specific row
    if (e.Style.RowIndex == 1 && e.Style.ColumnIndex > 0)
    {
        e.Style.GridCommentStyleInfo.TopLeftCommentBrush = Brushes.Red;
        e.Style.GridCommentStyleInfo.TopLeftComment = e.Style.GridModel[1, 0].CellValue + ": \nPopulation rate in " + e.Style.ColumnIndex + " is " + e.Style.CellValue.ToString();
    }

    //Set comment tip for specific column
    if (e.Style.ColumnIndex == 2)
    {
        e.Style.GridCommentStyleInfo.TopLeftCommentBrush = Brushes.Red;
        e.Style.GridCommentStyleInfo.TopLeftComment = e.Style.GridModel[e.Style.RowIndex, 0].CellValue + ": \nPopulation rate in " + e.Style.RowIndex + " is " + e.Style.CellValue.ToString();
    }
}

{% endhighlight %}

{% endtabs %}

![CommentTip for row and column using QueryCellInfo in WPF GridControl](Commenttip_images/show-commenttip-row_column.png)

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/WPF-GridControl-CommentTip/tree/master/commenttip_using_querycellinfo)

## Handling CommentTip opening event

The `CellCommentOpening` event will be triggered when the mouse hover on the cell has a comment indicator.

{% tabs %}

{% highlight C# %}

//CellCommentOpening event
grid.CellCommentOpening += Grid_CellCommentOpening;

grid.CellCommentOpening += Grid_CellCommentOpening;
private void Grid_CellCommentOpening(object sender, GridCellCommentOpeningEventArgs e)
{
    var grids = sender as GridControl;
    if (e.Cell.RowIndex == 1 && e.Cell.ColumnIndex == 2)
        grids.Model[e.Cell.RowIndex, e.Cell.ColumnIndex].GridCommentStyleInfo.TopLeftComment = "Hello";
}

{% endhighlight %}

{% endtabs %}

![Change the comment tip at run time in WPF GridControl](Commenttip_images/show-commenttip-openingevent.png)

## Customize the CommentTip

The comment can be customized by defining a TopLeftComment in the DataTemplate and assigning to the `GridCommentStyleInfo.TopLeftCommentTemplateKey` property of the GridControl. You can show the customized changes in comment tip window by using `GridRendererStyleInfo.Comment` property. Otherwise you can't see any customized changes.

{% tabs %}

{% highlight XAML %}

<Window.Resources>
    <DataTemplate x:Key="TopLeftComment">
        <Border x:Name="border" BorderThickness="1" BorderBrush="DarkBlue">
            <TextBlock Background="Purple" Foreground="White" FontSize="14" FontStyle="Italic" Text="{Binding Comment}" />
        </Border>
    </DataTemplate>
</Window.Resources>

{% endhighlight %}

{% highlight C# %}

grid.Model[1, 2].GridCommentStyleInfo.TopLeftCommentTemplateKey = "TopLeftComment";

//Using QueryCellInfo event
 private void Model_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{            
    if (e.Style.RowIndex == 1 && e.Style.ColumnIndex == 2)
    {
        e.Style.GridCommentStyleInfo.TopLeftCommentTemplateKey = "TopLeftComment";
    }
}

{% endhighlight %}

{% endtabs %}

![Customize the comment tip window in WPF GridControl](Commenttip_images/show-commenttip-window.png)


N> You can also customize the comment tip window in any position of comment tip indicator using `DataTemplate`.

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/WPF-GridControl-CommentTip/tree/master/commenttip_customization)
