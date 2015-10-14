---
layout: post
title: Ribbon State Persistence | Ribbon | WPF | Syncfusion
description: ribbon state persistence
platform: wpf
control: Ribbon
documentation: ug
---

# Ribbon State Persistence

State Persistence is the combined process of Serialization and Deserialization. Serialization is the process of converting the state of an object to a format in which it can be persisted as a file in the memory. The serialized format contains the object's state information. Deserialization is the complement process of Serialization, which converts into the object from the stored state information. 

WPF Ribbon control has a fully built-in Serialization support to serialize the entire Ribbon control states. You can save and load the Ribbon States at any time while running the application and also at the time of application exit and start.

You can persist Ribbon Control states separately as follows:

1. Quick Access Tool Bar
1. Quick Access Tool Bar Items
2. Quick Access Tool Bar State ( Above Ribbon, Below Ribbon)
3. Ribbon
4. Ribbon State (Normal, Hide)
5. Ribbon Window
6. Window Width
7. Window Height
8. Window Left
9. Window Top



## Use Case Scenarios

The Ribbon State Persistence feature helps users to load the state of the Ribbon control that existed when the application was closed. State Persistence feature gives a more consistent workflow for an application that is executed for a long time.

## Tables for Properties and Methods

### Properties



<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th><th>
{{ '**Default Value**' | markdownify }}</th></tr>
<tr>
<td>
AutoPersist</td><td>
This property will enable/disable the state persistence in Ribbon control. This property is available individually for Quick Access Tool Bar, Ribbon and Ribbon Window.</td><td>
DependencyProperty</td><td>
bool</td><td>
False</td></tr>
</table>




PersistElements Table

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th><th>
{{ '**Default Value**' | markdownify }}</th></tr>
<tr>
<td>
PersistElements</td><td>
This property has a collection of Ribbon elements, which are used to persist states at runtime.</td><td>
CLR</td><td>
ObservableCollection<RibbonElements></td><td>
Null </td></tr>
</table>


You can enable State Persistence in Ribbon control by setting the AutoPersist property to “True”. You can customize the State Persistence in Ribbon, Quick Access Tool Bar and Ribbon Window elements by using the AutoPersist property.



### Methods



SaveRibbonState Table

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<td>
SaveRibbonState()</td><td>
This method will save the current State of the Ribbon control.</td><td>
(+2 Overloads)No Params(IsolatedStorageFile arg1, string arg2)arg1 – This parameter is used to mention the custom Isolated Storage file.arg2 – This is the file name in the Isolated Storage file, which is used to save the Ribbon state.</td><td>
void</td></tr>
</table>


LoadRibbonState Table

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<td>
LoadRibbonState()</td><td>
This method will load the saved state of the Ribbon.</td><td>
(+2 Overloads)No Params(IsolatedStorageFile arg1, string arg2)arg1– This parameter is used to mention the custom Isolated Storage file.arg2 – This is the file name in the Isolated Storage file, which has the stored Ribbon State.</td><td>
void</td></tr>
</table>


ResetRibbonState Table

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<td>
ResetRibbonState()</td><td>
ResetRibbonState method will load the initial state of the Ribbon elements.</td><td>
No Params</td><td>
 void</td></tr>
</table>


DeleteRibbonState Table

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<td>
DeleteRibbonState()</td><td>
It will be delete the saved state of the file from memory.</td><td>
(+2 Overloads)    1. No params    2.(IsolatedStorageFile arg1,                     string arg2)arg1– This parameter is used to mention the custom Isolated Storage file.arg2 – This is the file name in the Isolated Storage file, which has to be deleted.</td><td>
 void</td></tr>
</table>


## Sample Link

To access a sample:

Click Start -> All Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.

Click the WPF drop-down list, and then select Run Locally Installed Samples.



In the sample browser, expand Ribbon, and then select Ribbon State Persistence.

# Using State Persistence in Application

You can persist Ribbon states in the following ways namely: 

Persisting Ribbon States at Application Exit and Load

Persisting Ribbon States Any Time while Running the Application

Persisting Ribbon States by XML Writer 



# Persisting Ribbon States at Application Exit and Load

The user can persist the Ribbon States at application exit and load by handling the AutoPersist property. You can customize the persisting states in Ribbon control by handling the AutoPersist property individually in Ribbon, QAT and Ribbon window. The following code snippet shows how to handle the property in Ribbon elements. 

{% highlight c# %}
 
   
<syncfusion:RibbonWindow x:Class="RibbonSample.Window1" x:Name="ribbonwindow"

    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"   

xmlns:sample="clr-namespace:RibbonSample"   AutoPersist="True"

WindowState="Normal" WindowStyle="SingleBorderWindow"

    Title="Ribbon Sample Demo"  WindowStartupLocation="CenterScreen">

    <Grid>

        <syncfusion:Ribbon Name="MyRibbon" AutoPersist="True">

            <syncfusion:Ribbon.QuickAccessToolBar>

                <syncfusion:QuickAccessToolBar AutoPersist="True">

                </syncfusion:QuickAccessToolBar>

            </syncfusion:Ribbon.QuickAccessToolBar>

        </syncfusion:Ribbon>

    </Grid>

</syncfusion:RibbonWindow>

 {% endhighlight %}







# Persisting Ribbon States Any Time while Running the Application

WPF Ribbon control now supports the persistence of its states any time while running the application. You can save and load the Ribbon states any time by using Ribbon methods. There are two methods to save and load the current Ribbon states. They are:

SaveRibbonState

LoadRibbonState



Before you call the methods, you have to specify the persisting Ribbon elements in PersistElements collection. You can change the collection any time. Save and Load states at runtime are fully based on this collection details. The following code snippet shows how to add Ribbon elements that are required to retain its state.

{% highlight c# %}
 
   

private void ribbonwindow_Loaded(object sender, RoutedEventArgs e)

  {

       this.MyRibbon.PersistElements.Add(RibbonElements.Ribbon);

       this.MyRibbon.PersistElements.Add(RibbonElements.RibbonWindow);                           

       this.MyRibbon.PersistElements.Add(RibbonElements.QuickAccessToolbar);

  }

{% endhighlight %}







## Saving Ribbon States

You can dynamically save and load the current Ribbon state at run time. You can save the current Ribbon State by using the SaveRibbonState method in Ribbon. This method has two overloaded methods for customizing the Save state process as follows:

1. void SaveRibbonState()

void SaveRibbonState(IsolatedStorageFile isoStorage, string storeFileName)

In the first method, there are no parameters. It will save the current state of the Ribbon Control to the default Isolated Storage file, which is built in the source.

{% highlight c# %}
 
    

  private void SaveRibbonState_Click(object sender, RoutedEventArgs e)

     {

       this.MyRibbon.SaveRibbonState();       

     } 

 {% endhighlight %}





You can also store the current Ribbon State in the custom Isolated Storage file by using the second overloaded method.  This method has two arguments namely IsolatedStorageFile and storeFileName. By using these two arguments you can define your own Isolated Storage file for saving the state.

{% highlight c# %}
 
   

  private void SaveRibbonState_Click(object sender, RoutedEventArgs e)

     {

       IsolatedStorageFile storage = 

                      IsolatedStorageFile.GetStore(IsolatedStorageScope.User  

                              |IsolatedStorageScope.Assembly, null, null);

       this.MyRibbon.SaveRibbonState(storage,"Customfilename.dat");       

     }

 {% endhighlight %}







## Loading Ribbon States

Load state process is also having the similar procedures of save states. We can load the Ribbon State at any time from the last saved Isolated Storage file. LoadRibbonState method is used to load the Ribbon state from the last saved state. This method has two overloaded methods as follows:

1. void LoadRibbonState()

void LoadRibbonState(IsolatedStorageFile isoStorage, string storeFileName)

The first method with no arguments will load the Ribbon State from the last saved state in the default Isolated Storage file, which is stored by the SaveRibbonState method.

{% highlight c# %}
 
    

private void LoadRibbonState_Click(object sender, RoutedEventArgs e)

        {

            this.MyRibbon.LoadRibbonState();

        }

 {% endhighlight %}







The second overloaded method will load the Ribbon State from the given file name in the mentioned Isolated Storage file.

{% highlight c# %}
 
   

private void LoadRibbonState_Click(object sender, RoutedEventArgs e)

        {

            IsolatedStorageFile storage = 

                       IsolatedStorageFile.GetStore(IsolatedStorageScope.User 

                                 |IsolatedStorageScope.Assembly, null, null);

            this.MyRibbon.LoadRibbonState(storage, "Customfilename.dat");

        }

 {% endhighlight %}







## Saving and Loading Many Ribbon States

You can easily maintain many Ribbon control states in the Isolated Storage files. You can save the consecutive or different states of the Ribbon control in different Isolated Storage filesand also  load any saved state from the Isolated Storage files which is in the old state. You can save the different states of the Ribbon control at various times as follows:

{% highlight c# %}
 
   

private void SaveLevel1State_Click(object sender, RoutedEventArgs e)

    {

        IsolatedStorageFile storage = 

             IsolatedStorageFile.GetStore(IsolatedStorageScope.User | 

                                 IsolatedStorageScope.Assembly, null, null);

        this.MyRibbon.SaveRibbonState(storage,"RibbonState1.dat");       

    }



private void SaveLevel2State_Click(object sender, RoutedEventArgs e)

    {

        IsolatedStorageFile storage = 

              IsolatedStorageFile.GetStore(IsolatedStorageScope.User | 

                                IsolatedStorageScope.Assembly, null, null);

        this.MyRibbon.SaveRibbonState(storage, "RibbonState2.dat");

    }



private void SaveLevel3State_Click(object sender, RoutedEventArgs e)

    {

       IsolatedStorageFile storage = 

           IsolatedStorageFile.GetStore(IsolatedStorageScope.User | 

                                IsolatedStorageScope.Assembly, null, null);

       this.MyRibbon.SaveRibbonState(storage, "RibbonState3.dat");

    }

 {% endhighlight %}







After saving the different states of the Ribbon Control, you can load the Ribbon state to any of the old states. The following code snippet explains the implementation.

{% highlight c# %}
 
    

private void LoadLevel1State_Click(object sender, RoutedEventArgs e)

        {

            IsolatedStorageFile storage = 

                  IsolatedStorageFile.GetStore(IsolatedStorageScope.User | 

                                IsolatedStorageScope.Assembly, null, null);

            this.MyRibbon.LoadRibbonState(storage, "RibbonState1.dat");

        }



private void LoadLevel2State_Click(object sender, RoutedEventArgs e)

        {

            IsolatedStorageFile storage = 

                   IsolatedStorageFile.GetStore(IsolatedStorageScope.User | 

                                IsolatedStorageScope.Assembly, null, null);

            this.MyRibbon.LoadRibbonState(storage, "RibbonState2.dat");

        }



private void LoadLevel3State_Click(object sender, RoutedEventArgs e)

        {

            IsolatedStorageFile storage = 

                  IsolatedStorageFile.GetStore(IsolatedStorageScope.User | 

                                 IsolatedStorageScope.Assembly, null, null);

            this.MyRibbon.LoadRibbonState(storage, "RibbonState3.dat");

        }

 {% endhighlight %}







# Persisting Ribbon States by XML Writer 



The WPF Ribbon control supports state persistence in the xml file created by the user. The ribbon states can be saved and loaded in the xml file by overloading the following methods:

SaveRibbonState(XmlWriter xmlWriter)

LoadRibbonState(XmlReader xmlReader)



## Methods



Methods Table

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<td>
SaveRibbonState</td><td>
It saves the ribbon state to the xml file given in the parameter. </td><td>
XmlWriter</td><td>
N/A</td><td>
N/A </td></tr>
<tr>
<td>
LoadRibbonState</td><td>
It loads the ribbon state from the xml file given in the parameter.</td><td>
XmlReader</td><td>
N/A</td><td>
N/A</td></tr>
</table>


# Utility Methods

## Resetting Ribbon States

You can load the Normal (Initial) Ribbon state at runtime by calling the ResetRibbonState method. This is a parameter less method. This will load the Normal state of the Ribbon control. Resetting the Ribbon state is applicable while AutoPersist is enabled in Ribbon elements. You can customize the resetting state of Ribbon elements by enabling the AutoPersist property.

{% highlight c# %}
 
   

private void ResetState_Click(object sender, RoutedEventArgs e)

        {

            this.MyRibbon.ResetRibbonState();

        }

 {% endhighlight %}







## Deleting Ribbon States

You can delete the unused saved Isolated Storage files by using the DeleteRibbonState method. This method has two overloads. They are:

DeleteRibbonState()

DeleteRibbonState(IsolatedStorageFile isoStorage, string deletefileName)



The first overloaded method will delete the default saved file from the default Isolated Storage file location. The following code snippet shows how to delete the default saved file.

{% highlight c# %}
 
   

  private void DeleteRibbonState_Click(object sender, RoutedEventArgs e)

     {

       this.MyRibbon.DeleteRibbonState(); 

     } 

 {% endhighlight %}





The second overloaded method is used to delete any file from specified Isolated Storage location. The following code snippet shows how to delete any file from the Isolated Storage location.

{% highlight c# %}
 
  

  private void DeleteRibbonState_Click(object sender, RoutedEventArgs e)

     {

       IsolatedStorageFile storage = 

                      IsolatedStorageFile.GetStore(IsolatedStorageScope.User  

                              |IsolatedStorageScope.Assembly, null, null);

       this.MyRibbon.DeleteRibbonState(storage,"RibbonState1.dat");       

     }

 {% endhighlight %}







