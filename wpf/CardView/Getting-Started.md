---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: CardView
documentation: ug
---

# Getting Started

## Control Structure

{{ '![](Getting-Started_images/Getting-Started_img1.png)' | markdownify }}
{:.image }


## Create the CardView Control

The CardView control can be created through Visual Studio, Expression Blend, XAML, and C#.

### Through Visual Studio 

To create the CardView control through Visual Studio, drag the CardView from the Toolbox and drop it in the Designer area. It generates the CardView control.

{{ '![](Getting-Started_images/Getting-Started_img2.png)' | markdownify }}
{:.image }


### Through Expression Blend

The CardView control can also be created and configured using Expression Blend. The following are the steps to do so.

1. Create a WPF project in Expression Blend and reference the following assemblies.
1. Syncfusion.Shared.Wpf
2. Syncfusion.Tools.Wpf
3. Syncfusion.Core
2. Search for CardView in the Toolbox.



{{ '![](Getting-Started_images/Getting-Started_img3.png)' | markdownify }}
{:.image }


3. Drag the CardView to the designer. This generates the following CardView control.

{{ '![](Getting-Started_images/Getting-Started_img4.png)' | markdownify }}
{:.image }


4. To add the items to the CardView by using the CollectionEditor, select the CardView and go to Properties area, and then click Items (Collection) under Common Properties.

{{ '![C:/Users/ApoorvahR/Desktop/1.png](Getting-Started_images/Getting-Started_img5.png)' | markdownify }}
{:.image }



5. Once the Collection Editor opens, click Add Another Item.  The Select Object window opens.
6. Select the CardViewItem by typing CardViewItem in the search box, and then click OK.



{{ '![](Getting-Started_images/Getting-Started_img6.png)' | markdownify }}
{:.image }




7. Configure the CardViewItem using the properties in the Collection Editor.



> _Note: You can also customize the appearance of CardView control and its items using the template editing feature available in the Expression Blend._

### Through XAML

To create the CardView control through XAML, add the following namespace to the directives list.

[XAML]

xmlns:syncfusion=http://schemas.syncfusion.com/wpf



After adding the above namespace the CardViewControl can be added to the application as follows:

[XAML]

         <syncfusion:CardView >

            <syncfusion:CardViewItem Header="Item1" >

                <ListBox>

                    <ListBoxItem HorizontalContentAlignment="Stretch" Padding="1">

                        <Grid >

                            <Grid.ColumnDefinitions>

                                <ColumnDefinition Width="75"/>

                                <ColumnDefinition Width="*"/>

                            </Grid.ColumnDefinitions>

                            <TextBlock Text="Name:"/>

                            <TextBox  Grid.Column="1" Text="David" />

                        </Grid>

                    </ListBoxItem>

                    <ListBoxItem HorizontalContentAlignment="Stretch" Padding="1">

                        <Grid >

                            <Grid.ColumnDefinitions>

                                <ColumnDefinition Width="75"/>

                                <ColumnDefinition Width="*"/>

                            </Grid.ColumnDefinitions>

                            <TextBlock Text="DOB:"/>

                            <TextBox  Grid.Column="1" Text="2/25/1986" />

                        </Grid>

                    </ListBoxItem>

                </ListBox>

            </syncfusion:CardViewItem>

        </syncfusion:CardView>





### Through C#

To create the CardView control through C#, include the following namespace to the directives list.

[C#]

using Syncfusion.Windows.Tools.Controls;





Next, create the CardView control as illustrated in the following code example.

[C#]



CardView cardView = new CardView();

            CardViewItem cardViewItem1 = new CardViewItem();

            TextBlock tBlock = new TextBlock() { Text = "John" };

            cardViewItem1.Content = tBlock;

            cardView.Items.Add(cardViewItem1);





