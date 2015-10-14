---
layout: post
title: Creating an Excel Document | Spreadsheet | wpf | Syncfusion
description: creating an excel document 
platform: wpf
control: Spreadsheet
documentation: ug
---

# Creating an Excel Document 

When you add the Spreadsheet control to the application, it will be loaded with a blank workbook. You can save this as an Excel document. You can also create new workbooks if required.

To create a new workbook, call the New method. New workbook will be created with three worksheets by default. The following code illustrates this:

{% tabs %}

{% highlight c# %}

spreadControl.New();

{% endhighlight %}

{% highlight vbnet %}
 
 spreadControl.New()
 
{% endhighlight %}

{% endtabs %}

You can also specify the number of worksheet you want to add in workbook by passing the sheet count to the New method. The following code illustrates this:

{% tabs %}

{% highlight c# %}

spreadControl.New(3);

{% endhighlight %}

{% highlight vbnet %}

 
spreadControl.New(3)

{% endhighlight %}

{% endtabs %}

### Using Command

You can also use the NewCommand to create the Excel document. By default when you execute the NewCommand it will create the workbook with three worksheets and you can also specify the number of worksheet you want to add in workbook by passing the sheet count as Command parameter. 

The following code illustrates how to bind the NewCommand__to a button: 

{% highlight xaml %}

<Button Command="{Binding Path=NewCommand}"/>

{% endhighlight %}