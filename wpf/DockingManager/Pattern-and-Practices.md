---
layout: post
title: Patterns and Practices | Docking Manager | WPF | Syncfusion
description: Patterns and Practices
platform: wpf
control: DockingManager
documentation: ug
---
# Patterns and Practices

## MVVM 

This section explains how to adapt the Syncfusion docking manager to an MVVM application. Since the WPF DockingManager is not an Itemscontrol, it is not possible to have a traditional `Itemsource` binding to a collection of objects in the view model. This can, however, be achieved by creating a wrapper or adapter for the DockingManager.

Here a simple text-reader application is used to demonstrate this approach. Example:

![](PatternandPractices_images/PatternandPractices_img1.jpeg)


1. `DocumentsView`: The pane that lists all the available documents. The tooltip will display the path of the document.
2. `PropertiesView`: The pane that shows the properties of a document. Our PropertyGrid control is used here.
3. `DocumentView`: The pane that uses the WPF flow-document reader to display the content of a file.
4. `CommandView`: The view has two commands: `Open` Document and `Exit`. Executing an Open Document action will open the Open File Dialog. The document that opened will be added to the existing documents list. Other commands like Close Document and New Document can also be implemented the same way.
5. The project structure looks like this:

![](PatternandPractices_images/PatternandPractices_img2.jpeg)


### Docking Adapter
The adapter is simply a user control that contains docking manager as its content. The adapter has two properties— ItemsSource and ActiveDocument. Binding a collection of objects to the `ItemsSource` property triggers a collection change where the adapter creates a corresponding framework element, example: a Content control, in the docking manager, setting the underlying data context of the control to the business model.

{% highlight xml %}

<mvvm:dockingadapter itemssource="{Binding Workspaces}" activedocument="{Binding ActiveDocument,Mode=TwoWay}">

</mvvm:dockingadapter>



{% endhighlight %}


![](PatternandPractices_images/PatternandPractices_img3.jpeg)


The text-reader application maintains a collection of workspaces. A workspace can be a normal dock pane or a document pane. The adapter also maintains an interface called __IDockElement____,__ that maintains basic attributes needed for every dock element.

The text-reader application is just for the sample and contains very basic operations.

This article and sample intend to showcase the MVVM support for the docking manager.
The adapter user control also determines the state of the element, whether it should be added to the docking manager as a dock element or document tab.

The adapter can be further customized to add elements as floating or auto-hidden.

The docking manager provides an `ActiveWindowChanged` event. Using this, the `ActiveDocument` property in the adapter needs to be updated every time focus changes to other panes.

### Application structure

![](PatternandPractices_images/PatternandPractices_img4.jpeg)


The view model has a collection of workspaces that is data-bound to the `ItemsSource` property of the docking adapter. The adapter transforms the particular view model or business object into a corresponding dock element in the docking manager.

Every dock element in the application is a workspace. There are three kinds of workspaces: the All Documents view, the Properties view, and the Document view. The docking adapter hooks up the “active window changed” event of the docking manager; the view model receives the message whenever the active document is changed.

#### Data Template

Since WPF has an implicit template approach, it is easy to apply visuals to the view models. In this application, the data templates are defined in App.xaml with only the DataType attribute mentioned and not key-specified. The WPF template engine can traverse the tree and find the appropriate model type and apply the templates.

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

#### Sample link

[http://www.syncfusion.com/downloads/Support/DirectTrac/94251/DockingDemo2143110883.zip](http://www.syncfusion.com/downloads/Support/DirectTrac/94251/DockingDemo2143110883.zip)

## Practice with PRISM

The following steps help you create sample project in the PRISM.

1.Create a New WPF project and add the following references to the solution project.

Microsoft.Practices.Composite.dll

Microsoft.Practices.Composite.Presentation.dll

Microsoft.Practices.Composite.UnityExtensions.dll

Microsoft.Practices.ServiceLocation.dll

Microsoft.Practices.Unity.dll

2.Rename MainWindow to Shell in the Project.
3.Add new class called Bootstrapper.cs to initialize the prism application. Here Mainwindow is treated as shell, so returing the mainwindow in the CreateShell method.

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

}





{% endhighlight %}

4.Override Onstartup method in the App.xaml.cs to execute Bootstrapper when the application starts
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

5.Next, create regions in the shell. To do this, first add the following namespace in the shell Window.
{% highlight xml %}

xmlns:prsm="http://www.codeplex.com/prism"





{% endhighlight %}

In the following code example, a region called “MainRegion” has been created to load DockingManager Module views.

{% highlight xml %}
<Window x:Class="DockingManagerPrism.App.MainWindow "

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

xmlns:prsm="http://www.codeplex.com/prism"

Title="MainWindow" Height="350" Width="525">

<Grid>

<syncfusion:DockingManager prsm:RegionManager.RegionName="MainRegion"  DockFill="True">
</syncfusion:DockingManager>

</Grid>

</Window>





{% endhighlight %}

6.Add Module to the project.

Right-click the Solution project, point to “Add” and then click “NewProject”. Then a new window called AddNewProject opens. Select “ClassLibrary” from Visual C#, then rename the project with desired name and click OK. Now a New Module is created in the Solution Project.

Now add following assemblies to the Module project:

* PresentationCore.dll
* PresentationFramework.dll
* WindowsBase.dll

Also add the following Prism assemblies:

* Microsoft.Practices.Composite.dll
* Microsoft.Practices.Composite.Presentation.dll
* Microsoft.Practices.Composite.UnityExtensions.dll
* Microsoft.Practices.ServiceLocation.dll
* Microsoft.Practices.Unity.dll

7.In the Shell project, add the reference to the type of DockingManager module by registering with ModuleCatalog instance in the ConfigureModuleCatalog method.


{% highlight c# %}

protected override void ConfigureModuleCatalog()

{

base.ConfigureModuleCatalog();

ModuleCatalog moduleCatalog = (ModuleCatalog)this.ModuleCatalog;

moduleCatalog.AddModule(typeof(DockingModule));

}



{% endhighlight %}

8.Adding Views to the Module, shown here is bottomleftmodule, similary the view for the module can be added according to number of modules.

{% highlight xml %}
<UserControl x:Class="DockingManagerPrism.Modules.BottomLeftModule"
           xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
           xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
           xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
           xmlns:d="http://schemas.microsoft.com/expression/blend/2008" mc:Ignorable="d"
           xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
           syncfusion:DockingManager.Header="BottomLeftModule" syncfusion:DockingManager.State="Dock"
           syncfusion:DockingManager.SideInDockedMode="Left" d:DesignHeight="300" d:DesignWidth="300">

<Grid>

</Grid>

</UserControl>



{% endhighlight %}

9.Add a region to the shell.

After creating View for the Module, register the view as Module using the following code example.

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

Then when you run the project, it is added as three of the Module in the Shell. The number of modules can be add based on the complexity of the project.

![](PatternandPractices_images/PatternandPractices_img5.jpeg)


