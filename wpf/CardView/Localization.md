---
layout: post
title: Localization in CardView control.
description: How to localize the CardView control.
platform: wpf
control: CardView
documentation: ug
---

# Localization 

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the CardView by [adding resource file](https://msdn.microsoft.com/library/aa992030.aspx). Application culture can be changed by setting `CurrentUICulture` after `InitializeComponent` method. 

Below application culture changed to French.

{% tabs %}

{% highlight C# %}

public MainWindow()
{
    InitializeComponent();
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
}    

{% endhighlight %}

{% endtabs %}


To localize the CardView based on `CurrentUICulture` using resource files, follow the below steps. 

1. Create new folder and named as **Resources** in your application. 

2. Right-click on the Resources folder, select **Add** and then **NewItem**.

3. In `Add New Item` wizard, select the **Resource File** option and name the filename as **Syncfusion.Tools.Wpf.&lt;culture name&gt;.resx**. For example, you have to give name as **Syncfusion.Tools.Wpf.fr-FR.resx** for French culture.

![](Localization_images/Localization_image1.png)

4. Now, select `Add` option to add the resource file in **Resources** folder.

![](Localization_images/Localization_image2.png)

5. Add the Name/Value pair in Resource Designer of **Syncfusion.Tools.Wpf.fr-FR.resx** file and change its corresponding value to corresponding culture. 

![](Localization_images/Localization_image3.png)

The following screenshot shows the localized CardView control.

![](Localization_images/Localization_image4.png)
