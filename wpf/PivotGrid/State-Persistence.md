---
layout: post
title: State Persistence
description: State Persistence
platform: wpf
control: PivotGrid
documentation: ug
---

## State Persistence

This feature enables the user to maintain the collapsed or expanded state in the PivotGrid when pivot schema is changed.

#### Use Case Scenarios

The user can maintain collapsed or expanded states and save/load these settings dynamically in the PivotGrid control. 

The following image shows state persistence in the PivotGrid control:

![D:/Diana/2012/2012_Vol 1/Mkt Content 2012/StatePersistenceDemo2.png](Features_images/Features_img26.png)



#### Properties

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td><td>
{{ '**Reference links**' | markdownify }}</td></tr>
<tr>
<td>
StatePersistenceEnabled</td><td>
Gets or sets a value indicating whether to maintain/show collapsed cells when pivot schema getting changed</td><td>
Dependency </td><td>
Boolean</td><td>
</td></tr>
</table>


#### Sample Link

The user can find a sample in the following location:

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\PivotAnalysis.Wpf\Samples\Appearance\State Persistence Demo

#### Adding State Persistence to an Application 

The user can enable or disable the state persistence by using the following code snippets in an application:

{% highlight C# %}  

[C#]

pivotGrid1.StatePersistenceEnabled = true;

{% endhighlight %} 

{% highlight vbnet %} 

[VB]

pivotGrid1.StatePersistenceEnabled = true

{% endhighlight %} 


