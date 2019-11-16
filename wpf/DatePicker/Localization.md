---
layout: post
title: Localization support | SfDatePicker | WPF | Syncfusion
description: Details about localization support in SfDatePicker contol for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Localization support in SfDatePicker

Localization is the process of making application as multi-lingual, by formatting the content according to cultures.

## Creating Resource file and adding value to the resource string based on Culture

Add a resource file(.resx) in the application and assign key values to the resource string based on the culture. Refer below screenshot,

![Add a resource file](Localization_images/localization-img1.png)

## Assign a Current UI culture to the application

While initializing the application, [CurrentCulture](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentculture?view=netframework-4.7.2) and [CurrentUICulture](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentuiculture?view=netframework-4.7.2) should be mentioned in code, so that application will get the appropriate values provided in resource file.

{% highlight XAML %}
 
 <syncfusion:SfDatePicker Name="datePicker" HorizontalAlignment="Center" VerticalAlignment="Center" FormatString="dddd, MMMM dd, yyyy h:mm:ss tt"/>

{% endhighlight %}

{% highlight C# %}

            CultureInfo culture = new System.Globalization.CultureInfo("ar-SA");
            culture.DateTimeFormat.AMDesignator = "صباحا";
            culture.DateTimeFormat.PMDesignator = "مساء";
            System.Threading.Thread.CurrentThread.CurrentCulture = culture;
            System.Threading.Thread.CurrentThread.CurrentUICulture = culture;

{% endhighlight %}

![Value field of SfDatePicker is localized](Localization_images/localization-img3.png)

Value field of SfDatePicker is localized
{:.caption}

![Display text is localized to ar-SA culture](Localization_images/localization-img2.png)

Display text "Choose Date" is localized to ar-SA culture
{:.caption}



