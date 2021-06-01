---
layout: post
title: Editing and AutoCompletion in WPF MultiColumnDropDown | Syncfusion
description: Editing and autocompletion in Syncfusion WPF MultiColumnDropDown (SfMultiColumnDropDownControl), its elements and more.
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

# Editing and AutoCompletion

## Editor

You can edit the textbox in the SfMultiColumnDropDownControl. You could make the textbox editable or non –editable in order to prevent typing. SfMulticolumnControl contains the following properties for Editing.

* AllowImmediatePopup – It specifies whether the DropDownGrid opens or not, when you edit the textbox. When it is set to true, DropDownGrid opens if the Editor finds the match values from the collection. Or else the DropDownGrid does not open.
* AllowSpinOnMouseWheel- It specifies whether the value can be changed by spinning the mouse wheel. It is a Boolean property. By default it is set to True.
* AllowNullInput – It specifies whether a null value can be set or not in the Editor. It is a Boolean property. By default it is set to False.
* ReadOnly –It specifies whether the Editor is set to read-only. When this property is set to true – you can only change the value by selecting from the DropDownGrid.
* IsDropDownOpen - It specifies whether the popup is in open or close state initially. It is a Boolean property and by default it is set to False.
* Text –Gets or sets the Text to the Editor. It is a string property. It has empty value as default.

## Auto Completion of Text

SfMultiColumnDropDownControl provides auto completion support. When you type into the editor, the control returns the relative match for the typed text based on the Display Member.

AllowAutoComplete: This property is a Boolean property that represents enables or disables provide suggestion text for auto completion.

As an example of this feature, consider a simple scenario where the SfMultiColumnDropDownControl is bound to an ObservableCollection, with AutoComplete enabled.

{% highlight xaml %}



<Window.DataContext>

  <local:Viewmodel/>

</Window.DataContext>



<syncfusion:SfMultiColumnDropDownControl AllowAutoComplete="True"

DisplayMember="Name"    

ItemsSource="{Binding GridItemSource}"

ValueMember="Title" />
{% endhighlight %}

In the above code example, AutoCompletion is enabled .It gives the matching suggestion from the collection based on the input as illustrated in the following screenshot.

![Features_images5](Features_images/Features_img5.png)


The following screenshot displays the output for AllowAutoCompletion set to False.

![Features_images6](Features_images/Features_img6.png)



