---
layout: post
title: Events in SfRangeSlider for WPF | Syncfusion®
description: Learn about triggering events and handling their arguments in the Syncfusion® WPF RangeSlider (SfRangeSlider).
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Events in WPF RangeSlider (SfRangeSlider)

## How to Trigger the `LabelLoaded` Event

The [LabelLoaded](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRangeSlider.html#Syncfusion_Windows_Controls_Input_SfRangeSlider_LabelLoaded) event is triggered when the slider label is created. The event arguments contain the label content as follows:

`Content` - Used to get or set the content of the label.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    LabelLoaded="SfRangeSlider_LabelLoaded"
                    Maximum="200"
                    Minimum="100"
                    ShowValueLabels="True"
                    TickFrequency="20"
                    TickPlacement="Outside" />

{% endhighlight %}

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 200,
                Minimum = 100,
                Value = 140,
                ShowValueLabels = true,
                TickFrequency = 20,
                TickPlacement = Syncfusion.Windows.Controls.Input.TickPlacement.Outside
            };
            rangeSlider.LabelLoaded += SfRangeSlider_LabelLoaded;
            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;
        }

        private void SfRangeSlider_LabelLoaded(object sender, LabelLoadedEventArgs e)
        {
            e.Content = e.Content + "%";
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger the `RangeChanged` Event

The [RangeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRangeSlider.html#Syncfusion_Windows_Controls_Input_SfRangeSlider_RangeChanged) event is triggered when either `RangeStart` or `RangeEnd` values change. The event arguments contain the following information:

- `NewEndValue` – Gets or sets the new end value of the range slider.
- `NewStartValue` – Gets or sets the new start value of the range slider.
- `OldStartValue` – Gets or sets the old start value of the range slider.
- `OldEndValue` – Gets or sets the old end value of the range slider.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    RangeChanged="SfRangeSlider_RangeChanged"
                    Maximum="100"
                    Minimum="0"
                    ShowRange="True"
                    RangeStart="30"
                    RangeEnd="60"/>

{% endhighlight %}

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                Value = 140,
                ShowRange = true,
                RangeStart = 30,
                RangeEnd = 60
            };

            rangeSlider.RangeChanged += SfRangeSlider_RangeChanged;
            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;
        }

        private void SfRangeSlider_RangeChanged(object sender, RangeChangedEventArgs e)
        {
            var newStartValue = e.NewStartValue;
            var newEndValue = e.NewEndValue;
            var oldStartValue = e.OldStartValue;
            var oldEndValue = e.OldEndValue;
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger the `RangeStartChanged` Event

The [RangeStartChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRangeSlider.html#Syncfusion_Windows_Controls_Input_SfRangeSlider_RangeStartChanged) event is triggered when the `RangeStart` value changes. The event arguments contain the following information:

- `OldStartValue` – Gets or sets the old start value of the range slider.
- `NewStartValue` – Gets or sets the new start value of the range slider.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    RangeStartChanged="SfRangeSlider_RangeStartChanged"
                    Maximum="100"
                    Minimum="0"
                    ShowRange="True"
                    RangeStart="30"
                    RangeEnd="60"/>

{% endhighlight %}

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                Value = 140,
                ShowRange = true,
                RangeStart = 30,
                RangeEnd = 60
            };

            rangeSlider.RangeStartChanged += SfRangeSlider_RangeStartChanged;
            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;
        }

        private void SfRangeSlider_RangeStartChanged(object sender, RangeStartChagedEventArgs e)
        {
            var newStartValue = e.NewStartValue;
            var oldStartValue = e.OldStartValue;
        }

{% endhighlight %}

{% endtabs %}

## How to Trigger the `RangeEndChanged` Event

The [RangeEndChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRangeSlider.html#Syncfusion_Windows_Controls_Input_SfRangeSlider_RangeEndChanged) event is triggered when the `RangeEnd` value changes. The event arguments contain the following information:

- `OldEndValue` – Gets or sets the old end value of the range slider.
- `NewEndValue` – Gets or sets the new end value of the range slider.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    RangeEndChanged="SfRangeSlider_RangeEndChanged"
                    Maximum="100"
                    Minimum="0"
                    ShowRange="True"
                    RangeStart="30"
                    RangeEnd="60"/>

{% endhighlight %}

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                Value = 140,
                ShowRange = true,
                RangeStart = 30,
                RangeEnd = 60
            };

            rangeSlider.RangeEndChanged += SfRangeSlider_RangeEndChanged;
            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;
        }

        private void SfRangeSlider_RangeEndChanged(object sender, RangeEndChagedEventArgs e)
        {
            var newEndValue = e.NewEndValue;
            var oldEndValue = e.OldEndValue;
        }

{% endhighlight %}

{% endtabs %}

