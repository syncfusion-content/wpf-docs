---
layout: post
title: Custom Formula | SfSpreadsheet | WPF | Syncfusion
description: custom formula
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Custom Formula

SfSpreadsheet allows you to add custom formulas into its function library. You can add the custom formula into the SfSpreadsheet by using the [AddFunction](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic457.html) method of [FomulaEngine](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic450.html),

{% highlight c# %}

    spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;

    void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
    {
        foreach (var grid in args.GridCollection)
          AddCustomFormula(grid); 
    }

    private void AddCustomFormula(SpreadsheetGrid grid)
    {
       // Add a formula named Length and Find to the Library.
       grid.FormulaEngine.AddFunction("Find", new LibraryFunction(FindMethod));
       grid.FormulaEngine.AddFunction("Length",new LibraryFunction(LengthMethod));
    }

    //Implementation of formulas
    
    public string FindMethod(string args)
    {
      if (args.Contains("text"))
        return "text";
      else
        return "Error";
    }

    public string LengthMethod(string range)
    {
       return range.Length.ToString();
    }

{% endhighlight %}
