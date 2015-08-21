---
layout: post
title: Support-for-All-Level-Type-Member
description: support for "all" level type member 
platform: wpf
control: OLAP Grid
documentation: ug
---

# Support for "All" Level Type Member 

This feature enables you to display the “All” level type member across the rows and columns in the OlapGrid. This member behaves as parent to other members in its hierarchy by controlling their visibility through expander. 

 Properties

_Property Table_

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<td>
ShowLevelTypeAll </td><td>
Specifies whether members with level type as All has to be displayed.  </td><td>
Normal </td><td>
Boolean </td><td>
NA </td></tr>
</table>


## Displaying "All" Level Type Member

To display the “All” level type member, set the _ShowLevelTypeAll_ property to _true_. By default this is set to _false_.  

  {% highlight c# %}

    

OlapDataManager DataManager = new OlapDataManager() { ShowLevelTypeAll = true};

    {% endhighlight %}





  {% highlight vbnet %}

    



OlapDataManager DataManager = New OlapDataManager() { ShowLevelTypeAll = True }

    {% endhighlight %}







![](Support-for-All-Level-Type-Member_images/Support-for-All-Level-Type-Member_img1.png)


_Member with Level type “All” is displayed._

## Sample Link

A demo of this feature is available in the following location:

## Windows XP

_..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Defining Reports\Reports-in-code Demo_

## Windows 7/Vista

_C:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\x.x.x.x\BI\ WPF\OlapGrid.WPF\Samples\Defining Reports\Reports-in-code Demo_

