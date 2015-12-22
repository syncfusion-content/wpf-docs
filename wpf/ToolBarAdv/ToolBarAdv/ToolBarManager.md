---
layout: post
title: ToolBarManager | ToolBarAdv | wpf | Syncfusion
description: toolbarmanager
platform: wpf
control: ToolBarAdv
documentation: ug
---

# ToolBarManager

ToolBarManager is a container in which you can place ToolBarTrayAdv in top, bottom, left or right.

Content of the ToolBarManager will be displayed in the remaining space. 

The following code illustrates how to place the ToolBarAdv at the top:


{%tabs%}
{% highlight xaml %}



<shared:ToolBarManager x:Name="toolBarManager" > 

            <shared:ToolBarManager.Resources>

                <Style TargetType="Button">

                    <Setter Property="Height" Value="20" />

                    <Setter Property="Width" Value="20"/>

                </Style>

                <Style TargetType="ToggleButton">

                    <Setter Property="Height" Value="20"/>

                    <Setter Property="Width" Value="20"/>

                </Style>



            </shared:ToolBarManager.Resources>

            <shared:ToolBarManager.TopToolBarTray>

                <shared:ToolBarTrayAdv >

                    <shared:ToolBarAdv ToolBarName="Standard">

                        <Button>

                            <Image Source="Images/NewDocumentHS.png" Width="16" Height="16"/>

                        </Button>

                        <Button >

                            <Image Source="Images/openHS.png"  Width="16" Height="16"/>

                        </Button>

                    </shared:ToolBarAdv>

                </shared:ToolBarTrayAdv>



            </shared:ToolBarManager.TopToolBarTray>

        </shared:ToolBarManager>


{% endhighlight %}


{% highlight C# %}



ToolBarAdv toolBar = new ToolBarAdv();

            Button button = new Button();

            button.Content = new Image()

            {

                Source = new BitmapImage()

                {

                    UriSource = new Uri("Images/NewDocumentHS.png", UriKind.RelativeOrAbsolute)

                }

            };

            toolBar.Items.Add(button);

            button = new Button();

            button.Content = new Image()

            {

                Source = new BitmapImage()

                {

                    UriSource = new Uri("Images/openHS.png", UriKind.RelativeOrAbsolute)

                }

            };

            toolBar.Items.Add(button);

            ToolBarTrayAdv tray = new ToolBarTrayAdv();

            tray.ToolBars.Add(toolBar);

            ToolBarManager manager = new ToolBarManager();

            manager.TopToolBarTray = tray;


{% endhighlight %}
{%endtabs%}


