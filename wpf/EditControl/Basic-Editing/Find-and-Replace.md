---
layout: post
title: Find and Replace support of the Edit Control for WPF
description: Find and Replace support of the Edit Control for WPF
platform: wpf
control: Edit Control
documentation: ug
---

## Find and Replace

Essential Edit WPF is now enhanced with **Find** **and** **Replace** feature, which enables users to search a text and replace it with an alternate text.  Various options available in text search are: 

* Match case
* Match whole word
* Search hidden Text   
* Substring
* Prefix 


To enable/disable **Find** **and** **Replace** feature, use **ShowFindAndReplace** property in EditControl.
The following code can be used to set the **ShowFindAndReplace** property of **EditControl** **class**.

{% highlight xaml %}
<sfedit:EditControl x:Name="editControl" DocumentSource="C:\Content.txt" FontSize="13" EnableOutlining="False" ShowFindAndReplace="True"/>



{% endhighlight %}

{% highlight c# %}

editControl.ShowFindAndReplace = true;


{% endhighlight %}

The following image displays Find and Replace Window

![](Find-and-Replace_images/Find-and-Replace_img1.jpeg)


The **Find** **and** **Replace** dialog provides the basic search functionality as mentioned below. 

* Quick Find
* Quick Replace
* Find Symbol

**Quick** **Find** (**Ctrl** **+** **F**)—Quick Find tab enables to search a text in an open document or a selection for a string. 

**Find** **Symbol**—Find Symbol tab enables to search for words and the position of the word in the document. 

**Quick** **Replace** (**Ctrl** **+** **H**)—Quick Replace tab enables to find a text and replace it with an alternative text.

**Quick** **Find**

Quick Find tab enables users to search all the occurrences of a text in an open document or a selection. Select Quick Find in Find and Replace dialog or use **Ctrl**+**F** to enable Quick Find. 

The following image displays Quick Find Tab

![](Find-and-Replace_images/Find-and-Replace_img2.jpeg)


**Find** **what**—enter the search text in Find what field to search the text in the document. 

**Look** **in**—you can choose the search area (the whole document or a selection) in this field. 

N> Select an area in the document before opening Find and Replace dialog,Selection is automatically selected in this field.This can also be selected in the dropdown box.

The following image displays look in field in Find and Replace Window 

![](Find-and-Replace_images/Find-and-Replace_img4.jpeg)


**Find** **Options**—Find options are placed under collapsible GroupBox control to have a compact view of the **Find** **and** **Replace** window.

Find and Replace window facilitates you to search the text based on the following options.

* **Match** **case**— performs a case-sensitive search.
* **Match** **whole** **word**—Searches for the text specified with in a word boundary.
* **Search** **up**—searches in lines above the current cursor location.
* **Search** **hidden** **text**—Text from the collapsed region will also be included in search area.

The following image displays Find Options Collapsed window.

![](Find-and-Replace_images/Find-and-Replace_img5.jpeg)


Click the **Find** **Next** or **Enter** to search the text in document. The Find Next Button will be enabled only when the search text is entered in **Find** **what** field.

The following image displays EditControl Sample Window

![](Find-and-Replace_images/Find-and-Replace_img6.jpeg)


**Find** **Symbol**

Find symbol tab in **Find** **and** **Replace** window facilitates the users to find all the occurrences of the specified text in the entire Edit Control’s text. **Find** **Symbol** tab can be enabled by selecting the drop down option in the Quick Find tab. 

The following image displays Find and Replace Window.

![](Find-and-Replace_images/Find-and-Replace_img7.jpeg)


The following image displays Find Symbol Tab in Find and Replace Window

![](Find-and-Replace_images/Find-and-Replace_img8.jpeg)


**Find** **Symbol** **tab** supports the following search options to refine the search results.

* **Whole** **word**—Searches the text when the whole word matches. 
* **Prefix**—Locates the line, when the line starts with the search text.
* **Substring**— Locate the line, when the line contains the search text.
* **Match** **case**— Performs a case sensitive search. 

Find Symbol Results (**Shift** **+** **F12**): The Whole word, Prefix, Substring options are radio buttons and Sub string will be selected in default. 

Find symbol results tab lists all the occurrences of the search text with additional details of line number and position of the text in the line. Double clicking on any item listed in the Find symbol will navigate the cursor to the result selected.

The following image displays EditControl Sample Window

![](Find-and-Replace_images/Find-and-Replace_img9.jpeg)


Click the **Find** **All** or **Enter** to search the text in document

N> Find Symbol results tab is a dockable so that it can be hidden,pinned or closed as necessary.

The following image displays Find Symbol Results

![](Find-and-Replace_images/Find-and-Replace_img11.jpeg)



The following image displays Find Symbol Results tab in Hidden State Window.

![](Find-and-Replace_images/Find-and-Replace_img12.jpeg)


**Quick** **Replace**

Quick replace tab in Find and replace window enables the users to search a text and replace it with an alternate text. Quick replace tab can be enabled by clicking on the Quick Replace button at the top of the Find and Replace window or by using **Ctrl** **+** **H** key from EditControl.

The following image shows Quick Replace Tab in Find and Replace Window 




![](Find-and-Replace_images/Find-and-Replace_img13.jpeg)


1. Quick Replace tab is similar to that of Quick Find except for **Replace** **With** field.
2. Replace with – Enter the alternative text to be replaced in this field.
3. Quick replace supports two functionalities
* **Replace**—Replaces the immediate occurrence of text specified in **Find** **what** with text specified in Replace with field.
* **Replaces**—Replaces all the occurrences of the text specified in **Find** **what** with the text specified in the Replace with field. 

