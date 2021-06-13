---
layout: post
title: Editable Support in WPF ComboBox control | Syncfusion
description: Learn here all about Auto Complete Support in Syncfusion WPF ComboBox (ComboBoxAdv) control, its elements and more.
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# Auto Complete Support in WPF ComboBox (ComboBoxAdv)

Auto complete can be enabled by using the [AutoCompleteMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html#Syncfusion_Windows_Tools_Controls_ComboBoxAdv_AutoCompleteMode) property. It can be used for both single and multiple selections.

 There are three different [AutoCompleteModes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html#Syncfusion_Windows_Tools_Controls_ComboBoxAdv_AutoCompleteModes): 

•	Suggest: Displays suggestion in drop-down list.

•	Append: Appends the first suggestion to text.

•	None: No suggestion or Append is made.

## Auto Complete Modes

### Suggest

A list of probable matches will be suggested and displayed in the drop-down list by setting the AutoCompleteMode property as Suggest. Suggested items will contain or start with the search text.

{% tabs %}
{% highlight C# %}

<syncfusion:ComboBoxAdv AutoCompleteMode="Suggest"/>

{% endhighlight %}

{% highlight c# %}

ComboBoxAdv comboBox = new ComboBoxAdv();       
combobox.AutoCompleteMode = AutoCompleModes.Suggest;

{% endhighlight %}
{% endtabs %}

![WPF ComboBoxAdv AutoComplete Suggest Mode](ComboBoxAdv_images/WPF-ComboBoxAdv-AutoComplete-Suggest-Mode.png)

N> Suggest mode will be applicable only with ItemSource collection.

### Append

When entering the text, AutoComplete will guide you to complete the text by appending the suitable text from the data source. 

N> Append will be operated as IsTextSearchEanbled property

{% tabs %}
{% highlight C# %}

<syncfusion:ComboBoxAdv AutoCompleteMode="Append"/>

{% endhighlight %}

{% highlight c# %}

ComboBoxAdv comboBox = new ComboBoxAdv();       
combobox.AutoCompleteMode = AutoCompleModes.Append;

{% endhighlight %}
{% endtabs %}

![WPF ComboBoxAdv AutoComplete Append Mode](ComboBoxAdv_images/WPF-ComboBoxAdv-AutoComplete-Append-Mode.png)

View sample in GitHub.
