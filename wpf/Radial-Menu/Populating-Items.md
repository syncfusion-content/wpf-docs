---
layout: post
title: Populate Items in WPF Radial Menu | Syncfusion®
description: Populate WPF Radial Menu items from business objects using data binding, display member paths, commands, and item templates.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# Populate Items in WPF Radial Menu (SfRadialMenu)

## Items Source  

Radial menu items can be populated with the business object collection. Let us create a WPF Radial Menu which will show the list of Application commands.   

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

Bind the Application command collection to the ItemsSource property of the WPF Radial Menu control. 

{%highlight xaml%}



<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}"/>

{%endhighlight%}

This will populate the WPF Radial Menu as shown in the image below. 





![Concepts_img1](Concepts_images/Concepts_img1.png)





## Display Member Path 

The DisplayMemberPath property of the WPF Radial Menu is used to specify the business model property displayed in item headers.

{%highlight xaml%}





<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}"

DisplayMemberPath="Name"

                         />


{%endhighlight%}

![Concepts_img2](Concepts_images/Concepts_img2.png)



Displaying member path

## Command Path

The CommandPath property of the WPF Radial Menu specifies the command in the business object that is bound to a menu item when items are populated through data binding.

{%highlight xaml%}





<navigation:SfRadialMenu IsOpen="True" DisplayMemberPath="Name" CommandPath="Command"

                                 ItemsSource="{Binding Options}" />


{%endhighlight%}

## Item Template 

The ItemTemplate property of the WPF Radial Menu is used to customize the appearance and content of item headers.

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



