---
layout: post
title: Orientation of ToolBarTrayAdv | ToolBarAdv | wpf | Syncfusion
description: orientation of toolbartrayadv
platform: wpf
control: ToolBarAdv
documentation: ug
---

# Orientation of ToolBarTrayAdv

ToolBarAdv provides horizontal and vertical orientation. You can set the orientation using the _Orientation_ property. 

The following code illustrates how to set orientation:

{%tabs%}

{% highlight xml %}          

            <shared:ToolBarTrayAdv Orientation="Vertical" >

                    <shared:ToolBarAdv ToolBarName="Standard">

                        <Button shared:ToolBarAdv.Icon="Images/NewDocumentHS.png">

                            <Image Source="Images/NewDocumentHS.png" Width="16" Height="16"/>

                        </Button>

                        <Button  >

                            <Image Source="Images/openHS.png"  Width="16" Height="16"/>

                        </Button>

                    </shared:ToolBarAdv>

                    <shared:ToolBarAdv Band="1"   ToolBarName="Extras">

                        <Button >

                            <Image Source="Images/InsertPictureHS.png"  Width="16" Height="16"/>

                        </Button>

                        <Button  >

                            <Image Source="Images/InsertHyperlinkHS.png"  Width="16" Height="16"/>

                        </Button>

                        <Button  >

                            <Image Source="Images/TableHS.png"  Width="16" Height="16"/>

                        </Button>

                    </shared:ToolBarAdv>

                </shared:ToolBarTrayAdv>


{% endhighlight %}


{% highlight C# %}

ToolBarTrayAdv tray = new ToolBarTrayAdv();

            tray.Orientation = Orientation.Vertical;

            ToolBarAdv toolBar = new ToolBarAdv();

            Button button = new Button();

            button.Content = new Image()

            {

                Source = new BitmapImage()

                {

                    UriSource = new Uri("Images/InsertPictureHS.png", UriKind.RelativeOrAbsolute)

                }

            };

            toolBar.Items.Add(button);

            button = new Button();

            button.Content = new Image()

            {

                Source = new BitmapImage()

                {

                    UriSource = new Uri("Images/InsertHyperlinkHS.png", UriKind.RelativeOrAbsolute)

                }

            };

            toolBar.Items.Add(button);

            button = new Button();

            button.Content = new Image()

            {

                Source = new BitmapImage()

                {

                    UriSource = new Uri("Images/TableHS.png", UriKind.RelativeOrAbsolute)

                }

            };

            toolBar.Items.Add(button);

            tray.ToolBars.Add(toolBar);


{% endhighlight %}

{%endtabs%}


![](Orientation-of-ToolBarTrayAdv_images/Orientation-of-ToolBarTrayAdv_img1.png)

