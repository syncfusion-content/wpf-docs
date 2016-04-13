---
layout: post
title: Layout Related Features | ####UsethefollowingcodesnippettodefinetheNextButtonEventforWizard | wpf | Syncfusion
description: layout related features
platform: wpf
control: Wizard
documentation: ug
---

# Layout Related Features

This section illustrates the following Layout-related features of Wizard control.

## Setting the Minimum Height for the Interior Wizard Page Header

You can set the minimum height for the header of the Interior wizard page by using the InteriorPageHeaderMinHeight property.

Use the following code snippet for setting the minimum height for the page header.


{%tabs%}
{% highlight xaml %}





<syncfusion:WizardControl Name="wizardControl" InteriorPageHeaderMinHeight="150">

    <syncfusion:WizardPage Name="wizardPage" />

</syncfusion:WizardControl>

{% endhighlight %}


{% highlight C# %}




WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardControl.InteriorPageHeaderMinHeight = 150; 


{% endhighlight %}

{%endtabs%}


![](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg)





{%seealso%}

Wizard Page Type

{%endseealso%}

## Setting the Banner Background Color

Set the background color of the banner for the Wizard control by using the BannerBackground property. The following code snippet is used to set this property.

{%tabs%}
{% highlight xaml %}




<syncfusion:WizardControl Name="wizardControl">

    <syncfusion:WizardPage Name="wizardPage" BannerBackground="Navy"/>

</syncfusion:WizardControl>
{% endhighlight %}



{% highlight C# %}




WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.BannerBackground = Brushes.Navy;

{% endhighlight %}

{%endtabs%}

![](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg)




{%seealso%}
Banner Image
{%endseealso%}

## Setting the Banner Image

Set an image for the banner of the Wizard control using the BannerImage property.

N> You can set the banner image either on the interior or exterior wizard page based on the wizard page type.



The following code snippet can be used to set the banner image.

{%tabs%}
{% highlight xaml %}




<syncfusion:WizardControl Name="wizardControl">

    <syncfusion:WizardPage Name="wizardPage" BannerImage="/Image/sync.bmp"/>

</syncfusion:WizardControl>
{% endhighlight %}

{% highlight C# %}




WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.BannerImage = new BitmapImage(new Uri("/Image/sync.bmp", UriKind.RelativeOrAbsolute));  
{% endhighlight %}
{%endtabs%}

![](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg)




{%seealso%}

Banner Background Color

{%endseealso%}

## Setting Minimum Width for the Banner Image on the Exterior Wizard Page

You can set the minimum width of the banner image on the 'Exterior' wizard page by using the ExteriorPageBannerImageMinWidth property.

The following code snippet illustrates setting the minimum width for the banner image.


{%tabs%}
{% highlight xaml %}




<syncfusion:WizardControl Name="wizardControl" ExteriorPageBannerImageMinWidth="10">

    <syncfusion:WizardPage Name="wizardPage" PageType="Exterior" BannerImage="/Image/sync.bmp"/>

</syncfusion:WizardControl>

{% endhighlight %}


{% highlight C# %}




WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.BannerImage = new BitmapImage(new Uri("/Image/sync.bmp", UriKind.RelativeOrAbsolute));

wizardPage.PageType = WizardPageType.Exterior;

wizardControl.ExteriorPageBannerImageMinWidth = 10;

{% endhighlight %}

{%endtabs%}

![](Layout-Related-Features_images/Layout-Related-Features_img4.jpeg)




{%seealso%}

Wizard Page Type

{%endseealso%}

## Setting Visual Styles for Wizard Control

The appearance of the Wizard control can be customized by using the “VisualStyle” property. The following are the various built-in skins for Wizard Control:

* Blend
* Office2003
* Office2007Blue
* Office2007Black
* Office2007Silver
* ShinyBlue
* ShinyRed
* SyncOrange
* VS2010
* Metro
* Transparent



