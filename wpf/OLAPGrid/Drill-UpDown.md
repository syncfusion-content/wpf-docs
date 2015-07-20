---
layout: post
title: Drill-UpDown
description: drill-up/down
platform: wpf
control: OLAP Grid
documentation: ug
---

# Drill-Up/Down

This is the basic feature of OlapGrid through which the amount of information can be limited. It allows you to drill down to access the detailed level of data, or roll up to see the summarized data using the expander’s present in the grid. The expander here refers to the plus/minus sign present in the grid followed by a member.

{ ![](Drill-UpDown_images/Drill-UpDown_img1.png) | markdownify }
{:.image }
    	-    Drilldown to view data in detail

{ ![](Drill-UpDown_images/Drill-UpDown_img2.png) | markdownify }
{:.image }
-    Collapse to view the summarized data

The expanders can be made hidden by setting the ShowExpanders property of OlapReport to false.

[C#]



// Hide Expanders

this.OlapGrid1.OlapDataManager.CurrentReport.ShowExpanders = false;



[VB]



' Hide Expanders

Me.OlapGrid1.OlapDataManager.CurrentReport.ShowExpanders = False



