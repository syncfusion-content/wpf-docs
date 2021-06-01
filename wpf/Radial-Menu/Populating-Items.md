---
layout: post
title: Populating Items in WPF Radial Menu control | Syncfusion
description: Learn here all about Populating Items support in Syncfusion WPF Radial Menu (SfRadialMenu) control and more.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# Populating Items in WPF Radial Menu (SfRadialMenu)

## Items Source  

Radial menu items can be populated with the business object collection. Let us create a RadialMenu which will show the list of Application commands.   

The Application command model look likes below.  



{%highlight c#%}





  public class ApplicationCommand

    {

        public string Name { get; set; }



        public string ImagePath { get; set; }



        public ICommand Command { get; set; }

    }

{%endhighlight%}

Create the Application command collection as follows. 


{%highlight c#%}




private List<ApplicationCommand> options;



public List<ApplicationCommand> Options

   {

            get { return options; }

            set { options = value; }

   }



{%endhighlight%}

Populate the Application command collection as follows. 


{%highlight c#%}





 Options = new List<ApplicationCommand>(); 

 Options.Add(new ApplicationCommand() { Name="Bold" , ImagePath="bold.png" });    			  Options.Add(new ApplicationCommand() { Name = "Cut" , ImagePath="cut.png"}); 

 Options.Add(new ApplicationCommand() { Name = "Copy" ,ImagePath="copy.png"}); 

 Options.Add(new ApplicationCommand() { Name = "Paste" ,ImagePath="paste.png"});

{%endhighlight%}

Bind the Application command collection to the ItemsSource property of the RadialMenu control. 

{%highlight xaml%}



<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}"/>

{%endhighlight%}

This will populate the RadialMenu as shown in the image below. 





![Concepts_img1](Concepts_images/Concepts_img1.png)





## Display Member Path 

DisplayMemberPath property of the Radial Menu used to define which business model property needs to be displayed inside the header of the Radial Menu items.

{%highlight xaml%}





<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}"

DisplayMemberPath="Name"

                         />


{%endhighlight%}

![Concepts_img2](Concepts_images/Concepts_img2.png)



Displaying member path

## Command Path

CommandPath property of the Radial Menu can be used to bind the command in the business object to the radial menu item when items are populated using data binding. 

{%highlight xaml%}





<navigation:SfRadialMenu IsOpen="True" DisplayMemberPath="Name" CommandPath="Command"

                                 ItemsSource="{Binding Options}" />


{%endhighlight%}

## Item Template 

ItemTemplate property of the RadialMenu can be used to customize the header part of the radial menu items.  

{%highlight xaml%}

 



<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}">

            <navigation:SfRadialMenu.ItemTemplate>

                <DataTemplate>

                    <StackPanel >

                        <Image Height="15" Width="15" Source="{Binding ImagePath}"/>

                        <TextBlock Margin="0,5,0,0" Text="{Binding Name}"/>

                    </StackPanel>

                </DataTemplate>

            </navigation:SfRadialMenu.ItemTemplate>

   </navigation:SfRadialMenu>

{%endhighlight%}

![Concepts_img3](Concepts_images/Concepts_img3.png)



