---
layout: post
title: History-Support
description: history support
platform: wpf
control: AutoComplete
documentation: ug
---

# History Support

History support in AutoComplete means, reusage of the items which are already used in the AutoComplete textbox. AutoComplete allows you to enable this history support by setting the value of the IsHistory property to True. AutoComplete guides you to select an item from the list of items which are added to the history, by using the drop-down button to open the drop-down list.

## Using History Support in an Application 

Items can be added to the history using the AddToHistory(String str) and AddToHistory(Object obj) methods, only if that items are present in the data source used with the AutoComplete. Also it supports to save the history while closing the application and to load the history while opening the application using the SaveHistory() and LoadHistory() methods. 

The following mentioned code example can be used to attain these functionalities.
{% highlight c# %}




AutoComplete autoComplete1 = new AutoComplete();

autoComplete1.Loaded += new RoutedEventHandler

(autoComplete1_Loaded);



void autoComplete1_Loaded(object sender, RoutedEventArgs e)

        {

            if (autoComplete1!= null)

                autoComplete1.LoadHistory();

        }



autoComplete1.SelectionChanged +=

   new SelectionChangedEventHandler(autoComplete1_SelectionChanged);





private void autoComplete1_SelectionChanged(object sender, 

                                             SelectionChangedEventArgs e)

        {

     autoComplete1.AddHistory(autoComplete1.SelectedItem);

     autoComplete1.SaveHistory();

        }
{% endhighlight %}


## Tables for properties, methods, and events

### Properties

_Property Table for History support_

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
IsHistory</td><td>
Gets or sets the value of IsHistory of the AutoComplete.</td><td>
DependencyProperty</td><td>
bool(true)</td><td>
</td></tr>
</table>


### Methods

_MethodsTable for History_

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Type </th><th>
Return Type </th><th>
Reference links </th></tr>
<tr>
<td>
AddHistory()</td><td>
It should be called to add an item to the history.It can be called at any time.This method will add an input string to the history list if IsHistoryEnabled property is set as True and these items will only be displayed in the History list which can be opened using the drop-down button. </td><td>
(String str)The input string must be there in the linked Custom Source.</td><td>
NA.</td><td>
Void</td><td>
</td></tr>
<tr>
<td>
AddHistory()</td><td>
It should be called to add the item to history.It can be called at any time.This method will add an input object to the history list if IsHistoryEnabled property is set as Ture and these items will only be displayed in the History list which can be opened using the drop-down button. </td><td>
(Object obj)The input object must be there in the linked Custom Source.</td><td>
NA.</td><td>
Void</td><td>
</td></tr>
<tr>
<td>
SaveHistory()</td><td>
It should be called if you want to save the history before closing the application.It can be called while closing the application.This method will save the History list in an isolated storage. </td><td>
</td><td>
NA</td><td>
Void</td><td>
</td></tr>
<tr>
<td>
LoadHistory()</td><td>
It should be called if you want to load the history while loading the application which is already saved.It can be called while loading the application.This method will load the history list from an isolated storage to be used in the application.</td><td>
</td><td>
NA</td><td>
Void</td><td>
</td></tr>
<tr>
<td>
ClearAllHistory()</td><td>
This should be called if you want to clear all the saved history.It can be called at any time.This method will clear the entire history list loaded from an isolated storage.</td><td>
</td><td>
NA</td><td>
Void</td><td>
</td></tr>
</table>


## Sample Link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo

