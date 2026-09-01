---
layout: post
title: Serialization and Deserialization in WPF Ribbon Control | Syncfusion®
description: Serialization and Deserialization in Ribbon lets you save and load the ribbon state, tab order, and QAT items to persist UI.
platform: wpf
control: Ribbon
documentation: ug
---

# Serialization and Deserialization in WPF Ribbon Control

State persistence is a combined process of serialization and deserialization. Serialization is the process of converting the state of the object to the format in which it can be stored as a file in the memory. Deserialization is a complementary process of serialization that converts the stored state information back into an object.

The WPF Ribbon Control provides built-in serialization support for saving and restoring its state, including layout mode settings. It also allows the control to be saved and loaded at runtime in either simplified or normal layout mode.

The following WPF Ribbon Control states can persist separately.


1. Quick Access Tool Bar

   a. Quick Access Tool Bar Items

   b. Quick Access Tool Bar State (Above Ribbon, Below Ribbon)

2. WPF Ribbon Control

   a. WPF Ribbon Control State (Normal, Hide)

   b. Layout Mode (Normal, Simplified)

3. RibbonWindow

   a. Window Width

   b. Window Height

   c. Window Left

   d. Window Top


## Use case scenarios

The State Persistence feature helps users to load the state of the WPF Ribbon Control that existed when the application was closed. State Persistence feature gives a more consistent workflow for an application that is executed for a long time.

### Persist WPF Ribbon Control states at application exit and load

The WPF Ribbon Control provides the `AutoPersist` property to persist control states when the application closes and restore them when it loads. Persistence can also be managed individually through the AutoPersist property in the WPF Ribbon Control, QAT, and RibbonWindow.

The following code example demonstrates how to configure the AutoPersist property for WPF Ribbon Control elements, including the QAT and RibbonWindow.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonStatePersistence.MainWindow"
Title="MainWindow" Height="350" Width="525" AutoPersist="True" x:Name="RibbonWindow" WindowStyle="SingleBorderWindow" WindowStartupLocation="CenterScreen" WindowState="Normal" syncfusion:SkinStorage.VisualStyle="Office2013" Loaded="RibbonWindow_Loaded">
<Grid>
<syncfusion:Ribbon x:Name="MyRibbon" AutoPersist="True" VerticalAlignment="Top">
<syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:QuickAccessToolBar AutoPersist="True">
</syncfusion:QuickAccessToolBar>
</syncfusion:Ribbon.QuickAccessToolBar>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

## Persist WPF Ribbon Control states any time while running the application

WPF Ribbon Control supports the persistence of its states any time while running the application. WPF Ribbon Control states can be saved and loaded at any time by using `SaveRibbonState` and `LoadRibbonState` methods

Before calling the methods, it is important to specify the persisting WPF Ribbon Control elements in `PersistElements` collection.This collection can be changed at any time. Save and Load states at runtime are fully based on this collection details. The following code snippet shows how to add elements that are required to retain its state.

{% tabs %}

{% highlight C# %}

private void RibbonWindow_Loaded(object sender, RoutedEventArgs e)
{
    this.MyRibbon.PersistElements.Add(RibbonElements.Ribbon);
    this.MyRibbon.PersistElements.Add(RibbonElements.RibbonWindow);
    this.MyRibbon.PersistElements.Add(RibbonElements.QuickAccessToolbar);
}

{% endhighlight %}

{% highlight VB %}

Private Sub RibbonWindow_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
Me.MyRibbon.PersistElements.Add(RibbonElements.Ribbon)
Me.MyRibbon.PersistElements.Add(RibbonElements.RibbonWindow)
Me.MyRibbon.PersistElements.Add(RibbonElements.QuickAccessToolbar)
End Sub

{% endhighlight %}

{% endtabs %}

## Saving WPF Ribbon Control states

The WPF Ribbon Control State can be saved and loaded dynamically at run time. To save the current State, use `SaveRibbonState` method.

This method has two overloaded methods for customizing the Save state process as follows:

1. void SaveRibbonState()

2. void SaveRibbonState(IsolatedStorageFile isoStorage, string storeFileName)


In the first method, there is no parameters. Current state of the WPF Ribbon Control is saved to the default Isolated Storage file, which is built in the source.

{% tabs %}

{% highlight C# %}

private void SaveRibbonState_Click(object sender, RoutedEventArgs e)
{
    this.MyRibbon.SaveRibbonState();
}

{% endhighlight %}

{% highlight VB %}

Private Sub SaveRibbonState_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
Me.MyRibbon.SaveRibbonState()
End Sub

{% endhighlight %}

{% endtabs %}

To store the current WPF Ribbon Control State in the custom Isolated Storage file, use the second overloaded method. This method has two arguments namely IsolatedStorageFile and storeFileName.

{% tabs %}

{% highlight C# %}

private void SaveRibbonState_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.SaveRibbonState(storage,"Customfilename.dat");
}

{% endhighlight %}

{% highlight VB %}

Private Sub SaveRibbonState_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.SaveRibbonState(storage,"Customfilename.dat")
End Sub

{% endhighlight %}

{% endtabs %}

### Loading WPF Ribbon Control states

Load state process is also having the similar procedures of save states. We can load the State at any time from the last saved Isolated Storage file. `LoadRibbonState` method is used to load the WPF Ribbon Control state from the last saved state. This method has two overloaded methods as follows:

1. void LoadRibbonState()

2. void LoadRibbonState(IsolatedStorageFile isoStorage, string storeFileName)

The first method with no arguments loads the WPF Ribbon Control State from the last saved state in the default Isolated Storage file, which is stored by the SaveRibbonState method.

{% tabs %}

{% highlight C# %}

private void LoadRibbonState_Click(object sender, RoutedEventArgs e)
{
    this.MyRibbon.LoadRibbonState();
}

{% endhighlight %}

{% highlight VB %}

Private Sub LoadRibbonState_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
Me.MyRibbon.LoadRibbonState()
End Sub

{% endhighlight %}

{% endtabs %}

The second overloaded method loads the WPF Ribbon Control State from the given file name in the mentioned Isolated Storage file.

{% tabs %}

{% highlight C# %}

private void LoadRibbonState_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.LoadRibbonState(storage, "Customfilename.dat");
}

{% endhighlight %}

{% highlight VB %}

Private Sub LoadRibbonState_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.LoadRibbonState(storage, "Customfilename.dat")
End Sub

{% endhighlight %}

{% endtabs %}

## Save and load many WPF Ribbon Control states

WPF Ribbon Control states can easily be maintained in the Isolated Storage files. Further, It supports to Save the consecutive or different states of the WPF Ribbon Control in different Isolated Storage files and also load any saved state from the Isolated Storage files which is in old state.

{% tabs %}

{% highlight C# %}

private void SaveLevel1State_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.SaveRibbonState(storage,"RibbonState1.dat");
}
private void SaveLevel2State_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.SaveRibbonState(storage, "RibbonState2.dat");
}
private void SaveLevel3State_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.SaveRibbonState(storage, "RibbonState3.dat");
}

{% endhighlight %}

{% highlight VB %}

Private Sub SaveLevel1State_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.SaveRibbonState(storage,"RibbonState1.dat")
End Sub
Private Sub SaveLevel2State_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.SaveRibbonState(storage, "RibbonState2.dat")
End Sub
Private Sub SaveLevel3State_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.SaveRibbonState(storage, "RibbonState3.dat")
End Sub

{% endhighlight %}

{% endtabs %}

After saving the different states of the WPF Ribbon Control, load the WPF Ribbon Control state to any of the old states

{% tabs %}

{% highlight C# %}

private void LoadLevel1State_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.LoadRibbonState(storage, "RibbonState1.dat");
}
private void LoadLevel2State_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.LoadRibbonState(storage, "RibbonState2.dat");
}
private void LoadLevel3State_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.LoadRibbonState(storage, "RibbonState3.dat");
}

{% endhighlight %}

{% highlight VB %}

Private Sub LoadLevel1State_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.LoadRibbonState(storage, "RibbonState1.dat")
End Sub
Private Sub LoadLevel2State_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.LoadRibbonState(storage, "RibbonState2.dat")
End Sub
Private Sub LoadLevel3State_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.LoadRibbonState(storage, "RibbonState3.dat")
End Sub

{% endhighlight %}

{% endtabs %}

## Persisting WPF Ribbon Control states by XML writer

The WPF Ribbon Control supports state persistence in the XML file created by the user. The states can be saved and loaded in the XML file by overloading the following methods:

* SaveRibbonState(XmlWriter xmlWriter)
* LoadRibbonState(XmlReader xmlReader)

The following code illustrates this 

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="PART_Ribbon" VerticalAlignment="Top">
<syncfusion:Ribbon.PersistElements>
<syncfusion:RibbonElements>QuickAccessToolbar</syncfusion:RibbonElements>
</syncfusion:Ribbon.PersistElements>
<syncfusion:Ribbon.BackStage>
<syncfusion:Backstage />
</syncfusion:Ribbon.BackStage>
<syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:QuickAccessToolBar />
</syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:RibbonTab Caption="RibbonTab">
<syncfusion:RibbonBar Header="RibbonBar">
<syncfusion:SplitButton Label="SplitButton" SizeForm="Large">
<syncfusion:RibbonMenuItem Header="RibbonMenuItem" />
</syncfusion:SplitButton>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="Disk" IsChecked="False">
<syncfusion:RibbonBar>
<syncfusion:RibbonButton Click="OnSaveDisk" Label="Save to disk" />
<syncfusion:RibbonButton Click="OnLoadDisk" Label="Load from disk" />
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private const string SaveLocation = @"D:\temp1.xml";
private void OnLoadDisk(object sender, RoutedEventArgs e)
{
    if (!File.Exists(SaveLocation))
    {
        return;
    }
    using (var reader = new StringReader(File.ReadAllText(SaveLocation)))
    {
        this.PART_Ribbon.LoadRibbonState(reader);
    }
}
private void OnSaveDisk(object sender, RoutedEventArgs e)
{
    using (var stream = new FileStream(SaveLocation, FileMode.Create))
    using (var writer = XmlWriter.Create(stream))
    {
        this.PART_Ribbon.SaveRibbonState(writer);
    }
}

{% endhighlight %}

{% highlight VB %}

Private Const SaveLocation As String = "D:\temp1.xml"
Private Sub OnLoadDisk(ByVal sender As Object, ByVal e As RoutedEventArgs)
If Not File.Exists(SaveLocation) Then
Return
End If
Using reader = New StringReader(File.ReadAllText(SaveLocation))
Me.PART_Ribbon.LoadRibbonState(reader)
End Using
End Sub
Private Sub OnSaveDisk(ByVal sender As Object, ByVal e As RoutedEventArgs)
Using stream = New FileStream(SaveLocation, FileMode.Create)
Using writer = XmlWriter.Create(stream)
Me.PART_Ribbon.SaveRibbonState(writer)
End Using
End Using
End Sub

{% endhighlight %}

{% endtabs %}

## Reset WPF Ribbon Control States

To load the Normal (Initial) state at runtime call the `ResetRibbonState` method. This is a parameter less method. This loads the Normal state of the WPF Ribbon Control. Resetting the state is applicable while `AutoPersist` is enabled in WPF Ribbon Control elements.

{% tabs %}

{% highlight C# %}

private void ResetState_Click(object sender, RoutedEventArgs e)
{
    this.MyRibbon.ResetRibbonState();
}

{% endhighlight %}

{% highlight VB %}

Private Sub ResetState_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
Me.MyRibbon.ResetRibbonState()
End Sub

{% endhighlight %}

{% endtabs %}


## Delete WPF Ribbon Control states

To delete the unused saved Isolated Storage files, use the DeleteRibbonState method.

{% tabs %}

{% highlight C# %}

private void DeleteRibbonState_Click(object sender, RoutedEventArgs e)
{
    this.MyRibbon.DeleteRibbonState();
}

{% endhighlight %}

{% highlight VB %}

Private Sub DeleteRibbonState_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
Me.MyRibbon.DeleteRibbonState()
End Sub

{% endhighlight %}

{% endtabs %}

Also this method is used to delete any file from specified Isolated Storage location.

{% tabs %}

{% highlight C# %}

private void DeleteRibbonState_Click(object sender, RoutedEventArgs e)
{
    IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User | IsolatedStorageScope.Assembly, null, null);
    this.MyRibbon.DeleteRibbonState(storage,"RibbonState1.dat");
}

{% endhighlight %}

{% highlight VB %}

Private Sub DeleteRibbonState_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
IsolatedStorageFile storage = IsolatedStorageFile.GetStore(IsolatedStorageScope.User Or IsolatedStorageScope.Assembly, null, null)
Me.MyRibbon.DeleteRibbonState(storage,"RibbonState1.dat")
End Sub

{% endhighlight %}

{% endtabs %}

