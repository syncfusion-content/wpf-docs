---
layout: post
title: Member Properties| OlapGrid | Wpf | Syncfusion
description: member properties
platform: wpf
control: OlapGrid
documentation: ug
---

# Member Properties

OlapGrid allows binding of members along with their properties. Member properties cover the basic information about each member in each tuple. This basic information includes the member name, parent level, number of children and so on. Member properties are available for all members at a given level. In-order to display member properties along with the dimension member, OlapReport requires member properties to be defined in the concerned dimension element. Also the OlapGrid layout should be set to **"ExcelLikeLayoutWithMemberProperties"**.

{% tabs %}
 
{% highlight c# %}
     
private OlapReport ReportWithMemberProperties()
{
    OlapReport olapReport = new OlapReport();
    // Specifying the current cube name
    olapReport.CurrentCubeName = "Adventure Works";
    MeasureElements measureElementColumn = new MeasureElements();
    // Specifying the Name for the Measure Element
    measureElementColumn.Elements.Add(new MeasureElement { Name = "Sales Amount Quota" });
    DimensionElement dimensionElementRow = new DimensionElement();
    // Specifying the Dimension Name
    dimensionElementRow.Name = "Employee";
    // Specifying the Hierarchy and level name for the Dimension Element
    dimensionElementRow.AddLevel("Employees", "Employee Level 02");
    dimensionElementRow.Hierarchy.LevelElements["Employee Level 02"].IncludeAvailableMembers = true;
    // Adding the Member properties to the Dimension Element
    dimensionElementRow.MemberProperties.Add(new MemberProperty("Title", "[Employee].[Employees].[Title]"));
    dimensionElementRow.MemberProperties.Add(new MemberProperty("Phone", "[Employee].[Employees].[Phone]"));
    dimensionElementRow.MemberProperties.Add(new MemberProperty("Email Address", "[Employee].[Employees].[Email Address]"));
    // Adding Row Members
    olapReport.SeriesElements.Add(dimensionElementRow);
    ///Adding Column Members
    olapReport.CategoricalElements.Add(measureElementColumn);
    return olapReport;
}
   
{% endhighlight %}

{% highlight vbnet %}
    
    
''' <summary>
''' OlapReport with KPI Elements
''' </summary>
''' <returns></returns>
Private Function ReportWithMemberProperties() As OlapReport
    Dim olapReport As New OlapReport()
    ' Selecting the Cube
    olapReport.CurrentCubeName = "Adventure Works"
    Dim measureElements As New MeasureElements()
    measureElements.Add(New MeasureElement With {.Name = " Sales Amount Quota"})
    olapReport.SeriesElements.Add(measureElements)
    Dim dimensionElementRow As New DimensionElement()
    ' Specifying the Name for Row Dimension Element
    dimensionElementRow.Name = "Employee"
    ' Specifying the Level element
    dimensionElementRow.AddLevel("Employees", "Employee Level 02")
    dimensionElementRow.Hierarchy.LevelElements["Employee Level 02"].IncludeAvailableMembers = true;
    ' Adding the Member properties to the Dimension Element
    dimensionElementRow.MemberProperties.Add(new MemberProperty("Title", "[Employee].[Employees].[Title]"));
    dimensionElementRow.MemberProperties.Add(new MemberProperty("Phone", "[Employee].[Employees].[Phone]"));
    dimensionElementRow.MemberProperties.Add(new MemberProperty("Email Address", "[Employee].[Employees].[Email Address]"));
    ' Adding Row Elements
    olapReport.SeriesElements.Add(dimensionElementRow)
    ' Adding Column Elements
    olapReport.CategoricalElements.Add(measureElements)
    Return olapReport
End Function

{% endhighlight %}

{% endtabs %}

![](Member-Properties_images/Member-Properties_img1.png)

To display member properties via header tooltip, the following property of OlapGrid should be set to true.

{% tabs %}
  
{% highlight c# %}

// To Display Member Properties in ToolTip
this.OlapGrid1.ShowMemberPropertiesToolTip = true;

{% endhighlight %}

{% highlight vbnet %}

' To Display Member Properties in ToolTip
Me.OlapGrid1.ShowMemberPropertiesToolTip = True

{% endhighlight %}

{% endtabs %}

![](Member-Properties_images/Member-Properties_img2.png)

A sample demo is available at the following location:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapGrid.WPF\Samples\Product Showcase\Member Properties 