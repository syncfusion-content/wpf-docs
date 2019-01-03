---
layout: post
title:  Placeholderstyle | SfKanban | wpf | Syncfusion
description: The following section describes the place holders of Kanban card while dragging.
platform: wpf
control: SfKanban
documentation: ug
---

# Placeholder.

The placeholder is to denote a card's new position in the [`KanbanColumn`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn.html). It will appear while dragging a card over the column.

### Placeholder style

[`PlaceholderStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle.html) property is used to customize the placeholder. Following properties are used to customize its appearance.

* [`Fill`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~Fill.html)  	 - This property is used to change the background color of the placeholder.
* [`Stroke`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~Stroke.html) 	 	 - This property is used to change the border color of the placeholder.
* [`StrokeThickness`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~StrokeThickness.html)  	 - This property is used to change the border width of the placeholder.
* [`StrokeDashArray`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~StrokeDashArray.html)     - This property is used to change the dashes of the placeholder border.
* [`FontSize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~FontSize.html)            - This is used to change the text size of the placeholder.
* [`Foreground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~Foreground.html)           - This property is used to change the text color of the placeholder.

Following properties are used to customize the selected category when you have more than one category in a column.

* [`SelectedBackground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~SelectedBackground.html) 	- This property is used to change the background color of the selected placeholder.
* [`SelectedStroke`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~SelectedStroke.html) 		- This property is used to change the border color of the selected placeholder.
* [`SelectedStrokeThickness`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~SelectedStrokeThickness.html) 	- This property is used to change the border width of the selected placeholder.
* [`SelectedStrokeDashArray`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~SelectedStrokeDashArray.html)     - This property is used to change the dashes of the selected placeholder.
* [`SelectedFontSize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~SelectedFontSize.html)            - This is used to change the font size of the text in selected placeholder.
* [`SelectedForeground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.PlaceholderStyle~SelectedForeground.html)           - This property is used to change the color of the text in selected placeholder.
The following code example describes the above behavior.

{% tabs %}

{% highlight xaml %}

<kanban:PlaceholderStyle FontSize="20"

                         Foreground="DarkGreen"

                         Fill="Fuchsia"

                         Stroke="Blue"

                         StrokeThickness="2"

                         SelectedFontSize="20"

                         SelectedForeground="Maroon"

                         SelectedStroke="Yellow"

                         SelectedStrokeThickness="2"

                         SelectedBackground="LawnGreen">

</kanban:PlaceholderStyle>


{% endhighlight %}

{% highlight C# %}

PlaceholderStyle style = new PlaceholderStyle();

style.FontSize = 20;

style.Foreground = new SolidColorBrush(Colors.DarkGreen);

style.Fill = new SolidColorBrush(Colors.Fuchsia);

style.Stroke = new SolidColorBrush(Colors.Blue);

style.StrokeThickness = 2;

style.StrokeDashArray = new DoubleCollection() {1, 1};

style.SelectedFontSize = 20;

style.SelectedForeground = new SolidColorBrush(Colors.Maroon);

style.SelectedStroke = new SolidColorBrush(Colors.Yellow);

style.SelectedBackground = new SolidColorBrush(Colors.LawnGreen);

style.SelectedStrokeThickness = 2;

style.SelectedStrokeDashArray = new DoubleCollection() {2, 1};

sfKanban.PlaceholderStyle = style;

{% endhighlight %}

{% endtabs %}

The following output demonstrates the above code example.

![](SfKanban_images/PlaceholderStyle.png)
