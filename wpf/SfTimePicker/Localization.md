---
layout: post
title: Localization support in SfTimePicker contol for WPF
description: Details about localization support in SfTimePicker contol for WPF
platform: wpf
control: SfTimePicker
documentation: ug
---

# Localization support in SfTimePicker

Localization is the process of making application as multi-lingual, by formatting the content according to cultures.

## Creating Resource file and adding value to the resource string based on Culture

Add a resource file(.resx) in the application and assign key values to the resource string based on the culture. Refer below screenshot,

![](Localization-images/localization-img1.png)

## Assign a Current UI culture to the application

While initializing the application, CurrentCulture and CurrentUICulture should be mentioned in code, so that application will get the appropriate values provided in resource file.

{% highlight XAML %}
 
 <syncfusion:SfTimePicker HorizontalAlignment="Center" VerticalAlignment="Center" FormatString="dddd, MMMM dd, yyyy h:mm:ss tt"/>

{% endhighlight %}

{% highlight C# %}

            CultureInfo culture = new System.Globalization.CultureInfo("ar-SA");
            culture.DateTimeFormat.AMDesignator = "صباحا";
            culture.DateTimeFormat.PMDesignator = "مساء";
            System.Threading.Thread.CurrentThread.CurrentCulture = culture;
            System.Threading.Thread.CurrentThread.CurrentUICulture = culture;

{% endhighlight %}

![](Localization-images/localization-img3.png)

Value field of SfTimePicker is localized
{:.caption}

![](Localization-images/localization-img2.png)

Display text "Choose Time" and Meridiem(AM/PM) is localized
{:.caption}




