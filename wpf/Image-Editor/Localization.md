---
layout: post
title: Localization support in syncfusion SfImageEditor WPF.
description: This section describes on how to localize the SfImageEditor resources with their corresponding culture.
platform: wpf
control: SfImageEditor
 documentation: ug
---

# Localization in WPF ImageEditor (SfImageEditor)

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the SfImageEditor by adding resource file. Application culture can be changed by setting `CurrentUICulture` before `InitializeComponent()` method.

Use the below code to change the application culture to French.

{% tabs %} 

{% highlight C# %} 

        public MainWindow()
        {
            Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
            InitializeComponent();           
        }  

{% endhighlight %}

{% endtabs %} 

To localize SfImageEditor based on `CurrentUICulture` using resource files, follow the below steps.

1.Create new folder and name it as **Resources** in your application.
2.Add the default resource file of SfImageEditor into **Resources** folder. You can download the Syncfusion.SfImageEditor.WPF.resx [`here`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfImageEditor.WPF-240771729).

![Shapes](Images/Localization_img1.png) 

3.Right-click on the Resources folder, select Add and then NewItem.

4.In Add New Item wizard, select the Resource File option and name it as Syncfusion.SfImageEditor.WPF.<culture name>.resx. For example, you have to give name as Syncfusion.SfImageEditor.WPF.fr.resx for French culture.

![Shapes](Images/Localization_img2.png) 

5.Now, select Add option to add the resource file in the Resources folder.

![Shapes](Images/Localization_img3.png) 

6.Add the Name/Value pair in Resource Designer of Syncfusion.SfImageEditor.WPF.fr.resx file and change its corresponding value to the corresponding culture.

![Shapes](Images/Localization_img4.png) 

Below image depicts the application translated into French culture.

![Shapes](Images/Localization_img5.png)   
