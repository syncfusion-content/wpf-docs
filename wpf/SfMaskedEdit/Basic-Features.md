---
layout: post
title: Basic-Features
description: basic features
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# Basic Features

## Masking the input

To mask the input, set the MaskType and Mask property as follows:

{% highlight xml %}


<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000"  HorizontalAlignment="Left"  TextWrapping="Wrap"  VerticalAlignment="Top" Width="255" Height="46"/>
{% endhighlight %}


{% highlight C# %}



   SfMaskedEdit maskededit = new SfMaskedEdit();

   maskededit.MaskType=MaskType.Simple;

   maskedEdit.Mask=”00/00/0000”;
{% endhighlight %}


This mask expression allows only numeric inputs in the places of 0.

## Setting Value

Set the Value property as follows:


{% highlight xml %}



<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000" Value="14/11/2014" HorizontalAlignment="Left"  TextWrapping="Wrap"  VerticalAlignment="Top" Width="255" Height="46"/>
{% endhighlight %}

{% highlight C# %}



   SfMaskedEdit maskededit = new SfMaskedEdit();

   maskededit.MaskType=MaskType.Simple;

   maskedEdit.Mask=”00/00/0000”;

   maskedEdit.Value=”14/11/2014”;
{% endhighlight %}
## Setting Prompt Char

### Set the PromptChar property as follows:


{% highlight xml %}




<syncfusion:SfMaskedEdit  MaskType="Simple" Mask="00/00/0000" PromptChar="*"  HorizontalAlignment="Left"  TextWrapping="Wrap"  VerticalAlignment="Top" Width="255" Height="46"/>
{% endhighlight %}

{% highlight C# %}



   SfMaskedEdit maskededit = new SfMaskedEdit();

   maskededit.MaskType=MaskType.Simple;

   maskedEdit.Mask=”00/00/0000”;

   maskedEdit.PromptChar=”*”;
{% endhighlight %}


By default, the prompt character is ‘_’.

## Setting Watermark

### Set the Watermark property as follows:

{% highlight xml %}


  <syncfusion:SfMaskedEdit  MaskType="Simple" Mask="00/00/0000" Watermark="Mask"  HorizontalAlignment="Left"  TextWrapping="Wrap"  VerticalAlignment="Top" Width="255" Height="46"/>
{% endhighlight %}

{% highlight C# %}



   SfMaskedEdit maskededit = new SfMaskedEdit();

   maskededit.MaskType=MaskType.Simple;

   maskedEdit.Mask=”00/00/0000”;

   maskedEdit.Watermark=”Type here”;
{% endhighlight %}


