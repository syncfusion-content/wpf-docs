---
layout: post
title: Layout Related Features | ####UsethefollowingcodesnippettodefinetheNextButtonEventforWizard | wpf | Syncfusion
description: This section gives detailed description on layout related features of WizardControl
platform: wpf
control: Wizard
documentation: ug
---

# Layout Related Features

This section illustrates the following Layout-related features of [Wizard Control](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardControl.html).

## Setting the Minimum Height for the Interior Wizard Page Header

You can set the minimum height for the header of the Interior wizard page by using the [InteriorPageHeaderMinHeight](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardControl~InteriorPageHeaderMinHeight.html) property in [Wizard Control](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardControl.html).

{%tabs%}

{% highlight xaml %}

<syncfusion:WizardControl Name="wizardControl" InteriorPageHeaderMinHeight="150">

<syncfusion:WizardPage Name="wizardPage" />

</syncfusion:WizardControl>

{% endhighlight %}

{% highlight C# %}

WizardControl wizardControl = new WizardControl();

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardControl.InteriorPageHeaderMinHeight = 150; 

this.Content = wizardControl;

{% endhighlight %}

{%endtabs%}

![InteriorPageHeaderMinHeight of WizardPage](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg)

## Setting the Banner Background Color

You can set the background color of the banner for the [Wizard Control](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardControl.html) by using the [BannerBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardPage~BannerBackground.html) property. 

{%tabs%}

{% highlight xaml %}

<syncfusion:WizardControl Name="wizardControl">

<syncfusion:WizardPage Name="wizardPage" BannerBackground="Navy"/>

</syncfusion:WizardControl>

{% endhighlight %}

{% highlight C# %}

WizardControl wizardControl = new WizardControl();

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.BannerBackground = Brushes.Navy;

this.Content = wizardControl;

{% endhighlight %}

{%endtabs%}

![BannerBackground in WizardControl](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg)

## Setting the Banner Image

You can set an image for the banner of the [Wizard Page](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardPage.html) in  [Wizard Control](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardControl.html)
 using the [BannerImage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardPage~BannerImage.html) property.

N> You can set the banner image either on the interior or exterior wizard page based on the wizard page type.

{%tabs%}

{% highlight xaml %}

<syncfusion:WizardControl Name="wizardControl">

<syncfusion:WizardPage Name="wizardPage" BannerImage="/Image/sync.bmp"/>

</syncfusion:WizardControl>

{% endhighlight %}

{% highlight C# %}

WizardControl wizardControl = new WizardControl();

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.BannerImage = new BitmapImage(new Uri("/Image/sync.bmp", UriKind.RelativeOrAbsolute));  

this.Content = wizardControl;

{% endhighlight %}

{%endtabs%}

![BannerImage of WizardPage](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg)

## Setting Minimum Width for the Banner Image on the Exterior Wizard Page

You can set the minimum width of the banner image on the 'Exterior' wizard page by using the [ExteriorPageBannerImageMinWidth](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardControl~ExteriorPageBannerImageMinWidth.html) property in [Wizard Control](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.WizardControl.html).

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

this.Content = wizardControl;

{% endhighlight %}

{%endtabs%}

![ExteriorPageBannerImageMinWidth in Wizard Control](Layout-Related-Features_images/Layout-Related-Features_img4.jpeg)

## Setting Visual Styles for Wizard Control

The appearance of the Wizard control can be customized by using the “VisualStyle” property of SfSkinManager. The following are the various built-in skins for Wizard Control:

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

{%tabs%}

{% highlight xaml %}

<syncfusion:WizardControl Name="wizard" syncfusion:SkinStorage.VisualStyle="Blend">
    <syncfusion:WizardPage  PageType="Exterior">
            <TextBlock Text="This is an example project for themes in Wizard control" />
    </syncfusion:WizardPage>
    <syncfusion:WizardPage />
</syncfusion:WizardControl>

{% endhighlight %}

{%endtabs%}

![Blend appearance of WizardControl](Layout-Related-Features_images/Layout-Related-Features_img5.png)



