---
layout: post
title: Line Background support of the Edit Control for WPF
description: Line Background support of the Edit Control for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---

# Line Background customization

## Apply Line Background customization

The `SetLineBackground` function helps to customize the background color of specific lines.

### Method

`SetLineBackground(lineNumber, fullLine, brush)` - Helps to customize the Background of Line. 

### Arguments

`lineNumber` - To specify the line number to be customized

`fullLine` - To specify, whether to highlight Full Line. 

`brush` - To specify the Brush of Background customization. 

{% highlight C# %}

// Set the background to a specified Line.

this.editControl1.SetLineBackground(LineNumber, true, Brushes.Red);

{% endhighlight %}

![](Line-Background-Customization_images/SetLineBackground.png)

## Reset Line Background customization

The `ResetLineBackground` function helps to reset the Background Color for customized lines.

### Method

`ResetLineBackground(lineNumber)` - Helps to reset the Background customization of Line. 

`lineNumber` - To specify the line number to be reset the applied customization. 

{% highlight C# %}

// Reset the background to a specified Line.

this.editControl1.ResetLineBackground(LineNumber);

{% endhighlight %}

## Line Background customization with better performance 

`OnBeforeLineRender` event will be raised just before loading the LineItem and its Background can be customized using `OnBeforeLineRender`. We recommend this, when EditControl is loaded with huge data. 

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

![](Line-Background-Customization_images/OnBeforeEvent.png)
