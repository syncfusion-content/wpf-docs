---
layout: post
title: Patterns and Practices
description: Patterns and Practices
platform: wpf
control: DockingManager
documentation: ug
---
## Patterns and Practices

### MVVM 

This session explains how to adapt the Syncfusion docking manager to an MVVM application. Since the WPF DockingManager is not an __item__ __control__, it is not possible to have a traditional **"Itemsource"** binding to a collection of objects in the view model. This can, however, be achieved by creating a wrapper or adapter for the DockingManager.

Here a simple text-reader application is used to demonstrate this approach. The sample looks like this:

![](PatternandPractices_images/PatternandPractices_img1.jpeg)


1. **Documents** **View**: The pane that lists all the available documents. The tooltip will display the path of the document.
2. ******Properties** **View**: The pane that shows the properties of a document. Our PropertyGrid control is used here.
3. **Document** **View**: The pane that uses the WPF flow-document reader to display the content of a file.
4. **Command** **View**: The view has two commands: **Open** **Document** and **Exit**. Executing an **Open** **Document** action will open the **Open** **File** **Dialog**. The document that opened will be added to the existing documents list. Other commands like **Close** **Document** and **New** **Document** can also be implemented the same way.
5. The project structure looks like this:

![](PatternandPractices_images/PatternandPractices_img2.jpeg)


**Docking** **Adapter** 
The adapter is simply a user control that contains our docking manager as its content. The adapter has two properties— **ItemsSource** and **ActiveDocument**. Binding a collection of objects to the **ItemsSource** property will trigger a collection change in which the adapter will create a corresponding framework element (e.g., a Content control) in the docking manager, setting the underlying data context of the control to the business model.

{% highlight xml %}

<mvvm:dockingadapter itemssource="{Binding Workspaces}" activedocument="{Binding ActiveDocument,Mode=TwoWay}">

</mvvm:dockingadapter>



{% endhighlight %}

<table>
<tr>
<td>
<br/><br/></td></tr>
</table>
![](PatternandPractices_images/PatternandPractices_img3.jpeg)


Our text-reader application maintains a collection of workspaces. A workspace can be a normal dock pane or a document pane. The adapter also maintains an interface called __IDockElement____,__ which maintains basic attributes needed for every dock element.

(The__ __text____-____reader__ __application__ __is__ __just__ __for__ __the__ __sample__ __and__ __contains__ __very__ __basic__ __operations.

__This__ __article__ __and__ __sample__ __intend__ __to__ __showcase__ __the__ __MVVM__ __support__ __for__ __the__ __docking__ __manager.)

The adapter user control also determines the state of the element, whether it should be added to the docking manager as a dock element or document tab.

__(__The__ __adapter__ __can__ __be__ __further__ __customized__ __to__ __add__ __elements__ __as__ __floating__ __or__ __auto____-____hidden__.)__

The docking manager provides an **ActiveWindowChanged** event. Using this, the **ActiveDocument** property in the adapter needs to be updated every time focus changes to other panes.

**Application** **structure**

![](PatternandPractices_images/PatternandPractices_img4.jpeg)


The view model has a collection of workspaces that is data-bond to the **ItemsSource** property of the docking adapter. The adapter transforms the particular view model or business object into a corresponding dock element in the docking manager.

Every dock element we see in the application is a workspace. There are three kinds of workspaces: the All Documents view, the Properties view, and the Document view. The docking adapter hooks up the “active window changed” event of the docking manager; the view model receives the message whenever the active document is changed.

**Data** **Template** 

Since WPF has an implicit template approach, it is easy for us to apply visuals to the view models. In this application, the data templates are defined in **App.xaml** with only the **DataType** attribute mentioned and not key-specified. The WPF template engine will traverse the tree and find the appropriate model type and apply the templates.

{% highlight xml %}
<application.resources>

<datatemplate datatype="{x:Type local:Document}">

<grid>

<local:documentview>

</local:documentview></grid>

</datatemplate>

<datatemplate datatype="{x:Type local:DocumentsViewModel}">

<grid>

<local:documentsview>

</local:documentsview></grid>

</datatemplate>

<datatemplate datatype="{x:Type local:PropertiesViewModel}">

<grid>

<local:propertiesview>

</local:propertiesview></grid>

</datatemplate>

</application.resources>



{% endhighlight %}

Following this approach, the docking adapter can also be treated as a normal item control and can be used in any MVVM application.

**Sample** **link**

[http://www.syncfusion.com/downloads/Support/DirectTrac/94251/DockingDemo2143110883.zip](http://www.syncfusion.com/downloads/Support/DirectTrac/94251/DockingDemo2143110883.zip# "")

### Practice with PRISM

The following steps will help to create sample project in the PRISM.

1. Create a New WPF project and add the following references to the solution project.

Microsoft.Practices.Composite.dll

Microsoft.Practices.Composite.Presentation.dll

Microsoft.Practices.Composite.UnityExtensions.dll

Microsoft.Practices.ServiceLocation.dll

Microsoft.Practices.Unity.dll

2. Rename MainWindow to Shell in the Project
3. Add new class called Bootstrapper.cs to initialize the prism application. Here Mainwindow is treated as shell, so returing the mainwindow in the CreateShell method.

{% highlight c# %}

public class BootStrapper : UnityBootstrapper

{

protected override System.Windows.DependencyObject CreateShell()

{

return new MainWindow();

}

protected override void InitializeModules()

{

base.InitializeModules();

App.Current.MainWindow = (Window)this.Shell;

App.Current.MainWindow.Show();

}





{% endhighlight %}

4. Override Onstartup method in the App.xaml.cs to execute Bootstrapper when the application starts
{% highlight c# %}

public partial class App : Application

{

protected override void OnStartup(StartupEventArgs e)

{

base.OnStartup(e);

Bootstrapper bootstrapper = new Bootstrapper();

bootstrapper.Run();

}

}





{% endhighlight %}

5. Next step is to create regions in the shell. To do this, first add the following namespace in the shell Window
{% highlight xml %}

xmlns:prsm="http://www.codeplex.com/prism"





{% endhighlight %}

In the below code, a region called “MainRegion” has been created to load DockingManager Module views

{% highlight xml %}
<Window x:Class="DockingManagerPrism.App.MainWindow "

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

xmlns:prsm="http://www.codeplex.com/prism"

Title="MainWindow" Height="350" Width="525">

<Grid>

<syncfusion:DockingManager prsm:RegionManager.RegionName="MainRegion"  DockFill="True"></syncfusion:DockingManager>

</Grid>

</Window>





{% endhighlight %}

6. Adding Module to the project

Right click the Solution project, point to “Add” and then click “NewProject”.Then NewWindow called AddNewProject will open.Select “ClassLibrary” from Visual C# .then rename the project with desired name and click OK.Now a New Module will be created in the Solution Project

Now add following assemblies to the Module project

* PresentationCore.dll
* PresentationFramework.dll
* WindowsBase.dll

Also add following Prism assemblies

* Microsoft.Practices.Composite.dll
* Microsoft.Practices.Composite.Presentation.dll
* Microsoft.Practices.Composite.UnityExtensions.dll
* Microsoft.Practices.ServiceLocation.dll
* Microsoft.Practices.Unity.dll

7. In the Shell project, add the reference to the type of DockingManager module by registering with ModuleCatalog instance in the ConfigureModuleCatalog method


{% highlight c# %}

protected override void ConfigureModuleCatalog()

{

base.ConfigureModuleCatalog();

ModuleCatalog moduleCatalog = (ModuleCatalog)this.ModuleCatalog;

moduleCatalog.AddModule(typeof(DockingModule));

}



{% endhighlight %}

8. Adding Views to the Module, here shows bottomleftmodule, similary the view for the module can be added according to numer of module

{% highlight xml %}
<UserControl x:Class="DockingManagerPrism.Modules.BottomLeftModule"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"

xmlns:d="http://schemas.microsoft.com/expression/blend/2008"

mc:Ignorable="d"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

syncfusion:DockingManager.Header="BottomLeftModule"

syncfusion:DockingManager.State="Dock"

syncfusion:DockingManager.SideInDockedMode="Left"

d:DesignHeight="300" d:DesignWidth="300">

<Grid>

</Grid>

</UserControl>



{% endhighlight %}

9. Add a region to the shell

After creating View for the Module, register the view as Module using the below code.

{% highlight c# %}
public class DockingModule : IModule

{

private readonly IRegionManager regionManager;

public DockingModule(IRegionManager regionManager)

{

this.regionManager = regionManager;

}

public void Initialize()

{

regionManager.RegisterViewWithRegion("MainRegion", typeof(BottomLeftModule));

regionManager.RegisterViewWithRegion("MainRegion", typeof(BottomRightModule));

regionManager.RegisterViewWithRegion("MainRegion", typeof(TopModule));

}

}



{% endhighlight %}

Then Run the project will get added as three of the Module in the Shell.The number of modules can be add based on the complexity of the project.

![](PatternandPractices_images/PatternandPractices_img5.jpeg)


