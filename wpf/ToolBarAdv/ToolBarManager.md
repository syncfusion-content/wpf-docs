---
layout: post
title: ToolBarManager
description: toolbarmanager
platform: wpf
control: ToolBarAdv
documentation: ug
---

# ToolBarManager

ToolBarManager is a container in which you can place ToolBarTrayAdv in top, bottom, left or right.

Content of the ToolBarManager will be displayed in the remaining space. 

The following code illustrates how to place the ToolBarAdv at the top:



[XAML]



&lt;shared:ToolBarManager x:Name="toolBarManager" &gt; 

            &lt;shared:ToolBarManager.Resources&gt;

                &lt;Style TargetType="Button"&gt;

                    &lt;Setter Property="Height" Value="20" /&gt;

                    &lt;Setter Property="Width" Value="20"/&gt;

                &lt;/Style&gt;

                &lt;Style TargetType="ToggleButton"&gt;

                    &lt;Setter Property="Height" Value="20"/&gt;

                    &lt;Setter Property="Width" Value="20"/&gt;

                &lt;/Style&gt;



            &lt;/shared:ToolBarManager.Resources&gt;

            &lt;shared:ToolBarManager.TopToolBarTray&gt;

                &lt;shared:ToolBarTrayAdv &gt;

                    &lt;shared:ToolBarAdv ToolBarName="Standard"&gt;

                        &lt;Button&gt;

                            &lt;Image Source="Images/NewDocumentHS.png" Width="16" Height="16"/&gt;

                        &lt;/Button&gt;

                        &lt;Button &gt;

                            &lt;Image Source="Images/openHS.png"  Width="16" Height="16"/&gt;

                        &lt;/Button&gt;

                    &lt;/shared:ToolBarAdv&gt;

                &lt;/shared:ToolBarTrayAdv&gt;



            &lt;/shared:ToolBarManager.TopToolBarTray&gt;

        &lt;/shared:ToolBarManager&gt;





[C#]



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





