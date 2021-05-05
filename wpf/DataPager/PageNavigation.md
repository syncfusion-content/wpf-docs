---
layout: post
title: PageNavigation in WPF DataPager control | Syncfusion
description: Learn here all about PageNavigation support in Syncfusion WPF DataPager (SfDataPager) control and more.
platform: wpf
control: SfDataPager Control
documentation: ug
---

# PageNavigation in WPF DataPager (SfDataPager)

SfDataPager allows you to move from the current Page to various Pages.For example, when you want to move the CurrentPage to the last page directly, you can use the method MoveToLastPage() . When this method is called, the current page moves to the last page. 

SfDataPager provides the following methods for page navigations.

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
MoveToFirstPage</td><td>
MoveToFirstPage()</td><td>
This method moves the current page index to the first page and displays the first page data.</td></tr>
<tr>
<td>
MoveToLastPage</td><td>
MoveToLastPage()</td><td>
This method moves the current page index to the last page and displays the last page data.</td></tr>
<tr>
<td>
MoveToNextPage</td><td>
MoveToNextPage()</td><td>
This method moves the current page index to the next page and displays the next page data. </td></tr>
<tr>
<td>
MoveToPreviousPage</td><td>
MoveToPreviousPage()</td><td>
This method moves the current page index to the previous page and displays the previous page data.</td></tr>
<tr>
<td>
MoveToPage</td><td>
MoveToPage(int pageIndex)</td><td>
This method moves the current page index to the corresponding page index that is passed as an argument.</td></tr>
</table>


## How To

## How to Interact with User before Page Changes

When you are working with Paging, you may be in Edit mode or in CurrentPage. In this case, you can stop navigating the Paging by using the PageIndexChanging event before changing the page.

The following example displays the MessageBox before the PageChanging,

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*" />
        <RowDefinition Height="Auto" />
    </Grid.RowDefinitions>
    <sfgrid:SfDataGrid AutoGenerateColumns="True" 
                       Grid.Row="0"
                       ItemsSource="{Binding ElementName=sfDataPager,Path=PagedSource}"/>
    <datapager:SfDataPager x:Name="sfDataPager" 
                           NumericButtonCount="10"
                           Grid.Row="1"
                           PageSize="16" 
                           PageIndexChanging="sfDataPager_PageIndexChanging"
                           Source="{Binding OrdersDetails}" />
</Grid>
{% endhighlight %}
{% highlight c# %}
private void sfDataPager_PageIndexChanging(object sender, Syncfusion.UI.Xaml.Controls.DataPager.PageIndexChangingEventArgs e)
{
    MessageBoxResult result = MessageBox.Show("Do you want to change the page?", "Confirm", MessageBoxButton.YesNo);

    if (result == MessageBoxResult.No)
    {
        e.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}
