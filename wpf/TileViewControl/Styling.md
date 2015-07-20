---
layout: post
title: Styling
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



These styles can be applied to the control using XAML. The following code example illustrates how to apply Office2007Blue style to the TileViewControl.



 [XAML]

&lt;syncfusion:TileViewControl         syncfusion:SkinStorage.VisualStyle="Office2010Blue"        /&gt;    





These styles can also be applied to the control using C# as follows.



[C#]

SkinStorage.SetVisualStyle(tileViewInstance, "Office2010Blue");





The following illustrations show the TileViewControl that is applied with different built-in styles.



{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2007Blue.png](Styling_images/Styling_img1.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2007silver.png](Styling_images/Styling_img2.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2007Black.png](Styling_images/Styling_img3.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2010Blue.png](Styling_images/Styling_img4.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2010silver.png](Styling_images/Styling_img5.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/office2010Black.png](Styling_images/Styling_img6.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/blend.png](Styling_images/Styling_img7.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/metro.png](Styling_images/Styling_img8.png) | markdownify }
{:.image }




{ ![C:/Users/boopeshkumart/Desktop/TileView_Themes/transparent.png](Styling_images/Styling_img9.png) | markdownify }
{:.image }




## ItemContainerStyle

The _ItemContainerStyle_ property of _TileViewControl_ sets the style of TileViewItem. This style will be applied to all items available in the TileViewControl. The following example illustrates how to apply styles to the items.

1. Create the style for TileViewControl.



[XAML]

    &lt;Style TargetType="{x:Type syncfusion:TileViewItem}" x:Key="itemStyle"&gt;

            &lt;Setter Property="Header" Value="{Binding XPath=@Name}"/&gt;

            &lt;Setter Property="ContentTemplate"&gt;

                &lt;Setter.Value&gt;



                    &lt;DataTemplate&gt;

                        &lt;Grid Margin="10"&gt;

                            &lt;Grid.RowDefinitions&gt;

                                &lt;RowDefinition Height="Auto"/&gt;

                                &lt;RowDefinition Height="Auto"/&gt;

                            &lt;/Grid.RowDefinitions&gt;

                            &lt;TextBlock Text="Description: " FontWeight="Bold"/&gt;

                            &lt;TextBlock Text="{Binding XPath=@Description}" FontFamily="Verdana" TextWrapping="Wrap" Margin="5,5,0,0"  Grid.Row="1"/&gt;

                        &lt;/Grid&gt;

                    &lt;/DataTemplate&gt;

                &lt;/Setter.Value&gt;

            &lt;/Setter&gt;

        &lt;/Style&gt;







2. Set the _ItemContainerStyle_ of the _TileViewControl_ as follows.



[XAML]

&lt;syncfusion:TileViewControl  ItemContainerStyle="{StaticResource itemStyle}" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"  &gt;





        &lt;/syncfusion:TileViewControl&gt;





This will generate the following TileViewControl.



{ ![](Styling_images/Styling_img10.png) | markdownify }
{:.image }




## ItemContainerStyleSelector

The _ItemContainerStyleSelector_ property is used to choose the ItemContainerStyle at run time base on specific conditions. The following examples illustrate this.



1. Create _StyleSelector_ in the code.



[C#]

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





2. Create the styles in the Window’s resource.



[XAML]

&lt;Style TargetType="{x:Type syncfusion:TileViewItem}" x:Key="CsBookStyle"&gt;

            &lt;Setter Property="Header" Value="{Binding XPath=@Name}"/&gt;

            &lt;Setter Property="ContentTemplate"&gt;

                &lt;Setter.Value&gt;

                    &lt;DataTemplate&gt;

                        &lt;Grid Margin="10"&gt;

                            &lt;Grid.RowDefinitions&gt;

                                &lt;RowDefinition Height="Auto"/&gt;

                                &lt;RowDefinition Height="Auto"/&gt;

                            &lt;/Grid.RowDefinitions&gt;

                            &lt;TextBlock Text="Description: " FontWeight="Bold"/&gt;

                            &lt;TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" FontFamily="Courier New" Foreground="Green" Margin="5,5,0,0" Grid.Row="1"/&gt;

                        &lt;/Grid&gt;

                    &lt;/DataTemplate&gt;

                &lt;/Setter.Value&gt;

            &lt;/Setter&gt;

        &lt;/Style&gt;



        &lt;Style TargetType="{x:Type syncfusion:TileViewItem}" x:Key="WpfBookStyle"&gt;

            &lt;Setter Property="Header" Value="{Binding XPath=@Name}"/&gt;

            &lt;Setter Property="ContentTemplate"&gt;

                &lt;Setter.Value&gt;



                    &lt;DataTemplate&gt;

                        &lt;Grid Margin="10"&gt;

                            &lt;Grid.RowDefinitions&gt;

                                &lt;RowDefinition Height="Auto"/&gt;

                                &lt;RowDefinition Height="Auto"/&gt;

                            &lt;/Grid.RowDefinitions&gt;

                            &lt;TextBlock Text="Description: " FontWeight="Bold"/&gt;

                            &lt;TextBlock Text="{Binding XPath=@Description}" FontFamily="Verdana" Foreground="Blue" TextWrapping="Wrap" Margin="5,5,0,0"  Grid.Row="1"/&gt;

                        &lt;/Grid&gt;

                    &lt;/DataTemplate&gt;

                &lt;/Setter.Value&gt;

            &lt;/Setter&gt;

        &lt;/Style&gt;



3. Define the Style selector in the Window’s resource.



[XAML]

&lt;local:TileViewItemContainerStyleSelector x:Key="tileViewStyleSelector"/&gt;





4. Set _ItemContainerStyle_ for the TileViewControl.



[XAML]

&lt;syncfusion:TileViewControl  ItemContainerStyleSelector="{StaticResource tileViewStyleSelector}" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"  Margin="20" &gt;



         &lt;/syncfusion:TileViewControl&gt;





This will generate the following TileViewControl.



{ ![](Styling_images/Styling_img11.png) | markdownify }
{:.image }




