---
layout: post
title: Performance Improvement along Virtualized Binding
description: Performance Improvement along Virtualized Binding
platform: wpf
control: PivotGrid
documentation: ug
---

# Performance Improvement along Virtualized Binding

This feature provides high performance for a large set of records. This feature also helps load the data in the PivotGrid control on demand.

## Use Case Scenarios

Users can view the output in a few seconds for a large number of records that have been bound with the PivotGrid control. 

### Properties

Properties Table

<table>
<tr>
<th>
 {{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }} </th><th>
 {{ '**Type**' | markdownify }}</th><th>
 {{ '**Data Type**' | markdownify }}</th><th>
 {{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<td>
UseIndexedEngine</td><td>
Gets or sets whether an optimized algorithm that relies on indexing the raw data should be used to compute the pivot information.</td><td>
CLR</td><td>
Boolean</td><td>
</td></tr>
<tr>
<td>
EnableOnDemandCalculations</td><td>
Gets or sets whether the calculations are postponed until the value is requested through the Indexer in the PivotEngine. The default value is false.</td><td>
CLR</td><td>
Boolean</td><td>
-</td></tr>
</table>


### Sample Link

To launch the sample for this feature:

1. Open the Syncfusion Dashboard.
2. Click WPF platform and then Run Samples.
3. Select PivotAnalysis product and navigate to Performance > On-demand Loading Demo.



### Adding a virtualized binding feature in Pivot Grid control 

1. Set the value as “true” for the following properties in Pivot Grid’s PivotEngine class:
1. UseIndexedEngine
2. EnableOnDemandCalculations
2. Update the PivotEngine values on demand using recursive calls.

The following code sample explains how to achieve on-demand loading support in PivotGrid control.

{% highlight C# %}  


DateTime _startIndex = DateTime.Now;

public MainPage()

        {

            InitializeComponent();



            pivotGrid.PivotEngine.EnableOnDemandCalculations =

                    pivotGrid.PivotEngine.UseIndexedEngine = true;



                pivotGrid.PivotEngine.GetValue = ItemObjectLookup;



               ObservableCollection<ItemObject> itemsSourceObject =

                    (AssociatedObject.DataContext as ViewModel.ViewModel).ItemObjectCollection;



                pivotGrid.PivotEngine.PivotSchemaChanged +=

                    PivotEngine_PivotSchemaChanged;



                pivotGrid.ItemSource = itemsSourceObject;

        }



private void PivotEngine_PivotSchemaChanged(object sender, PivotSchemaChangedArgs e)

        {

            _startIndex = DateTime.Now;

            pivotGrid.Dispatcher.BeginInvoke(DispatcherPriority.SystemIdle, new Action(() =>

                {

                    if (!pivotGrid.IgnoreRefesh)

                    {

                        if ((_scrollViewer.Content as TextBlock) != null)

                            (_scrollViewer.Content as TextBlock).Text = string.Empty;



                        CheckTime(_startIndex, "Initial part done in");

                        ContinueLoadingAsynchonolously(

                            pivotGrid.PivotEngine.IndexEngine, _startIndex);

                    }

                }));

        }



        private void ContinueLoadingAsynchonolously(IndexEngine engine, DateTime startIndex)

        {

            pivotGrid.Dispatcher.BeginInvoke(new Action(() =>

                {

                    if (engine != null && engine.HighRowLevel < engine.RowCount - 1)

                    {

                        int cutOff = Math.Min(engine.HighRowLevel + 800, engine.RowCount - 1);



                        object o = engine[cutOff, 0]; ////Gets 800 more rows from the pivot engine (on demand calculation).



                        if ((_scrollViewer.Content as TextBlock) != null)

                        {

                            (_scrollViewer.Content as TextBlock).Text +=

                                string.Format("\n{0}/{1}", engine.HighRowLevel, engine.RowCount - 1);

                            ContinueLoadingAsynchonolously(engine, startIndex); //Recursive call to update the rows of the PivotEngine until they reach high row level.

                        }

                    }

                    else

                    {

                        CheckTime(startIndex, "Load Completed");

                    }

                }), DispatcherPriority.SystemIdle);

        }



        private void CheckTime(DateTime start, string label)

        {

            if (_textBlock != null)

                _textBlock.Text += string.Format("\n{0} {1:0.0000} seconds.", label,

                                                 DateTime.Now.Subtract(start).TotalSeconds);

        }





        public IComparable ItemObjectLookup(object o, string name)

        {

            IComparable c = null;

            var io = o as ItemObject;

            if (io != null)

            {

                switch (name)

                {

                    case "Date":

                        c = io.Date;

                        break;

                    case "Client":

                        c = io.Client;

                        break;

                    case "Campaign":

                        c = io.Campaign;

                        break;

                    case "Color":

                        c = io.Color;

                        break;

                    case "Shape":

                        c = io.Shape;

                        break;

                    case "Price":

                        c = io.Price;

                        break;

                    case "Spend":

                        c = io.Spend;

                        break;

                    case "ColH":

                        c = io.ColH;

                        break;

                    case "ColI":

                        c = io.ColI;

                        break;

                    case "ColJ":

                        c = io.ColJ;

                        break;

                }

            }

            return c;

        } 
		
{% endhighlight %} 



