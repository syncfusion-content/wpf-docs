---
layout: post
title: Getting-started
description: getting started
platform: wpf
control: Presentation
documentation: ug
---

# Getting started

This section explains you the basic information on how to get started with creating or editing Microsoft PowerPoint files with few lines of code by using Essential Presentation APIs.

## Creating a new Presentation from scratch with basic elements

An entire PowerPoint file is represented with an instance of IPresentation interface of Essential Presentation. IPresentation is the root element in Essential Presentation DOM (document object model). Each Presentation consists of collection of slides. By using this DOM, you can add, edit and remove content from the document by iterating elements.

In this section, you can learn how to create a simple PowerPoint presentation with few slides in few lines by using Essential Presentation API.

Initially, you can learn how to create a slide as follows.

![](Getting-started_images/Getting-started_img1.png)


Create an instance of IPresentationinterface as follows. Instance of IPresentation represents the root element of Presentation that in turn contains the collections of slides.

 {% highlight c# %}


//Creates a new instance of PowerPoint Presentation

IPresentation presentation = Presentation.Create();

 {% endhighlight %}





Presentation has a property named Slides to represent the slide collections. Create an instance of an ISlide in the presentation by using the Add method of slide collection and during the creation of slide, you can specify the layout design as parameter. 

 {% highlight c# %}
 

//presentation.Slides represents the collection of slides in PowerPoint presentation

//Add a slide into the presentation through the Add method of Slide collection property

//The user has to pass the Slide design type as parameter

ISlide firstSlide = presentation.Slides.Add(SlideLayoutType.Blank);

 {% endhighlight %}





Each slide contains a collection of shapes. All the contents are added in slide as a shape or within a shape. You can add the textual contents in a slide with the help of textbox shape. The following code example explains how to add a textbox within the slide. You need to specify the left position, top position, width & height (in points) as parameters. 

 {% highlight c# %}


//Add a textbox shape in a slide by specifying its position & size

IShape titleShape = firstSlide.AddTextBox(100, 75, 756, 200);

//set the vertical alignment of textual contents within textbox shape

titleShape.TextBody.VerticalAlignment = VerticalAlignmentType.Bottom;

 {% endhighlight %}





All the contents of textbox or shape is added with in its body that represents a property named TextBody. Then add a paragraph into the textbox shape as follows. Here, the horizontal alignment of paragraph is set to center. By default it is left aligned.

 {% highlight c# %}
 

//Add a paragraph in the body of the shape

IParagraph paragraph = titleShape.TextBody.AddParagraph();

//set the Horizontal alignment of the paragraph as center

paragraph.HorizontalAlignment = HorizontalAlignmentType.Center;

 {% endhighlight %}





A paragraph can contain more than one text part. TextPart holds textual contents in the paragraph and is like span tag in html. Here, text part is added with the text “Hello Presentation” and set its formatting such as bold and font size.

 {% highlight c# %}
 
  
//Add a textPart in the paragraph

ITextPart textPart = paragraph.AddTextPart("Hello Presentation");

textPart.Font.FontSize = 80;

textPart.Font.Bold = true;

 {% endhighlight %}





Refer to the following screenshot.

![](Getting-started_images/Getting-started_img2.png)


Now, add another textbox shape in the shape. Further, within the textbox shape, add two paragraphs as follows.

 {% highlight c# %}


//Add another textbox shape 

IShape subTitleShape = firstSlide.AddTextBox(100, 300, 756, 100);

//Set the vertical alignment of textbox shape as top

subTitleShape.TextBody.VerticalAlignment = VerticalAlignmentType.Top;

//Add the first paragraph in the textbox shape

paragraph = subTitleShape.TextBody.AddParagraph();

//set the horizontal alignment of the paragraph as center

paragraph.HorizontalAlignment = HorizontalAlignmentType.Center;

//Add a new text part in the first paragraph with the text “by”

textPart = paragraph.AddTextPart("by");

//Sets the font size of the textpart as 40

textPart.Font.FontSize = 40;

//Add the second paragraph in the textbox shape

paragraph = subTitleShape.TextBody.AddParagraph();

paragraph.HorizontalAlignment = HorizontalAlignmentType.Center;

//Add a new text part in the second paragraph with the text “James Smith”

textPart = paragraph.AddTextPart("James Smith");

textPart.Font.FontSize = 40;

 {% endhighlight %}





On saving the Presentation at this instance will result with the PowerPoint Presentation with one slide and its contents are follows. 

![](Getting-started_images/Getting-started_img3.png)


Now this section demonstrates how to create a bulleted and numbered list in the second slide as follows.

![](Getting-started_images/Getting-started_img4.png)


Add three textbox shape in the slide. A textbox shape to hold the title “Bulleted & Numbered List”, a textbox to hold the bulleted list in the left side of the slide and another textbox to hold the numbered list in the right side.

The following code example explains how to add a new slide into the PowerPoint presentation.

 {% highlight c# %}
 

//Add the second slide into the presentation 

ISlide secondSlide = presentation.Slides.Add(SlideLayoutType.Blank);

 {% endhighlight %}





Add a new textbox at the top of the slide in order to set the title content for the slide. Further add a new paragraph within the newly created shape and add a text part with the text “Bulleted & Numbered List” as follows.

 {% highlight c# %}


//Add the textbox to add title of the slide

titleShape = secondSlide.AddTextBox(65, 30, 830, 100);

//sets the vertical alignment of shape contents as middle

titleShape.TextBody.VerticalAlignment = VerticalAlignmentType.Middle;

//Add a new paragraph into the shape

paragraph = titleShape.TextBody.AddParagraph();

//set the horizontal alignment of the paragraph

paragraph.HorizontalAlignment = HorizontalAlignmentType.Center;

//Add a textpart as child to the paragraph and set its text as “Bulleted & Numbered //List”

textPart = paragraph.AddTextPart("Bulleted & Numbered List");

//Sets the font name & font size of the textpart

textPart.Font.FontSize = 72;

textPart.Font.FontName = "Calibri";

 {% endhighlight %}





After setting the title content of the slide, then create two textboxes, one at the left hand side and other at the right hand side of the slide.

 {% highlight c# %}
 

// adding a textbox to hold the bulleted list 

IShape leftShape = secondSlide.AddTextBox(65, 140, 410, 250);

// adding another textbox to hold the numbered list

IShape rightShape = secondSlide.AddTextBox(485, 140, 410, 250);

 {% endhighlight %}





The ListFormat property of the paragraph represents all the list information. Some of the important properties are explained in the following table.

Property Table

<table>
<tr>
<th>
{{ '**Property Name**' | markdownify }}</th><th>
{{ '**Short Description**' | markdownify }}</th></tr>
<tr>
<td>
Type</td><td>
Specifies the type of the list. The value can be None or Bulleted or Numbered.</td></tr>
<tr>
<td>
IndentLevelNumber</td><td>
Specifies the list level of the paragraph. The possible value range is 1 to 9.On changing the value of IndentLevelNumber, you can easily create nested list level.</td></tr>
<tr>
<td>
BulletCharacter</td><td>
Represents the bullet character. You can set the bullet character manually when creating the list.</td></tr>
<tr>
<td>
FontName</td><td>
Represents the font name of the bullet character.</td></tr>
<tr>
<td>
Size</td><td>
Represents the size of the bullet or number with respect to its paragraph text size. Its unit is Percentage. Here, when you set the Size as 200%, the bullet character or number size is 200% of its text. The possible range can be 25 to 400</td></tr>
<tr>
<td>
NumberStyle</td><td>
Specifies the numbering style of the list. </td></tr>
<tr>
<td>
Startvalue</td><td>
Specifies the starting value of the numbered list. By default, it starts from 1</td></tr>
</table>


Here, a new paragraph is added and the ListFormat property is accessed. In order to create a bulleted list, you can set the list type as bulleted (paragraph.ListFormat.Type = ListType.Bulleted;) and set its list level by using the property IndentLevelNumber as 1. Then set its bullet character, font name & size as follows. 

Finally set the hanging indent of the paragraph with the property FirstLineIndent. There is no separate property for hanging indent and first line indent. If the value is positive, then the first line indent is applied, if the value is negative, then the hanging indent is applied.

 {% highlight c# %}
 
    

// adding a new paragraph with the text in the left hand side textbox. 

paragraph = leftShape.TextBody.AddParagraph("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

//Set the list type as bulleted

paragraph.ListFormat.Type = ListType.Bulleted;

//setting the bullet character for this list paragraph

paragraph.ListFormat.BulletCharacter = Convert.ToChar(183);

// setting the font of the bullet character

paragraph.ListFormat.FontName = "Symbol";

// setting the bullet character size. If 100, here means 100% of its text. Possible values can range from 25 to 400

paragraph.ListFormat.Size = 100;

// setting the list level as 1. Possible values can range from 1 to 9

paragraph.IndentLevelNumber = 1;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;

 {% endhighlight %}





Now you can create a new paragraph with bulleted list and set its list level as 2 by using the property IndentLevelNumber as follows.

 {% highlight c# %}
 
   

// adding another paragraph with the text in the left hand side textbox.  

paragraph = leftShape.TextBody.AddParagraph("Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

//Set the list type as bulleted

paragraph.ListFormat.Type = ListType.Bulleted;

//setting the bullet character for this list paragraph

paragraph.ListFormat.BulletCharacter = Convert.ToChar(183);

// setting the font of the bullet character

paragraph.ListFormat.FontName = "Symbol";

// setting the bullet character size. If 100, here means 100% of its text. Possible values can range from 25 to 400

paragraph.ListFormat.Size = 100;

// setting the list level as 2. Possible values can range from 1 to 9

paragraph.IndentLevelNumber = 2;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;

 {% endhighlight %}





Refer to the following screenshot.

![](Getting-started_images/Getting-started_img5.png)


Here, add two new paragraph with the bulleted list. One with list level 2 and other with list level 1.

 {% highlight c# %}
 
  

// adding another paragraph with the text in the left hand side textbox.  

paragraph = leftShape.TextBody.AddParagraph("Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.");

//Set the list type as bulleted

paragraph.ListFormat.Type = ListType.Bulleted;

//setting the bullet character for this list paragraph

paragraph.ListFormat.BulletCharacter = Convert.ToChar(183);

// setting the font of the bullet character

paragraph.ListFormat.FontName = "Symbol";

// setting the bullet character size. If 100, here means 100% of its text. Possible values can range from 25 to 400

paragraph.ListFormat.Size = 100;

// setting the list level as 2. Possible values can range from 1 to 9

paragraph.IndentLevelNumber = 2;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;





paragraph = leftShape.TextBody.AddParagraph("Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");

//Set the list type as bulleted

paragraph.ListFormat.Type = ListType.Bulleted;

//setting the bullet character for this list paragraph

paragraph.ListFormat.BulletCharacter = Convert.ToChar(183);

// setting the font of the bullet character

paragraph.ListFormat.FontName = "Symbol";

// setting the bullet character size. If 100, here means 100% of its text. Possible values can range from 25 to 400

paragraph.ListFormat.Size = 100;

// setting the list level as 1. Possible values can range from 1 to 9

paragraph.IndentLevelNumber = 1;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;

 {% endhighlight %}





On saving the presentation, the second slide with the list is as follows.

![](Getting-started_images/Getting-started_img6.png)


This section explains how to create numbered list. 

 {% highlight c# %}
 
 

paragraph = rightShape.TextBody.AddParagraph("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

//setting the list type as Numbered list

paragraph.ListFormat.Type = ListType.Numbered;

//setting the numbered style (list numbering) as Arabic number following by period.

paragraph.ListFormat.NumberStyle = NumberedListStyle.ArabicPeriod;

//setting the starting value as 1

paragraph.ListFormat.StartValue = 1;

// setting the list level as 1

paragraph.IndentLevelNumber = 1;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;

 {% endhighlight %}



 {% highlight c# %}
 
   

paragraph = rightShape.TextBody.AddParagraph("Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

//setting the list type as Numbered list

paragraph.ListFormat.Type = ListType.Numbered;

//setting the numbered style (list numbering) as lower case alphabet following by period.

paragraph.ListFormat.NumberStyle = NumberedListStyle.AlphaLcPeriod;

// setting the list level as 2

paragraph.IndentLevelNumber = 2;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;



paragraph = rightShape.TextBody.AddParagraph("Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.");

//setting the list type as Numbered list

paragraph.ListFormat.Type = ListType.Numbered;

//setting the numbered style (list numbering) as roman number lower casing following by period.

paragraph.ListFormat.NumberStyle = NumberedListStyle.RomanLcPeriod;

// setting the list level as 3

paragraph.IndentLevelNumber = 3;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;



paragraph = rightShape.TextBody.AddParagraph("Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");

//setting the list type as Numbered list

paragraph.ListFormat.Type = ListType.Numbered;

paragraph.ListFormat.NumberStyle = NumberedListStyle.ArabicPeriod;

// setting the list level as 1

paragraph.IndentLevelNumber = 1;

// setting the hanging value as 20

paragraph.FirstLineIndent = -20;

 {% endhighlight %}





On saving the presentation, the slide looks like the following screenshot.

![](Getting-started_images/Getting-started_img7.png)


This section explains how to insert a picture into a slide. Create a new slide with the title “Inserting Image…”

 {% highlight c# %}
 
   

//Add the third slide into the presentation 

ISlide thirdSlide = presentation.Slides.Add(SlideLayoutType.Blank);

//Add a textbox and set its vertical alignment as middle

titleShape = thirdSlide.AddTextBox(65, 30, 830, 100);

titleShape.TextBody.VerticalAlignment = VerticalAlignmentType.Middle;

//add a new paragraph in the titleShape and set its horizontal alignment as center

paragraph = titleShape.TextBody.AddParagraph();

paragraph.HorizontalAlignment = HorizontalAlignmentType.Center;

//Add a new text part with the text as “Inserting Image…”

textPart = paragraph.AddTextPart("Inserting Image...");

textPart.Font.FontSize = 72;

textPart.Font.FontName = "Calibri";

 {% endhighlight %}





Image can be added into the slide with the help of AddPicture method of shape collection. When the image is added, you can specify the image stream, position & size as parameters to this method. The following code example explains how to insert two images into the third slide.

 {% highlight c# %}
 


//Add the third slide into the presentation 

Image image = Image.FromFile(@"image1.jpg");

IPicture picture = thirdSlide.Shapes.AddPicture(new MemoryStream(image.ImageData), 65, 140, 410, 250);



image = Image.FromFile(@"image2.jpg");

picture = thirdSlide.Shapes.AddPicture(new MemoryStream(image.ImageData), 485, 140, 410, 250);

 {% endhighlight %}





After adding the images into the slide, the slide looks like the following screenshot. 

![](Getting-started_images/Getting-started_img8.png)


Finally, you can save the presentation by using Save method as follows. In order to release the resources utilized by presentation instance, make sure that the presentation gets closed finally.

 {% highlight c# %}
 
 

//Add the third slide into the presentation 

presentation.Save("sample.pptx");

presentation.Close();

 {% endhighlight %}



# Creating a Chart in Presentation from scratch 

Charts can convey much more than numbers and makes it easier to understand the meaning behind the numbers. A Slide can have more than 1 chart. You can access the chart present in the slide through the property ISlide.Charts that represents the collection of chart in the slide. The chart collection provides a method named AddChart to include a chart in the slide. In order to create a chart, you need the data to be represents as chart, serie and category information. The chart data is preserved within Presentation as an excel file (embedded). Filling the chart data values is like filling an excel sheet.

Create a new presentation with one slide as follows.

 {% highlight c# %}
 
  

//Create an instance of the IPresentation  

IPresentation presentation = Presentation.Create();

//Create a new slide

ISlide slide = presentation.Slides.Add(SlideLayoutType.Blank);

 {% endhighlight %}





The chart is represented by IOfficeChart interface in the Essential Presentation. Now, in the next step add a new chart into the slide.

 {% highlight c# %}
 


//Add a new chart in the slide by specifying its position & size as parameters.

IOfficeChart chart = slide.Charts.AddChart(100, 150, 800, 350);

 {% endhighlight %}





Chart title and its formatting is set by using ChartTitle property of IOfficeChart and ChartTitleArea property of IOfficeChart respectively. 

 {% highlight c# %}
 
  

//Add a new chart in the slide by specifying its position & size as parameters.

chart.ChartTitle = "Sales comparison";

chart.ChartTitleArea.Bold = true;

 {% endhighlight %}





The chart type is specified with the help of ChartType property of IOfficeChart interface. 

N> 3D charts are not supported in image & PDF conversion._

 {% highlight c# %}
 
   

//Specify the chart type 

chart.ChartType = OfficeChartType.Column_Clustered;


 {% endhighlight %}




All the chart data is preserved in the PowerPoint presentation as an embedded excel sheet. The data is filled by having an excel sheet in mind. The chart data is added into the presentation by using ChartData property of IOfficeChart. This ChartData provides APIs for setting the value. 

 {% highlight c# %}
 
    

//SetValue method takes 3 parameters – RowIndex, columnIndex & data

chart.ChartData.SetValue(1, 1, "Month");

chart.ChartData.SetValue(2, 1, "July");

chart.ChartData.SetValue(3, 1, "August");

chart.ChartData.SetValue(4, 1, "September");

chart.ChartData.SetValue(5, 1, "October");

chart.ChartData.SetValue(6, 1, "November");

chart.ChartData.SetValue(7, 1, "December");



chart.ChartData.SetValue(1, 2, "2013");

chart.ChartData.SetValue(2, 2, 35);

chart.ChartData.SetValue(3, 2, 37);

chart.ChartData.SetValue(4, 2, 30);

chart.ChartData.SetValue(5, 2, 29);

chart.ChartData.SetValue(6, 2, 25);

chart.ChartData.SetValue(7, 2, 30);



chart.ChartData.SetValue(1, 3, "2014");

chart.ChartData.SetValue(2, 3, 30);

chart.ChartData.SetValue(3, 3, 25);

chart.ChartData.SetValue(4, 3, 29);

chart.ChartData.SetValue(5, 3, 35);

chart.ChartData.SetValue(6, 3, 38);

chart.ChartData.SetValue(7, 3, 32);



chart.ChartData.SetValue(1, 4, "2015");

chart.ChartData.SetValue(2, 4, 35);

chart.ChartData.SetValue(3, 4, 37);

chart.ChartData.SetValue(4, 4, 30);

chart.ChartData.SetValue(5, 4, 29);

chart.ChartData.SetValue(6, 4, 25);

chart.ChartData.SetValue(7, 4, 30);

 {% endhighlight %}





After filling these data, the embedded excel sheet looks like the following screenshot. 

![](Getting-started_images/Getting-started_img9.png)


Once the chart data is added, you need to specify the Chart serie and category for chart creation. IOfficeChartSerie interface represents the chart serie and Collection of chart serie that is accessed by the Series property of IOfficeChart interface. The following code example creates three series and set its data range.

 {% highlight c# %}
 
    

//Create a new chart serie with the name “2013”

IOfficeChartSerie serie2013 = chart.Series.Add("2013");

//setting the data range of chart serie 

//This indexer takes 4 parameters – start row, start column, end row, end column

Serie2013.Values = chart.ChartData[2, 2, 7, 2];





IOfficeChartSerie serie2014 = chart.Series.Add("2014");

Serie2014.Values = chart.ChartData[2, 3, 7, 3];



IOfficeChartSerie serie2015 = chart.Series.Add("2015");

Serie2015.Values = chart.ChartData[2, 4, 7, 4];

 {% endhighlight %}





Then set the primary category axis’s data range as follows.

 {% highlight c# %}
 
    

//setting the data range of the category axis

chart.PrimaryCategoryAxis.CategoryLabels = chart.ChartData[2, 1, 7, 1];

 {% endhighlight %}





Finally, save the presentation by using the Save method as follows. In order to release the resources utilized by presentation instance, make sure that the presentation is closed finally.

 {% highlight c# %}
 
    

//Add the third slide into the presentation 

presentation.Save("sample.pptx");

presentation.Close();

 {% endhighlight %}





Now the chart added in the slide looks like chart in the following screenshot.

![](Getting-started_images/Getting-started_img10.png)


# Converting PowerPoint Presentation into PDF document

For converting a Presentation file or a slide into PDF, the following assemblies need to be referenced.

* Syncfusion.Core
* Syncfsuion.Compression.Base
* Syncfusion.OfficeChart.Base
* Syncfusion.Presentation.Base
* Syncfusion.OfficeChartToImageConverter.WPF
* Syncfusion.SfChart.WPF
* Syncfusion.Shared.WPF
* Syncfusion.Pdf.Base
* Syncfusion.PresentationToPDFConverter.Base

PresentationToPdfConverter class is responsible for converting an entire Presentation or a slide into PDF. You can pass the instance of Presentation or slide to the Convert method of PresentationToPdfConverter class and this method returns an instance of PDF document. 

Method Table

<table>
<tr>
<th>
{{ '**Method Name**' | markdownify }}</th><th>
{{ '**Short Description**' | markdownify }}</th></tr>
<tr>
<td>
Convert(ISlide slide)</td><td>
Converts the specified slide into PDF document</td></tr>
<tr>
<td>
Convert(IPresentation presentation)</td><td>
Converts the specified Presentation into PDF document</td></tr>
<tr>
<td>
Convert(IPresentation presentation, PresentationToPdfConverterSettings settings)</td><td>
Converts the specified Presentation into PDF document with respect to settings</td></tr>
</table>


PresentationToPdfConverterSettings is used to customize the conversion of Presentation to PDF document. This settings class has two properties for customizing the conversion.

1. ShowHiddenSlide – When true, converts the hidden slide also.
2. SlidesPerPage – Specifies the number of slides per PDF page.

Instance of ChartToImageConverter class is mandatory to convert the charts present in the presentation to PDF. ChartToImageConverter class resides within Syncfusion.OfficeChartToImageConverter.WPF assembly.  When ChartToImageConverter property of Presentation is not registered with ChartToImageConverter instance as follows, then the charts are not exported to PDF file.

 {% highlight c# %}
 
    

//Open/load a PowerPoint presentation file

IPresentation presentation = Presentation.Open(fileName);



//Create an instance of ChartToImageConverter and assign it to ChartToImageConverter property of Presentation

presentation.ChartToImageConverter = new ChartToImageConverter();

 {% endhighlight %}





The following code example converts the entire presentation into PDF document. It is mandatory to close the instance of PdfDocument and Presentation in order to release the resources occupied. 

 {% highlight c# %}
 
 

//Open/load a PowerPoint presentation file

IPresentation presentation = Presentation.Open(fileName);



//Create an instance of ChartToImageConverter and assign it to ChartToImageConverter property of Presentation

presentation.ChartToImageConverter = new ChartToImageConverter();



//Create an instance of PresentationToPdfConverterSettings

PresentationToPdfConverterSettings settings = new PresentationToPdfConverterSettings();

//set the flag meant for showing hidden slides as true

settings.ShowHiddenSlides = true;

//Set the scaling mode as best

presentation.ChartToImageConverter.ScalingMode = Syncfusion.OfficeChart.ScalingMode.Best;



//convert the PowerPoint presentation into PDF document

PdfDocument PDFdocument = PresentationToPdfConverter.Convert(presentation, settings);



//Save the PDF document

PDFdocument.Save(@"Sample.pdf");

//Close the PDF document & presentation

PDFdocument.Close();

presentation.Close();

 {% endhighlight %}







# Converting Slide into Image

For converting a Presentation or a Slide to Image, the following assemblies need to be referenced.

* Syncfusion.Core
* Syncfsuion.Compression.Base
* Syncfusion.OfficeChart.Base
* Syncfusion.Presentation.Base
* Syncfusion.OfficeChartToImageConverter.WPF
* Syncfusion.SfChart.WPF
* Syncfusion.Shared.WPF

A slide can be converted to image by using the ConvertToImage method of ISlide interface

Method Table

<table>
<tr>
<th>
{{ '**Method Name**' | markdownify }}</th><th>
{{ '**Short description**' | markdownify }}</th></tr>
<tr>
<td>
ConvertToImage(Syncfusion.Drawing.ImageType imageType)</td><td>
Converts the current slide into image and returns an instance of image of the specified ImageType</td></tr>
<tr>
<td>
ConvertToImage(Syncfusion.Drawing.ImageFormat imageFormat)</td><td>
Converts the current slide into image and returns the image as stream.</td></tr>
</table>


Instance of ChartToImageConverter class is mandatory to convert the charts present in the presentation to image. ChartToImageConverter class resides within Syncfusion.OfficeChartToImageConverter.WPF assembly.  If ChartToImageConverter property of Presentation is not registered with ChartToImageConverter instance as follows, then the charts are not appeared in image, it is skipped.

 {% highlight c# %}
 
    

//Open/load a PowerPoint presentation file

IPresentation presentation = Presentation.Open(fileName);



//Create an instance of ChartToImageConverter and assign it to ChartToImageConverter property of Presentation

presentation.ChartToImageConverter = new ChartToImageConverter();

 {% endhighlight %}





The following code example converts the first slide of the PowerPoint presentation into image and save it as a file.

 {% highlight c# %}
 
    

//Open/load a PowerPoint presentation file

IPresentation presentation = Presentation.Open(fileName);



//Create an instance of ChartToImageConverter and assign it to ChartToImageConverter //property of Presentation

presentation.ChartToImageConverter = new ChartToImageConverter();



//Set the scaling mode as best

presentation.ChartToImageConverter.ScalingMode = Syncfusion.OfficeChart.ScalingMode.Best;



//Converts the first slide into image

Image image = presentation.Slides[0].ConvertToImage(Syncfusion.Drawing.ImageType.Metafile);



//save the image as file

image.Save("slide1.png");



//close the presentation instance

presentation.Close();

 {% endhighlight %}







