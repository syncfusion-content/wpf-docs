---
layout: post
title: Events | SfRangeSlider | wpf | Syncfusion
description: Events 
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Events

## How to trigger LabelLoaded event? 

The `LabelLoaded` event is triggered when the slider label is created. The argument contains the label content.

`Content` - Used to gets or sets the content of the label.

{%highlight xaml%}

<rangeSlider:SfRangeSlider Width="500"  Minimum="0" Maximum="100"  />

{%endhighlight%}

{%highlight C#%}

private void RangeSlider_LabelLoaded(object sender, LabelLoadedEventArgs e)
{
   e.Content = e.Content + "%";
}

{%endhighlight%}

## How to trigger RangeChangedEvent?

The `RangeChanged` event is triggered when either `RangeStart` or `RangeEnd` values are changed. The argument contains the following information.

`NewEndValue` – Gets or sets the new end value of range slider.
`NewStartValue` – Gets or sets the new start value of range slider.
`OldStartValue` – Gets or sets the old start value of range slider.
`OldEndValue` – Gets or set the old end value of range slider.

{%highlight C#%}

  private void RangeSlider_RangeChanged(object sender, RangeChangedEventArgs e)
  {
            var newStartValue = e.NewStartValue;
            var newEndValue = e.NewEndValue;
            var oldStartValue = e.OldStartValue;
            var oldEndValue = e.OldEndValue;
  }

{%endhighlight%}

## How to trigger RangeStartChanged event?

The `RangeStartChanged` event is triggered when `RangeStart` value is changed. The argument contains the following information.

`OldStartValue` – Gets or sets the old start value of range slider.
`NewStartValue` – Gets or sets the new start value of range slider.

{%highlight C#%}

private void RangeSlider_RangeStartChanged(object sender, RangeStartChagedEventArgs e)
{
     var newStartValue = e.NewStartValue;
     var oldStartValue = e.OldStartValue;
}

{%endhighlight%}

## How to trigger RangeEndChanged event?

The `RangeEndChanged` event is triggered when `RangeEnd` value is changed. The argument contains the following information.

`OldEndValue` – Gets or sets the old end value of range slider.
`NewEndValue` – Gets or sets the new end value of range slider.

{%highlight C#%}

private void RangeSlider_RangeEndChanged(object sender, RangeEndChagedEventArgs e)
{
            var newEndValue = e.NewEndValue;
            var oldEndValue = e.OldEndValue;
}

{%endhighlight%}

