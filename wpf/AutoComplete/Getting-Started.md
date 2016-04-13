---
layout: post 
title: Getting-Started | AutoComplete | wpf | Syncfusion
description: getting started
platform: wpf
control: AutoComplete
documentation: ug
---

# Getting Started

## Structure of the AutoComplete Control

![](Getting-Started_images/Getting-Started_img1.png)

AutoComplete Control Structure
{:.caption}

## Add AutoComplete to an Application

Following are the step-by-step instructions to add an AutoComplete control in a WPF application. The AutoComplete control can be created by using either C#, XAML code. It can also be created using Blend.

### Creating AutoComplete using C#

1. Open Visual Studio, On the File menu click New -> Project. This opens the New Project Dialog box.



   ![](Getting-Started_images/Getting-Started_img2.png)

    Creating New Project
	{:.caption}

2. In the Project Dialog window, select WPF application and, in the Name field type the name of the project. Click OK.

   ![](Getting-Started_images/Getting-Started_img3.png)

    Creating New WPF Application
	{:.caption}



3. Go to Solution Explorer. Right-click References folder and click Add Reference. Add the Syncfusion.Tools.WPF.dll assembly to the project References folder.



   ![](Getting-Started_images/Getting-Started_img4.png)

    Adding Reference
	{:.caption}


   {%highlight xaml%}


         xmlns:syncfusion="clr-namespace:

         Syncfusion.Windows.Tools.Controls;assembly=Syncfusion.Tools.Wpf"
   {%endhighlight%}


4.Add Syncfusion.Tools.WPF reference in XAML and C# code as follows.


   {%highlight c#%}
       using Syncfusion.Windows.Tools.Controls;
   {%endhighlight%}



5.Click and open the C# file. Add AutoComplete to the application.

   {%highlight c#%}

       AutoComplete AutoComplete1 = new AutoComplete();

       List<String> ProductSource = new List<String>();

      customSource.Add("WPF");

      customSource.Add("Chart");

      customSource.Add("GridView");

      customSource.Add("WF");

      customSource.Add("Xlsio");

      customSource.Add("Business Intelligence");

      customSource.Add("Tools");

      customSource.Add("Silverlight");

      customSource.Add("Schedule");

      customSource.Add("Mvc");

      customSource.Add("Pdf");

      this.AutoComplete1.CustomSource = ProductSource;

   {%endhighlight%}
   
   
   ![](Getting-Started_images/Getting-Started_img5.png)
   
   AutoComplete Created Using C#
   {:.caption}


   
### Create AutoComplete using XAML

Following are the steps to create the AutoComplete by using VisualStudio in XAML as follows.

1. Create a new WPF application in Visual Studio. In Visual Studio Toolbox, click SyncfusionWPF Toolbox tab and select AutoComplete.



   ![](Getting-Started_images/Getting-Started_img6.png)


    Select AutoComplete From ToolBox
	{:.caption}


2. Drag-and-drop the AutoComplete to Design View, to add AutoComplete to the application.

   ![](Getting-Started_images/Getting-Started_img7.png)

    AutoComplete Drag and Drop from ToolBox
	{:.caption}



3. You can now customize the properties of AutoComplete in the Properties Window.
   ~~~



         <local:ProductSource x:Key="Src"/>

          <syncfusion:AutoComplete x:Name="AutoComplete1" Source="Custom” CustomSource="{StaticResource Src}"/>
   ~~~
   {:.prettyprint}
    ![](Getting-Started_images/Getting-Started_img8.png)

     AutoComplete Created Using XAML
	 {:.caption}

### Create AutoComplete using Expression Blend

The AutoComplete control provides full Blend support. Here are the step-by-step instructions to create a WPF application in Blend.

1. Open Blend, On the File Menu click New Project. This opens the New Project dialog box.



   ![](Getting-Started_images/Getting-Started_img9.png)

   Create New project in Expression Blend
   {:.caption}



2. In the Project type’s panel, select WPF application and then click OK.



   ![](Getting-Started_images/Getting-Started_img10.png)

    Create New WPF Application in Expression Blend
	{:.caption}



3. Add the following Reference with the sample project.

4. Syncfusion.Tools.WPF.dll

5. On the Window menu, select Assets. This opens the Assets Library dialog box. In the Search box, type AutoComplete. This displays the search results as shown below-.



   ![](Getting-Started_images/Getting-Started_img11.png)
  
    AutoComplete Displayed in Assets window
	{:.caption}


6. Drag the AutoComplete control to the Design View.

   ![](Getting-Started_images/Getting-Started_img12.png)

    AutoComplete Drag & Drop from Asset window
	{:.caption}



7. You can now customize the properties of the AutoComplete in the Properties Window.

   ![](Getting-Started_images/Getting-Started_img13.png)

    Properties Window
	{:.caption}
   


{% highlight xaml %}


<local:ProductSource x:Key="Src"/>
<syncfusion:AutoComplete x:Name="AutoComplete1" Source="Custom” CustomSource="{StaticResource Src}"/>
{% endhighlight %}

{% highlight c# %}



List<String> ProductSource = new List<String>();
customSource.Add("Diagram");customSource.Add("Gauge");
customSource.Add("GridView");customSource.Add("Chart");
customSource.Add("Business Intelligence");
customSource.Add("Schedule");customSource.Add("Grid");
customSource.Add("DocIo");customSource.Add("XlsIo");
customSource.Add("Pdf");
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img14.png)

AutoComplete Created Using Blend
{:.caption}

