---
layout: post
title: Bind Commands With Chart Or Chart Area | wpf | Syncfusion
description: Learn here all about Bind Commands With Chart Or Chart Area support in Syncfusion WPF Chart (Classic) control, its elements and more details.
platform: wpf
control: Chart (Classic)
documentation: ug
---

## Bind Commands With Chart Or Chart Area

Custom RoutedUICommands can be bound to the Chart or ChartArea just like any other control and InputBindings such as KeyboardGestures and MouseGestures can be set for those commands. Note that for KeyboardGestures and MouseGestures to work, Chart or ChartArea should be in focus. In the following sample, a custom command is created to change the series type of all the ChartSeries in the ChartArea to ChartType.Bar.

{% tabs %}
{% highlight xaml %}

<Window.Resources>

    <XmlDataProvider x:Key="myXmlData">

        <x:XData>

            <Products xmlns="">

                <Product X="1" Series1Y="3" Series1Y1="6"  Series2Y="4" Series2Y1="6" Series3Y="2" Series3Y1="2"/>

                <Product X="2" Series1Y="2" Series1Y1="4" Series2Y="3" Series2Y1="5" Series3Y="2.5" Series3Y1="6"/>

                <Product X="3" Series1Y="3" Series1Y1="6" Series2Y="3.5" Series2Y1="5" Series3Y="1" Series3Y1="4"/>

                <Product X="4" Series1Y="2" Series1Y1="7" Series2Y="1" Series2Y1="6" Series3Y="4" Series3Y1="6"/>

                <Product X="5" Series1Y="1" Series1Y1="3" Series2Y="3.5" Series2Y1="1" Series3Y="3" Series3Y1="8"/>

            </Products>

        </x:XData>

    </XmlDataProvider>

</Window.Resources>



<Grid>

    <sfchart:Chart Name="Chart1">

        <sfchart:ChartArea GridBackground="White">

            <sfchart:ChartSeries Name="Series11" Type= "Column"

            DataSource="{Binding Source={StaticResource myXmlData}, XPath=Products/Product}"

            BindingPathX="X" BindingPathsY="Series1Y, Series1Y1" >

            </sfchart:ChartSeries>

        </sfchart:ChartArea>

    </sfchart:Chart>

</Grid>

{% endhighlight  %}
{% highlight c# %}

public partial class Window1 : Window

{

    public Window1()

    {

        InitializeComponent();

        CommandBinding commandbinding = new

        CommandBinding(CustomCommand.ChangeSeriesType, OnChangeSeriesTypeExecute, OnChangeSeriesTypeCanExecute);

        CommandManager.RegisterClassCommandBinding(typeof(ChartArea), commandbinding);

        Chart1.Areas[0].Focusable = true;

    }



    private static void OnChangeSeriesTypeExecute(object target, ExecutedRoutedEventArgs args)

    {

        ChartArea area = (ChartArea)target;

        foreach (ChartSeries series in area.Series)

        {

            series.Type = ChartTypes.Bar;

        }

    }



    private static void OnChangeSeriesTypeCanExecute(object target, CanExecuteRoutedEventArgs args)

    {

        ChartArea area = (ChartArea)target;

        if (area != null)

        {

            if (area.Series.Count > 0)

            {

                args.CanExecute = true;

            }

            else

            {

                args.CanExecute = false;

            }

        }

        else

        {

            args.CanExecute = false;

        }

    }

}

public class CustomCommand

{

    private readonly static RoutedUICommand ch_type = new RoutedUICommand("ChangeSeriesType", "ChangeSeriesType", typeof(CustomCommand));

    public static RoutedUICommand ChangeSeriesType

    {

        get

        {

            ch_type.InputGestures.Add(new KeyGesture(Key.T, ModifierKeys.Control));

            return ch_type;

        }

    }

}

{% endhighlight  %}
{% endtabs %}