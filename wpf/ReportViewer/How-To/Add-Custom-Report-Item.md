---
layout: post
title: Custom Report Item
description: Overview of Custom Report Item
platform: WPF
control: ReportViewer
documentation: ug
---

## Overview

A custom report item allows you to add the functionality that is not natively supported in the RDL or extend the functionality of existing controls in the RDL standard. The run-time component allows to render the custom report item in report viewer.

## Creating a custom report item run-time component

The run-time component of the custom report item is implemented by using CLS-compliant language, and is called by the report processor at run-time. The below section provides detail to create run-time component for the barcode custom report item for report viewer.

### Create report item assembly

1.	Open the Visual Studio and select the class library project type, and then name the project as "Syncfusion.Extensions.BarcodeCRI" for the run-time component.
2.	Add the reference "Syncfusion.ReportControls.Wpf" for the extension project.
3.  Add a class "BarcodeCustomReportItem" by inheriting the `ICustomReportItem` interface.

>Note: Refer the above assemblies from the below installed location.
For report platform: %localappdata%\Syncfusion\ReportsSDK\Samples\Common\Assemblies and
For Essential Studio: C:\Program Files (x86)\Syncfusion\Essential Studio{{ site.releaseversion }}\Assemblies 


### Implementing the ICustomReportItem interface

To create a CustomReportItem run-time component, you should implement the `ICustomReportItem` interface, it generates the following two method stubs:

Interface methods	|Definition
----------|----------
GenerateReportItemDefinition	|Called first and is used for setting definition properties and creating the image object that contains both the definition and instance properties that are used for rendering the item.
EvaluateReportItemInstance	|Called after the definition objects have been evaluated, and it provides the instance objects that will be used for rendering the item.

{% highlight c# %}
namespace Syncfusion.Extensions.BarcodeCRI
{
    public class BarcodeCustomReportItem : RDL.Data.ICustomReportItem
    {
        #region ICustomReportItem Members

        public void GenerateReportItemDefinition(CustomReportItem cri)
        {
            //It will create the Image object
            cri.CreateCriImageDefinition();
        }

        public void EvaluateReportItemInstance(CustomReportItem cri)
        {
            Thread thread = new Thread(delegate ()
            {
                RDL.Data.Image imageReportItem = (RDL.Data.Image)cri.GeneratedReportItem;
                imageReportItem.ImageData = DrawImage(cri);
            }, (1024 * 1024 * 64));

            thread.SetApartmentState(ApartmentState.STA);
            thread.Start();
            thread.Join();
        }

        #endregion

        //To create image from custom report item control
        private byte[] DrawImage(CustomReportItem customReportItem)
        {
            try
            {
                byte[] imageData = null;
                SfBarcode barcodeControl = new SfBarcode();
                barcodeControl.Background = new SolidColorBrush(Colors.Transparent);
                barcodeControl.Height = customReportItem.Height.ToPixels();
                barcodeControl.Width = customReportItem.Width.ToPixels();
                barcodeControl.Text = barcodeValue;
                barcodeControl.InvalidateArrange();
                barcodeControl.UpdateLayout();
                MemoryStream stream = new ImageConversion().CovertToImage(barcodeControl);
                imageData = new byte[(int)stream.Length];
                stream.Seek(0, SeekOrigin.Begin);
                stream.Read(imageData, 0, (int)stream.Length);
                return imageData;
            } 
            catch
            {
                return null;
            }
        }
    }
}
{% endhighlight %}

### Convert custom report item as image

The custom report item is rendered as image in report viewer, so that the run-time component need to be converted as an image. The following converter is used to generate the image for rendering.

{% highlight c# %}

internal partial class ImageConversion : UserControl
{
    Canvas InnerCanvas;

    public MemoryStream CovertToImage(Control innerControl)
    {
        try
        {
            this.InnerCanvas = new Canvas();
            this.Content = this.InnerCanvas;

            innerControl.Margin = new Thickness(0);
            InnerCanvas.Children.Add(innerControl);

            InnerCanvas.Width = innerControl.Width;
            InnerCanvas.Height = innerControl.Height;

            Canvas canvas = this.InnerCanvas;
            canvas.Measure(new Size((int)canvas.Width, (int)canvas.Height));
            canvas.Arrange(new Rect(new Size((int)canvas.Width, (int)canvas.Height)));

            int Height = ((int)(InnerCanvas.ActualHeight));
            int Width = ((int)(InnerCanvas.ActualWidth));

            this.Height = InnerCanvas.Height;
            this.Width = InnerCanvas.Width;
            InnerCanvas.LayoutTransform = null;

            Size size = new Size(InnerCanvas.ActualWidth, InnerCanvas.ActualHeight);

            InnerCanvas.Background = Brushes.White;
            InnerCanvas.Arrange(new Rect(size));
            InnerCanvas.UpdateLayout();

            RenderTargetBitmap rtb = new RenderTargetBitmap(Width, Height, 300, 300, PixelFormats.Default);
            rtb.Render(InnerCanvas);

            var Source = new MemoryStream();
            BitmapEncoder encoder = new BmpBitmapEncoder();
            encoder.Frames.Add(BitmapFrame.Create(rtb));
            encoder.Save(Source);
            return Source;
        }
        catch
        {
            return null;
        }
    }
}
{% endhighlight %}

#### Build project

You can clean and build the extension project, it will generate the run-time component assembly "Syncfusion.Extensions.BarcodeCRI.dll" in the bin folder of the project.

## Deploy a custom report item 

To deploy a custom report item, you must modify the application configuration files or create "ReportExtensions.config" file and copy the run-time component assembly (Syncfusion.Extensions.BarcodeCRI) and its dependent assemblies to the bin folder of your application. The deployment requires configuration to process the extensions, and the following describes about configuration settings.

You need to replace the newly created assembly and its dependent assemblies in the application bin folder. 

1.	Create a "ReportExtensions.config" file in your application.
2.	The following "configSections" section is mandatory to process the extension in the control, so add it as shown in the following code:

{% highlight xml %}
<configSections>
    <section name="ReportingExtensions" type="Syncfusion.Reporting.Extensions,  Syncfusion.ReportControls.WPF" allowLocation="true" allowDefinition="Everywhere" />
</configSections>
{% endhighlight %}

3.	You must add the `ReportItem` tag for all newly added report item types. It has following attributes:

Attribute Name |	Description
---------|----------
Name	|Name of your report item that is going to display in the list.
Assembly	|Name of the newly created report item assembly.
Type	|Report item class name with the namespace.

{% highlight xml %}
 <ReportingExtensions>
    <ReportItems>
      <ReportItem Name="Barcode" Assembly="Syncfusion.Extensions.BarcodeCRI" Type="Syncfusion.Extensions.BarcodeCRI.BarcodeCustomReportItem" />
    </ReportItems>
  </ReportingExtensions>
</configuration>
{% endhighlight %}

After creating the config file, add it to the report viewer application.

The following steps describe how to create a standalone report viewer application:

[Create a standalone report viewer application in WPF.](/wpf/reportviewer/getting-started)

Run the application, output with the barcode custom report item is rendered as below:

![](Add-Custom-Report-Item-images/Custom-Report-Item-1.png)

Shows the invoice report rendered with the barcode custom report item.
   {:.caption}	

