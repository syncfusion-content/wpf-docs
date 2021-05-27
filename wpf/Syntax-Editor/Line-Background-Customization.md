---
layout: post
title: Line Background Customization in WPF Syntax Editor | Syncfusion
description: Learn about Line Background Customization support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
 documentation: ug
---

# Line Background Customization in WPF Syntax Editor

## Applying line background customization

The `SetLineBackground` function helps to customize the background color of specific lines.

### Method

`SetLineBackground(lineNumber, fullLine, brush)`: Helps to customize the background of line.

### Arguments

`lineNumber`: Specifies the line number where the cursor is currently located in EditControl.

`fullLine`: Specifies whether to highlight full line or not.

`brush`: Specifies the `Brush` for background customization.

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

## Resetting line background customization

The `ResetLineBackground` function helps to reset the background color of customized lines.

### Method

`ResetLineBackground(lineNumber)`: Helps to reset the background customization of line.

### Arguments

`lineNumber`: Specifies the line number where the cursor is currently located in EditControl.

{% tabs %}

{% highlight C# %}

// Reset the background to a specified Line.

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

