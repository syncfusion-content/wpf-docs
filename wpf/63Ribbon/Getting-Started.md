---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: Ribbon
documentation: ug
---

# Getting Started

Topics in this section guide you on getting started with the Ribbon control. It also elaborates on various features and supports provided by the control.

## Why to use our Ribbon control

Here are some highlights of our Ribbon control.

* Provides a ribbon window that overrides the default window and shows the window in Office 2007 style.
* Provides full layout like Office 2007 UI
* RibbonBar is available to structure the layouts
* There can be in two modes:
* LargeButton mode
* SmallButton mode
* Ribbon has a custom implementation of button control as Ribbon Button
* It has curved corners, which resembles the same as the Office ribbon button
* Minimize / Maximize the ribbon
* Keyboard navigation made easy through KeyTips (Super accelerator support)
* QuickAccessToolbar provides placing of items that are used very often.
* OfficeMenu – provides a menu drop-down like the Office2007 menu



## Control Structure



{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }




The different components of the control are described below:

1. Controls
1. BackStage Button – Used to Show/Hide the Backstage
2. QAT -   This area holds the frequently accessed items. The user can add/remove items dynamically.
2. Minimize Ribbon Button - Used to change the state (Minimize/Maximize) of Ribbon
3. Ribbon Status Bar – Displays the status bar items



{ ![](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }




Components of the BackStage view of the control are described below:

1. BackStage Items - The BackStage Items consist of the following:
1. BackStageCommandButton - This button is similar to a control and is used to perform certain task on click.
2. BackStageTabItem - This is a tab like control that comprises of Header and Content area. Header is displayed in the left bar and content occupies the remaining area in the RibbonWindow.



BackStage Corner Image - Image placed at the bottom-right corner of the BackStage area

## Creating the Control through Visual Studio

To create a control using Visual Studio:

Drag and drop the Ribbon control from toolbox to designer. It will generate the Ribbon as shown below:

{ ![](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }




Click on the SmartTag button in the Ribbon. The SmartTag opens as shown below:

{ ![](Getting-Started_images/Getting-Started_img4.png) | markdownify }
{:.image }




The smart tag is used to add and configure items to the Ribbon. The Visual Studio’s (VS’s) property editor is used to configure ribbon properties. The Collection Editor shown in the following screenshot (can be opened by clicking the button in the Items property in the VS property grid) can be used to add items to the Ribbon:



{ ![](Getting-Started_images/Getting-Started_img5.png) | markdownify }
{:.image }




## Creating the Control through Expression Blend

Ribbon control can also be created and configured by using Expression Blend. To create control through the Expression Blend:

1. Create a WPF project in the Expression Blend and add the reference to the following assemblies:
1. Syncfusion.Tools.Wpf
2. Syncfusion.Shared.Wpf
3. Syncfusion.Core



Search the Ribbon in the toolbox.



{ ![](Getting-Started_images/Getting-Started_img6.png) | markdownify }
{:.image }




Drag and drop the Ribbon into the designer. It will create the Ribbon control as shown below:



{ ![](Getting-Started_images/Getting-Started_img7.png) | markdownify }
{:.image }




Add the Ribbon Tabs as follows:

* Select the Ribbon and go to Properties area.
* Click Items (Collection) under Common Properties





{ ![](Getting-Started_images/Getting-Started_img8.png) | markdownify }
{:.image }




The Collection Editor window opens:



{ ![](Getting-Started_images/Getting-Started_img9.png) | markdownify }
{:.image }




1. Click Add Another Item. The Select Object window opens.
2. Select the RibbonTab ( type RibbonTab in the search box ) 
3. Click OK
4. Edit the RibbonTab properties in the Collection Editor window
5. Click OK
6. Choose the RibbonTab and add the required RibbonBars
7. Choose the RibbonBar and add the required controls 
8. The control will be created.
## Configuring Ribbon 


The following topics under this section explain the basic steps to create and configure the Ribbon and its elements. 

### Configuring QAT

This section explains how to create and configure the QAT (Quick Access Toolbar) in Ribbon.

QAT Item

QAT Items can be added as follows: 



[XAML]

&lt;syncfusion:Ribbon.QuickAccessToolBar&gt;

 &lt;syncfusion:QuickAccessToolBar&gt;



    &lt;syncfusion:RibbonButton Label="Undo"/&gt;



     &lt;syncfusion:RibbonButton Label="Redo"/&gt;



  &lt;/syncfusion:QuickAccessToolBar&gt;



&lt;/syncfusion:Ribbon.QuickAccessToolBar&gt;





More Commands Options

QAT items can also be added through More Commands dialog box. 







{ ![](Getting-Started_images/Getting-Started_img10.png) | markdownify }
{:.image }




All items added to the Ribbon will be included in More Commands dialog. This can be avoided by using the ShowInMoreCommands attached property available in the Ribbon as shown below:



[XAML]

&lt;syncfusion:RibbonBar Header="Clipboard" 					syncfusion:Ribbon.ShowInMoreCommands="False"&gt;





QAT Menu Items

QAT Menu Items can be added as follows:



[XAML]

&lt;syncfusion:Ribbon.QuickAccessToolBar&gt;

 &lt;syncfusion:QuickAccessToolBar&gt;



  &lt;syncfusion:QuickAccessToolBar.QATMenuItems&gt;



    &lt;syncfusion:RibbonButton Label="Save"/&gt;



    &lt;syncfusion:RibbonButton Label="Print Preview"/&gt;



  &lt;/syncfusion:QuickAccessToolBar.QATMenuItems&gt;



 &lt;/syncfusion:QuickAccessToolBar&gt;



&lt;/syncfusion:Ribbon.QuickAccessToolBar&gt;





The QAT Menu Items will be displayed as below. After configuring the QAT, it appears as shown in the following image:



{ ![](Getting-Started_images/Getting-Started_img11.png) | markdownify }
{:.image }




### Configuring Application Menu

The topics under this section explain how to create and configure Application Menu in Ribbon.

Populating Left Pane Items

Application Menu’s left pane items can be populated as follows:



[XAML]

&lt;syncfusion:Ribbon.ApplicationMenu&gt;

 &lt;syncfusion:ApplicationMenu Width="38" Height="38" 			ApplicationButtonImage="/Resources/syncfusion.png" IsPopupOpen="False"&gt;         



  &lt;syncfusion:SimpleMenuButton Label="Save" /&gt;



  &lt;syncfusion:SplitMenuButton Label="Save As"&gt;



     &lt;syncfusion:ApplicationMenuGroup Header="Save in another format" 			  IconBarEnabled="False"&gt;



        <syncfusion:SimpleMenuButton  Label="Save As" 

Description="Save a copy of the item to your computer in one of 			the several formates"  />



      &lt;/syncfusion:ApplicationMenuGroup&gt;



  &lt;/syncfusion:SplitMenuButton&gt;



 &lt;/syncfusion:ApplicationMenu&gt;



&lt;/syncfusion:Ribbon.ApplicationMenu&gt;





Populating Bottom Pane Items

Footer items for the Application menu can be added as follows:



[XAML]

&lt;syncfusion:ApplicationMenu.ApplicationItems&gt;

 &lt;syncfusion:RibbonButton SizeForm = "Small" Label="Edit Options"/&gt;



&lt;/syncfusion:ApplicationMenu.ApplicationItems&gt;                                   





Items added to the ApplicationItems collection will be displayed in the footer of the Application Menu.

The Application Menu appears as shown in the following image:



{ ![](Getting-Started_images/Getting-Started_img12.png) | markdownify }
{:.image }


### Configuring the BackStage 

The topics under this section explain how to create and configure the BackStage in Ribbon.

BackStageCommandButton

The BackStageCommandButton can be added to BackStage as follows: 



[XAML]

&lt;syncfusion:Ribbon.BackStage&gt;



 &lt;syncfusion:Backstage Name="RibbonBackStage"&gt;



  &lt;syncfusion:BackStageCommandButton Header="Save"  Command="Save"/&gt;



  &lt;syncfusion:BackStageCommandButton Header="Exit"/&gt;



 &lt;/syncfusion:Backstage&gt;



&lt;/syncfusion:Ribbon.BackStage&gt;                  





BackStageTabItem 

The BackStageTabItem can be added to BackStage as follows.



[XAML]

&lt;syncfusion:Ribbon.BackStage&gt;



 &lt;syncfusion:Backstage Name="RibbonBackStage"&gt;



&lt;!--BackStage Tab item helps to show some contents with header.--&gt;



   &lt;syncfusion:BackstageTabItem Header="Info" &gt;



&lt;!--Back Stage tab item content can be of any type.--&gt;

                        &lt;Grid&gt;



                        &lt;/Grid&gt;



   &lt;/syncfusion:BackstageTabItem&gt;



  &lt;/syncfusion:Backstage&gt;



&lt;/syncfusion:Ribbon.BackStage&gt;                  





## Data Binding 

The topics under this section explain data binding support of Ribbon with Object binding and XML binding.

### Object Binding

Ribbon control supports binding for business objects. 

The following sample illustrates this:

Create a class that acts as a model for RibbonTab. 



[C#]

public class CustomRibbonTab

    {

        public string TabHeader { get; set; }



        public ObservableCollection<CustomRibbonBar> CustomRibbonBars { get; 				set; }



        public CustomRibbonTab()

        {

            CustomRibbonBars = new ObservableCollection<CustomRibbonBar>();

        }



    }





Create a class that acts as a model for RibbonBar. 



[C#]

public class CustomRibbonBar

    {

        public string BarHeader { get; set; }



        public ObservableCollection<CustomRibbonItem> CustomRibbonItems { 				get; set; }



        public CustomRibbonBar()

        {

            CustomRibbonItems = new ObservableCollection<CustomRibbonItem>();

        }



    }





Create a Class that acts as a model for RibbonItem. 



[C#]

public class CustomRibbonItem

    {

        public string ItemHeader

        {

            get; set;

        }



        public bool IsBoolean { get; set; }



        public bool IsLarge { get; set; }

    }





Iinitialize the Ribbon Items in the ViewModel class as follows:



[C#]

public class ViewModel

    {

        public ObservableCollection<CustomRibbonTab> CustomRibbonTabs { get; 				set; }



        public ViewModel()

        {

            CustomRibbonTabs = new ObservableCollection<CustomRibbonTab>();

            PopulateRibbonTabs();

        }

        void PopulateRibbonTabs()

        {

            CustomRibbonTab cTab1 = new CustomRibbonTab() { TabHeader = 				"Tab1" };



            PopulateRibbonBars(cTab1);



            CustomRibbonTab cTab2 = new CustomRibbonTab() { TabHeader = 				"Tab2" };



            PopulateRibbonBars(cTab2);



            CustomRibbonTabs.Add(cTab1);



            CustomRibbonTabs.Add(cTab2);

        }



        void PopulateRibbonBars(CustomRibbonTab cTab)

        {

            CustomRibbonBar cBar1 = new CustomRibbonBar() { BarHeader = 				cTab.TabHeader + " - Bar1" };



            PopuplateRibbonItems(cBar1);



            CustomRibbonBar cBar2 = new CustomRibbonBar() { BarHeader = 				cTab.TabHeader + " - Bar2" };



            PopuplateRibbonItems(cBar2);



            CustomRibbonBar cBar3 = new CustomRibbonBar() { BarHeader = 				cTab.TabHeader + " - Bar3" };



            PopuplateRibbonItems(cBar3);



            cTab.CustomRibbonBars.Add(cBar1);



            cTab.CustomRibbonBars.Add(cBar2);



            cTab.CustomRibbonBars.Add(cBar3);



        }

        void PopuplateRibbonItems(CustomRibbonBar cBar)

        {

            CustomRibbonItem cItem1 = new CustomRibbonItem() { ItemHeader = 				cBar.BarHeader + " - Item1 " };



            CustomRibbonItem cItem2 = new CustomRibbonItem() { ItemHeader = 				cBar.BarHeader + " - Item2 " , IsBoolean= true};



            CustomRibbonItem cItem3 = new CustomRibbonItem() { ItemHeader = 				cBar.BarHeader + " - Item3 ", IsLarge= true};          



            cBar.CustomRibbonItems.Add(cItem1);



            cBar.CustomRibbonItems.Add(cItem2);



            cBar.CustomRibbonItems.Add(cItem3);



        }

    }







Create an instance of the ViewModel class and set it as DataContext for the RibbonWindow. 

Set the ItemsSource of the Ribbon , RibbonTab and RibbonBar to the corresponding collection as given in the following code snippet:



[XAML]

<syncfusion:RibbonWindow x:Class="RibbonDataBindingDemo.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"        

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" 

        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

        syncfusion:SkinStorage.VisualStyle="Office2010Blue"

        xmlns:local="clr-namespace: RibbonDataBindingDemo "

        Title="MainWindow" Height="350" Width="525" >





&lt;syncfusion:RibbonWindow.DataContext&gt;

   &lt;local:ViewModel/&gt;

&lt;/syncfusion:RibbonWindow.DataContext&gt;    



 <syncfusion:Ribbon Grid.Row="0" 

                   Name="Ribbon1"                    

                   ItemsSource="{Binding CustomRibbonTabs}">



  &lt;syncfusion:Ribbon.ItemContainerStyle&gt;



   &lt;Style TargetType="{x:Type syncfusion:RibbonTab}"&gt;



    &lt;Setter Property="Caption" Value="{Binding TabHeader}"&gt;&lt;/Setter&gt;

    &lt;Setter Property="Foreground" Value="Red"&gt;&lt;/Setter&gt;

    &lt;Setter Property="ItemsSource" Value="{Binding CustomRibbonBars}"/&gt;

    &lt;Setter Property="ItemContainerStyle"&gt;

      &lt;Setter.Value&gt;



       &lt;Style TargetType="{x:Type syncfusion:RibbonBar}"&gt;

        &lt;Setter Property="Header" Value="{Binding BarHeader}"/&gt;

        &lt;Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/&gt;

        &lt;Setter Property="ItemTemplate"&gt;

          &lt;Setter.Value&gt;

            &lt;DataTemplate&gt;

               &lt;syncfusion:RibbonButton Label="{Binding ItemHeader}"/&gt;

             &lt;/DataTemplate&gt;

          &lt;/Setter.Value&gt;

        &lt;/Setter&gt;

       &lt;/Style&gt;



      &lt;/Setter.Value&gt;

     &lt;/Setter&gt;

    &lt;/Style&gt;

   &lt;/syncfusion:Ribbon.ItemContainerStyle&gt;

  &lt;/syncfusion:Ribbon&gt;

 &lt;/syncfusion:RibbonWindow&gt;





The Ribbon is displayed as shown in the following screenshot:



{ ![](Getting-Started_images/Getting-Started_img13.png) | markdownify }
{:.image }


### XML Binding

XML file can also be used as ItemsSource for the Ribbon. The following example illustrates this:

1. Create an xml file with the following details and name it as Data.xml.



[XML]

&lt;?xml version="1.0" encoding="utf-8" ?&gt;

&lt;RibbonTabs&gt;



  &lt;TabCategory Name="Book Rental"&gt;



    &lt;BarCategory Name="Rental"&gt;

      &lt;Command Name="Add to Bookshelf"/&gt;

      &lt;Command Name="My BookShelf"/&gt;

      &lt;Command Name="Popular Books"/&gt;

      &lt;Command Name="Latest Additions"/&gt;

      &lt;Command Name="Price Winning Books"/&gt;

    &lt;/BarCategory&gt;



    &lt;BarCategory Name="How it works"&gt;

      &lt;Command Name="Request a book"/&gt;

      &lt;Command Name="Receive"/&gt;

    &lt;/BarCategory&gt;



  &lt;/TabCategory&gt;



  &lt;TabCategory Name="Account Settings"&gt;



    &lt;BarCategory Name="My Account"&gt;

      &lt;Command Name="Sign in"/&gt;

      &lt;Command Name="Deactivate"/&gt;

    &lt;/BarCategory&gt;



    &lt;BarCategory Name="Security"&gt;

      &lt;Command Name="Enable Secure surfing"/&gt;

      &lt;Command Name="Change Password"/&gt;

    &lt;/BarCategory&gt;



  &lt;/TabCategory&gt;  



&lt;/RibbonTabs&gt;





2. Add the XmlDataProvider for the above XML document as given in the following code snippet:



[XAML]

&lt;XmlDataProvider Source="Data/Data.xml" x:Key="xmlSource" XPath="RibbonTabs"/&gt; 





3. Set the ItemsSource property for the Ribbon, RibbonTab and RibbonBar as shown in the below code snippet:



[XAML]

<syncfusion:Ribbon 

     	x:Name="ribbon" 

     	ItemsSource="{Binding Source={StaticResource xmlSource}, 			            	XPath=TabCategory}">



 &lt;syncfusion:Ribbon.ItemContainerStyle&gt;



  &lt;Style TargetType="{x:Type syncfusion:RibbonTab}"&gt;



   &lt;Setter Property="ItemsSource" Value="{Binding XPath=BarCategory}" /&gt;



    &lt;Setter Property="ItemContainerStyle"&gt;



     &lt;Setter.Value&gt;



       &lt;Style TargetType="{x:Type syncfusion:RibbonBar}"&gt;                                



         &lt;Setter Property="ItemsSource" Value="{Binding XPath=Command}"/&gt;                               



           &lt;Setter Property="ItemTemplate"&gt;



             &lt;Setter.Value&gt;



                 &lt;DataTemplate&gt;



                  &lt;syncfusion:RibbonButton Label="{Binding XPath=@Name}"/&gt;                                            



                 &lt;/DataTemplate&gt;



             &lt;/Setter.Value&gt;



           &lt;/Setter&gt;



        &lt;Setter Property="Header" Value="{Binding XPath=@Name}"/&gt;



      &lt;/Style&gt;



    &lt;/Setter.Value&gt;



   &lt;/Setter&gt;



   &lt;Setter Property="Caption" Value="{Binding XPath=@Name}"/&gt;



  &lt;/Style&gt;



 &lt;/syncfusion:Ribbon.ItemContainerStyle&gt;



&lt;/syncfusion:Ribbon&gt;



A Ribbon is created as shown in the following screenshot:



{ ![](Getting-Started_images/Getting-Started_img14.png) | markdownify }
{:.image }


## Customizing Data Templates

This section explains how to customize Ribbon and its elements using templates.

### Item Template 

It is possible to set the ItemTemplate for the RibborBar to control the display of the data that is bound to the RibbonBar. Since the RibbonBar can contain any UI Elements, the ItemTemplate is used to define the UI Elements to hold the data. 



[XAML]

       &lt;Style TargetType="{x:Type syncfusion:RibbonBar}"&gt;

        &lt;Setter Property="Header" Value="{Binding BarHeader}"/&gt;

        &lt;Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/&gt;

        &lt;Setter Property="ItemTemplate"&gt;

          &lt;Setter.Value&gt;

            &lt;DataTemplate&gt;

               &lt;syncfusion:RibbonButton Label="{Binding ItemHeader}"/&gt;

             &lt;/DataTemplate&gt;

          &lt;/Setter.Value&gt;

        &lt;/Setter&gt;

       &lt;/Style&gt;







### Item Template Selector

This feature enables you to use different templates for items depending on specific constraints. The following example illustrates this: 

Create the template selector as shown in the following code snippet:



[C#]

public class RibbonItemTemplateSelector : DataTemplateSelector



    {

        public override DataTemplate SelectTemplate(object item, 							DependencyObject container)

        {

            Window window = Application.Current.MainWindow;



            if (((CustomRibbonItem)item).IsBoolean)

            {

                return ((DataTemplate)window.Resources["BooleanTemplate"]);

            }

            else if(((CustomRibbonItem)item).IsLarge)

            {

      	     return 							((DataTemplate)window.Resources["LargeButtonTemplate"]);

            }

            else

                return 									((DataTemplate)window.Resources["SmallButtonTemplate"]);



        }

    }









Define Data templates in the Window’s resources as follows:



[XAML]

&lt;DataTemplate x:Key="SmallButtonTemplate"&gt;

 &lt;syncfusion:RibbonButton SizeForm="Small" Label="{Binding ItemHeader}"/&gt;

&lt;/DataTemplate&gt;



&lt;DataTemplate x:Key="LargeButtonTemplate"&gt;

  &lt;syncfusion:RibbonButton SizeForm="Large" Label="{Binding ItemHeader}"/&gt;

&lt;/DataTemplate&gt;



&lt;DataTemplate x:Key="BooleanTemplate"&gt;

  &lt;syncfusion:RibbonCheckBox  Content="{Binding ItemHeader}"/&gt;

&lt;/DataTemplate&gt;





 Create the instance for the template selector in the Window’s resources as follows:



[XAML]

&lt;local:RibbonItemTemplateSelector x:Key="ribbonItemTemplateSelector"/&gt;





Use this template selector to choose template for the RibbonBar as follows:



[XAML]

&lt;syncfusion:Ribbon Name="Ribbon1"                                       		ItemsSource="{Binding CustomRibbonTabs}"&gt;

 &lt;syncfusion:Ribbon.ItemContainerStyle&gt;



  &lt;Style TargetType="{x:Type syncfusion:RibbonTab}"&gt;



   &lt;Setter Property="Caption" Value="{Binding TabHeader}"&gt;&lt;/Setter&gt;

   &lt;Setter Property="Foreground" Value="Red"&gt;&lt;/Setter&gt;

   &lt;Setter Property="ItemsSource" Value="{Binding CustomRibbonBars}"/&gt;

   &lt;Setter Property="ItemContainerStyle"&gt;

     &lt;Setter.Value&gt;



       &lt;Style TargetType="{x:Type syncfusion:RibbonBar}"&gt;

         &lt;Setter Property="Header" Value="{Binding BarHeader}"/&gt;

         &lt;Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/&gt;

         &lt;Setter Property="ItemTemplateSelector" Value="{StaticResource 				ribbonItemTemplateSelector}"/&gt;                                                     

       &lt;/Style&gt;

      &lt;/Setter.Value&gt;

    &lt;/Setter&gt;

   &lt;/Style&gt;

  &lt;/syncfusion:Ribbon.ItemContainerStyle&gt;

&lt;/syncfusion:Ribbon&gt;





A ribbon generates as shown in the following screenshot:



{ ![](Getting-Started_images/Getting-Started_img15.png) | markdownify }
{:.image }


## Styling

The topics under this section explain how to customize the Ribbon using styles.

Visual Style

Ribbon supports the following built-in Visual Styles:

* Office2007Blue
* Office2007Black
* Office2007Silver
* Office2010Blue
* Office2010Black
* Office2010Silver
* Blend
* VS2010
* Metro
* Transparent



Visual Styles can be applied via XAML as follows:



[XAML]

syncfusion:SkinStorage.VisualStyle="Office2010Blue"



The VisualStyle attached property available in the SkinStorage class is used to set the Visual Styles for the controls. 

The following code snippet shows how to set the visual style in XAML:



[XAML]

&lt;syncfusion:RibbonWindow x:Class="BackStageSample.MainWindow"        syncfusion:SkinStorage.VisualStyle="Office2010Blue"        Title="BackStage Demo"  xmlns:syncfusion="http://schemas.syncfusion.com/wpf" /&gt;    





Now, the RibbonWindow and the controls inside the RibbonWindow get the Office2010Blue look.

Visual styles can be set using C# as follows:



[C#]

SkinStorage.SetVisualStyle(ribbonWindowInstance, "Office2010Blue");





## Class Diagram

The class diagram for Ribbon controls are as follows.



{ ![](Getting-Started_images/Getting-Started_img16.jpeg) | markdownify }
{:.image }






{ ![](Getting-Started_images/Getting-Started_img17.jpeg) | markdownify }
{:.image }


