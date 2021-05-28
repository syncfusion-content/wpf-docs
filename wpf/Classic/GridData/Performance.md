---
layout: post
title: Performance in WPF Wizard Control control | Syncfusion
description: Learn here all about Performance support in Syncfusion WPF GridDataControl (Classic) control and more.
platform: wpf
control: GridData (Classic)
documentation: ug
---
# Performance in WPF GridDataControl (Classic)

Essential Grid has a high performance standard, where you can make the grid to work with large amounts of data with few property settings, without a performance hit. It provides complete support for Virtual Mode, where the data is loaded only on demand and thus saves the memory consumption and provides quick response. It also handles very high frequency updates and refresh scenarios. The following topic discusses this:

## High Frequency Updates

This section illustrates an example that let you know how to handle high frequency updates using grid while keeping the CPU usage at a minimum level. It uses a simple data source with few double-valued columns. It changes random cell values and also does record insertions and removals, using a timer event.

The following code illustrates changing of random cell values:

{% highlight c# %}

private void timer_Tick(object sender, EventArgs e)

{

....................

for (int i = 0; i < numberOfChangesEachTimer; i++)

	{

		int recNum = rand.Next(table.Rows.Count - 1);

		int col = rand.Next(table.Columns.Count - 1) + 1;

		DataRow drow = table.Rows[recNum];

		if (drow.RowState != DataRowState.Deleted && !(drow[col] is DBNull))

		{

			double value = (int)(Convert.ToDouble(drow[col]) * (rand.Next(50) / 100.0f + 0.8));

			//Console.WriteLine("{0}, {1}: {2}", recNum, col, value);

			drow[col] = value;

		}

   }

}

{% endhighlight  %}

The following code illustrates record insertions and removals:

{% highlight c# %}

private void timer_Tick(object sender, EventArgs e)

{

....................

if (toggleInsertRemove > 0 && (timerCount % insertRemoveModulus) == 0)

	{

		icount = ++icount % (toggleInsertRemove * 2);

		shouldInsert = icount < toggleInsertRemove;

		if (shouldInsert)

		{

			for (int ri = 0; ri < insertRemoveCount; ri++)

			{

				int recNum = rand.Next(Math.Min(30, table.Rows.Count));

				double next = rand.Next(100);

				object[] values = new object[table.Columns.Count];

				values[0] = "H" + ti.ToString("00000");

				for (int n = 1; n < table.Columns.Count; n++)

					values[n] = next + n;

				DataRow drow = table.NewRow();

				drow.ItemArray = values;

				table.Rows.InsertAt(drow, recNum);

				ti++;

			}

		}

		else

		{

			for (int ri = 0; ri < insertRemoveCount; ri++)

			{

				int recNum = 5; //rand.Next(m_set.Count - 1);

				int rowNum = recNum + 1;

				// Underlying data structure (this could be a data table or whatever structure

				// you use behind a virtual grid).

				if (table.Rows.Count > 10)

					table.Rows.RemoveAt(recNum);

			}

		}

	}

}

{% endhighlight  %}

N> For complete code of this example, refer the following browser sample: ...\My Documents\Syncfusion\EssentialStudio\<Version Number>\WPF\Grid.WPF\ Samples\3.5\WindowsSamples\Grid Data Control – Advanced\Trader Grid Test Demo

## PLINQ Support in GridDataControl

[PLINQ](https://docs.microsoft.com/en-us/dotnet/standard/parallel-programming/introduction-to-plinq) is the parallel implementation of the standard LINQ. GridDataControl uses a QueryableCollectionView that works on top of LINQ expressions for performing major operations such as Sorting, Filtering, Grouping and Summaries calculation. Since PLINQ works on top of LINQ expression trees, QueryableCollectionView now has a property UsePLINQ = true / false (this class implements _IParallelizable View_ interface) that would add a AsParallel() to change it into a Parallel Query. Sorting, Grouping and Summary operations would be automatically done in parallel when this property is set.

{% tabs %}

{% highlight xaml %}

<syncfusion:GridDataControl x:Name="grid"  

                AutoPopulateColumns="True"    

                AutoPopulateRelations="False"

                UsePLINQ="True"

				VisualStyle="Office14Silver">

</syncfusion:GridDataControl>

{% endhighlight  %}

{% highlight c# %}

this.gridDataControl1.UsePLINQ = true;

{% endhighlight  %}

{% endtabs %}

N> This only works for strongly-typed collections and not for legacy object models like DataTable.