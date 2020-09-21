---
layout: post
title: Events | SfRangeSlider | wpf | Syncfusion
description: This section provides details about all events and their arguments in Syncfusion WPF RangeSlider (SfRangeSlider). 
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Events in WPF RangeSlider(SfRangeSlider)

## How to trigger LabelLoaded event? 

The [LabelLoaded](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~LabelLoaded_EV.html) event is triggered when the slider label is created. The argument contains the label content.

`Content` - Used to gets or sets the content of the label.

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

{%endhighlight%}

{%highlight C#%}

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

{%endhighlight%}

{% endtabs %}

## How to trigger RangeChangedEvent?

The [RangeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~RangeChanged_EV.html) event is triggered when either `RangeStart` or `RangeEnd` values are changed. The argument contains the following information.

`NewEndValue` – Gets or sets the new end value of range slider.
`NewStartValue` – Gets or sets the new start value of range slider.
`OldStartValue` – Gets or sets the old start value of range slider.
`OldEndValue` – Gets or set the old end value of range slider.

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

{%endhighlight%}

{%highlight C#%}

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

{%endhighlight%}

{% endtabs %}

## How to trigger RangeStartChanged event?

The [RangeStartChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~RangeStartChanged_EV.html) event is triggered when `RangeStart` value is changed. The argument contains the following information.

`OldStartValue` – Gets or sets the old start value of range slider.
`NewStartValue` – Gets or sets the new start value of range slider.

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

{%endhighlight%}

{%highlight C#%}

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

{%endhighlight%}

{% endtabs %}

## How to trigger RangeEndChanged event?

The [RangeEndChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~RangeEndChanged_EV.html) event is triggered when `RangeEnd` value is changed. The argument contains the following information.

`OldEndValue` – Gets or sets the old end value of range slider.
`NewEndValue` – Gets or sets the new end value of range slider.

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

{%endhighlight%}

{%highlight C#%}

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

{%endhighlight%}

{% endtabs %}

