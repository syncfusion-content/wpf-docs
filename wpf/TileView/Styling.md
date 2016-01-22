---
layout: post
title: Styling | TileView | wpf | Syncfusion
description: styling
platform: wpf
control: TileView Control
documentation: ug
---

# Styling

Styling can be applied to both the TileViewControl and its items. The TileViewControl supports nine built-in styles that can be implemented at run time based on specified conditions.

## Visual Styles

The TileViewControl has the following built-in styles:

1. Office2007Blue
1. Office2007Black
2. Office2007Silver
3. Office2010Blue
4. Office2010Black
5. Office2010Silver
6. Blend
7. Metro
8. Transparent



These styles can be applied to the control using XAML and C#. The following code example illustrates how to apply Office2007Blue style to the TileViewControl.


{%tabs %}

{% highlight xaml %}

<syncfusion:TileViewControl         syncfusion:SkinStorage.VisualStyle="Office2010Blue"        />    
{% endhighlight %}





{% highlight c# %}

SkinStorage.SetVisualStyle(tileViewInstance, "Office2010Blue");
{% endhighlight %}

{% endtabs %}


The following illustrations show the TileViewControl that is applied with different built-in styles.



![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2007Blue.png](Styling_images/Styling_img1.png)





![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2007silver.png](Styling_images/Styling_img2.png)





![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2007Black.png](Styling_images/Styling_img3.png)




![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2010Blue.png](Styling_images/Styling_img4.png)




![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2010silver.png](Styling_images/Styling_img5.png)





![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2010Black.png](Styling_images/Styling_img6.png)




![C:/Users/boopeshkumart/Desktop/TileView_Themes/blend.png](Styling_images/Styling_img7.png)





![C:/Users/boopeshkumart/Desktop/TileView_Themes/metro.png](Styling_images/Styling_img8.png)





![C:/Users/boopeshkumart/Desktop/TileView_Themes/transparent.png](Styling_images/Styling_img9.png)





## ItemContainerStyle

The _ItemContainerStyle_ property of _TileViewControl_ sets the style of TileViewItem. This style will be applied to all items available in the TileViewControl. The following example illustrates how to apply styles to the items.

1. Create the style for TileViewControl.


   ~~~ xml
     

     <Style TargetType="{x:Type syncfusion:TileViewItem}" x:Key="itemStyle">

            <Setter Property="Header" Value="{Binding XPath=@Name}"/>

            <Setter Property="ContentTemplate">

                <Setter.Value>



                    <DataTemplate>

                        <Grid Margin="10">

                            <Grid.RowDefinitions>

                                <RowDefinition Height="Auto"/>

                                <RowDefinition Height="Auto"/>

                            </Grid.RowDefinitions>

                            <TextBlock Text="Description: " FontWeight="Bold"/>

                            <TextBlock Text="{Binding XPath=@Description}" FontFamily="Verdana" TextWrapping="Wrap" Margin="5,5,0,0"  Grid.Row="1"/>

                        </Grid>

                    </DataTemplate>

                </Setter.Value>

            </Setter>

        </Style>

   ~~~
   





2. Set the _ItemContainerStyle_ of the _TileViewControl_ as follows.


   ~~~ xml
     

     <syncfusion:TileViewControl  ItemContainerStyle="{StaticResource itemStyle}" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"  >





        </syncfusion:TileViewControl>

   ~~~
   



This will generate the following TileViewControl.



![](Styling_images/Styling_img10.png)





## ItemContainerStyleSelector

The _ItemContainerStyleSelector_ property is used to choose the ItemContainerStyle at run time base on specific conditions. The following examples illustrate this.



1. Create _StyleSelector_ in the code.


   ~~~ cs
   
       

         public class TileViewItemContainerStyleSelector : StyleSelector

            {

      

                 public override Style SelectStyle(object item, DependencyObject container)

                {



                     Window window = Application.Current.MainWindow;



                     string bookname = (item as System.Xml.XmlElement).GetAttribute("Name").ToString().ToLower();

                     if (bookname.Contains("wpf"))

                    {

                     return ((Style)window.Resources["WpfBookStyle"]);

                    }

                     else

                    {

                     return ((Style)window.Resources["CsBookStyle"]);

                    }



                }

            }
   ~~~
  




2. Create the styles in the Window’s resource.


   ~~~ xml
   

        <Style TargetType="{x:Type syncfusion:TileViewItem}" x:Key="CsBookStyle">

            <Setter Property="Header" Value="{Binding XPath=@Name}"/>

            <Setter Property="ContentTemplate">

                <Setter.Value>

                    <DataTemplate>

                        <Grid Margin="10">

                            <Grid.RowDefinitions>

                                <RowDefinition Height="Auto"/>

                                <RowDefinition Height="Auto"/>

                            </Grid.RowDefinitions>

                            <TextBlock Text="Description: " FontWeight="Bold"/>

                            <TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" FontFamily="Courier New" Foreground="Green" Margin="5,5,0,0" Grid.Row="1"/>

                        </Grid>

                    </DataTemplate>

                </Setter.Value>

            </Setter>

        </Style>



        <Style TargetType="{x:Type syncfusion:TileViewItem}" x:Key="WpfBookStyle">

            <Setter Property="Header" Value="{Binding XPath=@Name}"/>

            <Setter Property="ContentTemplate">

                <Setter.Value>



                    <DataTemplate>

                        <Grid Margin="10">

                            <Grid.RowDefinitions>

                                <RowDefinition Height="Auto"/>

                                <RowDefinition Height="Auto"/>

                            </Grid.RowDefinitions>

                            <TextBlock Text="Description: " FontWeight="Bold"/>

                            <TextBlock Text="{Binding XPath=@Description}" FontFamily="Verdana" Foreground="Blue" TextWrapping="Wrap" Margin="5,5,0,0"  Grid.Row="1"/>

                        </Grid>

                    </DataTemplate>

                </Setter.Value>

            </Setter>

        </Style>
   ~~~
   


3. Define the Style selector in the Window’s resource.


   ~~~ xml
    

     <local:TileViewItemContainerStyleSelector x:Key="tileViewStyleSelector"/>

   ~~~
   



4. Set _ItemContainerStyle_ for the TileViewControl.


   ~~~ xml
     

      <syncfusion:TileViewControl  ItemContainerStyleSelector="{StaticResource tileViewStyleSelector}" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"  Margin="20" >



         </syncfusion:TileViewControl>
   ~~~
   




This will generate the following TileViewControl.



![](Styling_images/Styling_img11.png)





