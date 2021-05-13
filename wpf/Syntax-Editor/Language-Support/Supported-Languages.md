---
layout: post
title: Supported Languages in WPF Syntax Editor control | Syncfusion
description: Learn about Supported Languages support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# Supported Languages in WPF Syntax Editor

Edit for WPF provides built-in support for a procedural and markup languages such as C#, Visual Basic, XAML and XML. It also supports SQL language and facilitates the users to provide custom language configurations.

With the language support, EditControl enables the users to create, open, modify and save programming codes from different file types. EditControl provides built in Syntax highlighting and outlining support for all supported languages with SQL being exception in outlining support. It also provides built-in IntelliSense support for all procedural languages such as C# and Visual Basic.

The `DocumentLanguage` property in the EditControl class enables the users to select the language. DocumentLanguage is a Language enum type property with default value as Text. The following lines of code can be used to change the DocumentLanguage property.

{% tabs %}

{% highlight XAML %}

<sfedit:EditControl x:Name="editControl" DocumentLanguage="CSharp" DocumentSource="C:\Source.cs" FontSize="13"/>

{% endhighlight %}

{% highlight C# %}

editControl.DocumentLanguage = Languages.CSharp;

{% endhighlight %}

{% endtabs %}

The following image displays the EditControl displaying contents.

![EdiControl language support](Supported-Languages_images/Supported-Languages_img1.jpeg)
