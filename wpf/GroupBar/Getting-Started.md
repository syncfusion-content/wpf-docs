---
layout: post
title: Getting Started| GroupBar | Wpf | Syncfusion
description: getting started
platform: wpf
control: GroupBar
documentation: ug
---

# Getting Started

This section describes how to add `GroupBar` control in a WPF and overview of its basic functionalities.

### Control Structure

![](Getting-Started_images/Getting-Started_img1.png)

# Creating simple application with GroupBar

You can create the WPF application with GroupBar control as follows:

1. [Creating project](#creating-the-project)
2. [Adding control via designer](#adding-control-via-designer)
3. [Adding control manually using code](#adding-control-manually-using-code)

### Creating the project

Create a new WPF project in the Visual Studio to display the GroupBar with  functionalities.

## Adding control via designer

The GroupBar control can be added to the application by dragging it from the toolbox and dropping it in a designer view. The following required assembly references will be added automatically:

* Syncfusion.Shared.wpf.dll
* Syncfusion.Tools.wpf.dll

   ![](Getting-Started_images/Getting-Started_img2.png)

2. To add items to GroupBarItems with the Collection Editor, select GroupBar and look at its properties. Click the button in the Items property. This will open the Collection Editor.

   ![](Getting-Started_images/Getting-Started_img3.png)

Using the Collection Editor, add the GroupBarItems and configure their properties.The GroupBar control can also be created and configured using Microsoft Expression Blend. Follow these steps to do so. 

1. Create a WPF project in Expression Blend and reference the following assemblies.

2. Search for _GroupBar_ in the toolbox.

   ![](Getting-Started_images/Getting-Started_img4.png)


3. Drag GroupBar to the designer and drop it there. This will generate the control. 

   ![](Getting-Started_images/Getting-Started_img5.png)


4. To add items to the GroupBar control with the Collection Editor, select GroupBar and go to Properties. Next, click Items (Collection) under Common Properties.

   ![](Getting-Started_images/Getting-Started_img6.png)

5. Once the Collection Editor opens, click Add Another Item to open the Select Object window. Select the GroupBarItem by typing _GroupBarItem_ in the search box and clicking OK.


   ![](Getting-Started_images/Getting-Started_img7.png)


6. Figure 8: Collection Editor for GroupBar in Expression BlendGroupBarItem using the properties in the Collection Editor.



You can also customize the appearance of the GroupBar control and its items by using the template-editing feature available in Expression Blend.

## Adding control manually using code

To create the GroupBar control through code, use the following XAML or C# code.

{% tabs %}

{% highlight XAML %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="300" Width="230" Name="groupBar"/> 
{% endhighlight %} 

{% highlight C# %}

//Creating an instance of GroupBar
GroupBar groupBar = new GroupBar();
//Setting height for GroupBargroupBar.Height = 300;
//Setting width for GroupBar
groupBar.Width = 200;
//Adding GroupBar to window
this.Content = groupBar;

{% endhighlight %} 

{% highlight VB %}

 Dim groupBar As GroupBar = New GroupBar
'Setting height for GroupBargroupBar.Height = 300;
'Setting width for GroupBar
groupBar.Width = 200
'Adding GroupBar to window
Me.Content = groupBar

{% endhighlight %}

{% endtabs %}

### ItemsSource Support/GroupBar Control

Items in a GroupBar can also be added by binding a collection of business object through ItemsSource property. The following is an example of the business object, which is used for ItemsSource binding. 

{% tabs %}

{% highlight C# %}

public class RegionStatistics

{

public string Population{get; set;}

public string Name{get; set;}

public string Location{get; set;}

}


// Adding Items to the ObservableCollection

// Add items to the ObservableCollection, by using the following code.


private void Window1_Loaded(object sender, RoutedEventArgs e)

{

SampleList = new ObservableCollection<RegionStatistics>();

SampleList.Add(new RegionStatistics() { Name = "Mexico", Population = "107,449,525", Location="North America" });

SampleList.Add(new RegionStatistics() { Name = "Canada", Population = "33,098,932", Location = "North America" });

SampleList.Add(new RegionStatistics() { Name = "United States", Population = "304,228,357", Location = "North America" });

SampleList.Add(new RegionStatistics() { Name = "Costa Rica", Population = "04,075,261", Location = "Central America" });

SampleList.Add(new RegionStatistics() { Name = "Brazil", Population = "188,078,287", Location = "South America" });

gri.DataContext = this;

}

{% endhighlight %}

{% highlight VB %}

Public Class RegionStatistics
    
    Public Property Population As String
        Get
        End Get
        Set
        End Set
    End Property
    
    Public Property Name As String
        Get
        End Get
        Set
        End Set
    End Property
    
    Public Property Location As String
        Get
        End Get
        Set
        End Set
    End Property
End Class

' Adding Items to the ObservableCollection
' Add items to the ObservableCollection, by using the following code.
    
    Private Sub Window1_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
        SampleList = New ObservableCollection(Of RegionStatistics)
        SampleList.Add(New RegionStatistics)
        SampleList.Add(New RegionStatistics)
        SampleList.Add(New RegionStatistics)
        SampleList.Add(New RegionStatistics)
        SampleList.Add(New RegionStatistics)
        gri.DataContext = Me
    End Sub

{% endhighlight %}

{% endtabs %}

### Binding ItemsSource Property

 Set the ItemsSource property, by using the following code.

{% tabs %}

{% highlight XAML %}

<sync:GroupBar Name="gBar" ItemsSource="{Binding SampleList}"/> 

{% endhighlight %} 

{% highlight C# %}

Binding bind = new Binding();  
bind.Source = this; 
bind.Path = new PropertyPath("SampleList");  
gBar.SetBinding(GroupBar.ItemssourceProperty, bind);

{% endhighlight %} 

{% highlight VB %}

Dim bind As Binding = New Binding
bind.Source = Me
bind.Path = New PropertyPath("SampleList")
gBar.SetBinding(GroupBar.ItemssourceProperty, bind)

{% endhighlight %} 

{% endtabs %}


![](Getting-Started_images/Getting-Started_img8.jpeg)


### Using ItemTemplate

Apply the ItemTemplate to GroupBar, by using the following code. 

{% tabs %}

{% highlight XAML %}       

<sync:GroupBar.ItemTemplate>

<DataTemplate>

<TextBlock Text="{Binding Name}" FontWeight="Bold"/>

</DataTemplate>

</sync:GroupBar.ItemTemplate>

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img9.jpeg)

### Using ItemContainer Style 

The above image shows that the GroupBar is bounded with the ObservableCollection SampleList. Write the HeaderTemplate and ContentTemplate for the ItemContainer, by using the following code. 

The Item Container Style should be declared as follows.

{% tabs %}

{% highlight XAML %}

<sync:GroupBar.ItemContainerStyle>

<Style TargetType="{x:Type sync:GroupBarItem}">

</Style>

</sync:GroupBar.ItemContainerStyle>


{% endhighlight %}

{% endtabs %}

Apply Header Template to the Header Template property of the Item, by using the following code.

{% tabs %}

{% highlight XAML %}

<Setter Property="Header" Value="{Binding}"/>

            <Setter Property="HeaderTemplate">
                    <Setter.Value>
                           <DataTemplate>
                                <TextBlock Text="{Binding Name}" FontWeight="Bold"/>
                           </DataTemplate>
                    </Setter.Value>
            </Setter>

{% endhighlight %}

{% endtabs %}

Apply Content Template to Content Template property of the item, by using the following code.

{% tabs %}

{% highlight XAML %}
 
 <Setter Property="Content" Value="{Binding}"/>
                        <Setter Property="ContentTemplate">
                            <Setter.Value>
                                <DataTemplate>
                                    <StackPanel Height="50">
                     <TextBlock Text="{Binding Name}" FontWeight="Bold" Margin="1" HorizontalAlignment="Center" FontSize="14"/>
                                        <TextBlock Text="{Binding Location}" HorizontalAlignment="Center"/>
                                        <TextBlock Text="{Binding Population}" HorizontalAlignment="Center"/>
                                    </StackPanel>
                                </DataTemplate>
                            </Setter.Value>
                        </Setter>

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img10.jpeg)


### Using Template Selector

Template can be applied according to the logic set by the user using Template Selector.

The following code illustrates this.

N> Data Template has been written for North America Statistics data

{% tabs %}

{% highlight XAML %}

<DataTemplate x:Key="North">

<StackPanel Height="50">

<TextBlock Text="{Binding Name}" FontWeight="Bold" Margin="1" HorizontalAlignment="Center" FontSize="14" Foreground="Blue"/>

<TextBlock Text="{Binding Location}" HorizontalAlignment="Center" Foreground="Blue"/>

<TextBlock Text="{Binding Population}" HorizontalAlignment="Center" Foreground="Blue"/>

</StackPanel>

</DataTemplate>

{% endhighlight %}

{% endtabs %}

N> Data Template has been written for South America Statistics data.

{% tabs %}

{% highlight XAML %}

<DataTemplate x:Key="South">

<StackPanel Height="50">

<TextBlock Text="{Binding Name}" FontWeight="Bold" Margin="1" HorizontalAlignment="Center" FontSize="14" Foreground="Red"/>

<TextBlock Text="{Binding Location}" HorizontalAlignment="Center" Foreground="Red"/>

<TextBlock Text="{Binding Population}" HorizontalAlignment="Center" Foreground="Red"/>

</StackPanel>

</DataTemplate>

{% endhighlight %}

{% endtabs %}

N> Data Template has been written for Other Statistics data.

{% tabs %}

{% highlight XAML %}

<DataTemplate x:Key="Other">

<StackPanel Height="50">

<TextBlock Text="{Binding Name}" FontWeight="Bold" Margin="1" HorizontalAlignment="Center" FontSize="14" Foreground="Brown"/>

<TextBlock Text="{Binding Location}" HorizontalAlignment="Center" Foreground="Brown"/>

<TextBlock Text="{Binding Population}" HorizontalAlignment="Center" Foreground="Brown"/>

</StackPanel>

</DataTemplate>

{% endhighlight %}

{% endtabs %}

N> Following is the data template selector logic set by the user.

{% tabs %}

{% highlight C# %}

/// <summary>

/// Logic for Template Selector

/// </summary>

public class SampleTemplateSelector : DataTemplateSelector

{

public override DataTemplate SelectTemplate(object item, DependencyObject container)
{

Window win = Application.Current.MainWindow;

if (((RegionStatistics)item).Location == "North America")
{
return win.Resources["North"] as DataTemplate;
}

else if (((RegionStatistics)item).Location == "South America")
{
return win.Resources["South"] as DataTemplate;
}

else
{
return win.Resources["Other"] as DataTemplate;
}

}
}

{% endhighlight %}

{% highlight VB %}

''' <summary>
''' Logic for Template Selector
''' </summary>
Public Class SampleTemplateSelector
    Inherits DataTemplateSelector
    
    Public Overrides Function SelectTemplate(ByVal item As Object, ByVal container As DependencyObject) As DataTemplate
        Dim win As Window = Application.Current.MainWindow
        If (CType(item,RegionStatistics).Location = "North America") Then
            Return CType(win.Resources("North"),DataTemplate)
        ElseIf (CType(item,RegionStatistics).Location = "South America") Then
            Return CType(win.Resources("South"),DataTemplate)
        Else
            Return CType(win.Resources("Other"),DataTemplate)
        End If
        
    End Function
End Class

{% endhighlight %}

{% endtabs %}

N> The ContentTemplate Selector can be applied as follows.

{% tabs %}

{% highlight XAML %}

<sync:GroupBar.ItemContainerStyle>

<Style TargetType="{x:Type sync:GroupBarItem}">

<Setter Property="Header" Value="{Binding}"/>
<Setter Property="HeaderTemplate">

<Setter.Value>

<DataTemplate>

<TextBlock Text="{Binding Name}" FontWeight="Bold"/>

</DataTemplate>

</Setter.Value>

</Setter>

<Setter Property="Content" Value="{Binding}"/>

<Setter Property="ContentTemplateSelector" Value="{StaticResource Selector}"/>

</Style>

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img11.jpeg)


### Events associated with GroupBar ContextMenu

When ItemsSource is in use, Add Tab, Delete Tab, Rename Tab, etc Commands in Context menu cannot be used. To enable this user can use the following event associated with the context menu.

ContextMenuItemClick - The Event is called when any of the ContextMenu items clicked. It contains the following property.

MenuItem –Gets the MenuItem. Users can perform the require command in this menu.

Add a new tab when ItemsSource in use, by using the following code.

{% tabs %}

{% highlight C# %}

gBar.ContextMenuItemClick += new GroupBarContextMenuItemEventHandler(gBar_ContextMenuItemClick);

private void gBar_ContextMenuItemClick(object sender, GroupBarContextMenuItemEventArgs e)

{

if (e.MenuItem.ToString() == "Add Tab")
{
    SampleList.Add(new RegionStatistics() { Name = "New Item", Population ="00,000,000", Location = "**** ****" });
    e.Handled = true;
}

}
{% endhighlight %}

{% highlight VB %}

AddHandler gBar.ContextMenuItemClick, AddressOf Me.gBar_ContextMenuItemClick

    Private Sub gBar_ContextMenuItemClick(ByVal sender As Object, ByVal e As GroupBarContextMenuItemEventArgs)
        If (e.MenuItem.ToString = "Add Tab") Then
            SampleList.Add(New RegionStatistics)
            e.Handled = true
        End If        
    End Sub

{% endhighlight %}

{% endtabs %}

N> Set the Handled property of GroupBarContextMenuItemEventArgs to true to avoid the in-built logic to execute.

![](Getting-Started_images/Getting-Started_img12.jpeg)

![](Getting-Started_images/Getting-Started_img13.jpeg)