---
layout: post
title: Line Background Customization in WPF Syntax Editor | Syncfusion
description: Learn about Line Background Customization support in Syncfusion Essential Studio WPF Syntax Editor (EditControl) control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# Line Background Customization in WPF Syntax Editor (EditControl)

The EditControl provides several ways to customize the background color of specific lines. The samples below assume `using Syncfusion.Windows.Edit;` and an `EditControl` instance named `editControl1`.

## Applying a line background

The `SetLineBackground` method customizes the background color of a single line.

### Method signature

`SetLineBackground(lineNumber, fullLine, brush)`: Helps to customize the background of line.

### Parameters

* `lineNumber` – the 1-based line number to which the background is applied.
* `fullLine` – `true` to highlight the full line width; `false` to highlight only the text area.
* `brush` – the `System.Windows.Media.Brush` used to paint the background.

{% tabs %}

{% highlight C# %}

// Set the background to a specified Line.

this.editControl1.SetLineBackground(this.editControl1.LineNumber, true, Brushes.Yellow);

{% endhighlight %}

{% highlight VB %}

' Set the background to a specified Line.

this.editControl1.SetLineBackground(this.editControl1.LineNumber, true, Brushes.Yellow)

{% endhighlight  %}

{% endtabs %}

![SetLineBackground](Line-Background-Customization_images/SetLineBackground.png)

## Resetting a line background

The `ResetLineBackground` method clears the background color applied by `SetLineBackground`.

### Method signature

`ResetLineBackground(lineNumber)`: Helps to reset the background customization of line.

### Parameters

* `lineNumber` – the 1-based line number to reset.

{% tabs %}

{% highlight C# %}
// Reset the background of the current line.
this.editControl1.ResetLineBackground(this.editControl1.LineNumber);

{% endhighlight %}

{% highlight VB %}

' Reset the background to a specified Line.

this.editControl1.ResetLineBackground(this.editControl1.LineNumber)

{% endhighlight  %}

{% endtabs %}

## On demand line background customization

The `OnBeforeLineRender` event customizes the background color of the line on demand.

{% tabs %}

{% highlight C# %}

public MainWindow()

{

     InitializeComponent();

     editControl1.DocumentSource = "../../Source.cs";
     
     editControl1.OnBeforeLineRender += new 
     
     Syncfusion.Windows.Edit.OnBeforeLineRenderEventHandler(editControl1_OnBeforeLineRender);
}

// Invoked when before the Line Render.

 private void editControl1_OnBeforeLineRender(object sender, Syncfusion.Windows.Edit.OnBeforeLineRenderArgs args)
{
   
    if (args.LineItem.LineNumber % 2 == 0)
   
        {
            args.BackgroundColor = Brushes.LightGray;
            args.IsFullLine = false;
        }
}

{% endhighlight %}

{% highlight VB %}

public MainWindow()

{

     InitializeComponent()

     editControl1.DocumentSource = "../../Source.cs"
     
     editControl1.OnBeforeLineRender += new 
     
     Syncfusion.Windows.Edit.OnBeforeLineRenderEventHandler(editControl1_OnBeforeLineRender)
}

' Invoked when before the Line Render.

 private void editControl1_OnBeforeLineRender(object sender, Syncfusion.Windows.Edit.OnBeforeLineRenderArgs args)
{
   
    if (args.LineItem.LineNumber % 2 == 0)
   
        {
   
            args.BackgroundColor = Brushes.LightGray
   
            args.IsFullLine = false;   
        }
}

{% endhighlight  %}

{% endtabs %}

N> The on demand line background customization is recommended when the `EditControl` is loaded with huge data.

![OnBeforeEvent](Line-Background-Customization_images/OnBeforeEvent.png)
