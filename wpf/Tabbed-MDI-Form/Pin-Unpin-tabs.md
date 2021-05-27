---
layout: post
title: Pin and Unpin TabItems in WPF Tabbed MDI Form control | Syncfusion
description: Learn here all about Pin and Unpin TabItems support in Syncfusion WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: wpf
control: DocumentContainer
 documentation: ug
---
# Pin and Unpin TabItems in WPF Tabbed MDI Form (DocumentContainer)

This section explains the pin and unpin tab items support in DocumentContainer.

## Enabling/disabling pinning behavior

The [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) attached property of DocumentContainer decides whether the tab item can be pinnable or not. The corresponding tab item will be pinned only if the property [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) is true. When the property is false, pin and unpin behavior of tab item will be disabled. The default value of the [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) property is false.

{% tabs %}

{% highlight XAML %}

<syncfusion:DocumentContainer  
                Name="DocContainer"
	           Mode="TDI">
                <syncfusion:DocumentContainer.Icon>
                    <ImageBrush ImageSource="document.png"/>
                </syncfusion:DocumentContainer.Icon>
                                
                <!--TDI/MDI Children elements of the Document Container-->
                <FlowDocumentScrollViewer                      
                    syncfusion:DocumentContainer.AllowPin="True"
                    syncfusion:DocumentContainer.Header="Document Container">
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left">
                        <Paragraph FontWeight="Bold" FontSize="15" TextAlignment="Center">
                            Syncfusion WPF Document Container</Paragraph>
                        <Paragraph>This  sample exhibits the special features 
                                of the Syncfusion Document Container Control for 
                                Windows Presentation Foundation(WPF).
                        </Paragraph>
                        <Paragraph>View this document to experience the features of the 
                                Document Container.Document Container supports both TDI and MDI.
                        </Paragraph>
                        <Paragraph>On certain occasions, users may need the data to be contained in 
                                the traditional MDI(Multiple Document Interface) and others where constant 
                                comparison needs to be made between the documents requires a 
                                TDI(Tabbed Document Interface).</Paragraph>
                    </FlowDocument>
                </FlowDocumentScrollViewer>
                <FlowDocumentScrollViewer  
                       syncfusion:DocumentContainer.AllowPin="True"
                       syncfusion:DocumentContainer.Header="Features" >
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left" >
                        <Paragraph FontWeight="Bold"  FontSize="15" TextAlignment="Center">Document 
                                Container-Features</Paragraph>
                        <Paragraph>Document container comes with a set of features. They include
                        </Paragraph>
                        <List>
                            <ListItem>
                                <Paragraph>Provides options for both MDI and TDI container Mode
                                </Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Various window switching styles. Ctrl+tab could be used 
                                    to easily navigate through the windows</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Skins Support</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>State Persistence. Document container can be used to 
                                    load, save data in IS, BIN and in XML</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Huge set of properties, methods and events for easy 
                                    customization</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Document container can be resized and moved using the keyboard.
                                </Paragraph>
                            </ListItem>

                        </List>
                    </FlowDocument>
                </FlowDocumentScrollViewer >
                <FlowDocumentScrollViewer  
                        syncfusion:DocumentContainer.AllowPin="True"
                        syncfusion:DocumentContainer.Header="Window 1" >
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left">
                        <Paragraph>For ease of navigation, users can switch between the MDI and TDI modes.
                        </Paragraph>
                        <Paragraph>Most users prefers keyboard to mouse navigation. Thus, to 
                            satisfy all users, syncfusion Document Container is boosted by 
                            Window Switcher(CTRL+TAB keys) for smooth, fine and flexible navigation 
                            between interfaced windows. syncfusion ships five different modes of window 
                            switchers.
                        </Paragraph>
                        <Paragraph>
                            Hold down the CTRL key  and use the TAB keystroke repeatedly to 
                            experience active switchers in effect.
                        </Paragraph>
                    </FlowDocument>
                </FlowDocumentScrollViewer>
            </syncfusion:DocumentContainer>

{% endhighlight %}

{% endtabs %}

## Pin and Unpin tab items using PinButton

The PinButton will be visible in the tab items only when the property [ShowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_ShowPinProperty) is true. The default value of the property is false, so the pin button will be collapsed in the tab item.

{% tabs %}

{% highlight XAML %}

  <syncfusion:DocumentContainer  
                Name="DocContainer"
	           Mode="TDI">
                <syncfusion:DocumentContainer.Icon>
                    <ImageBrush ImageSource="document.png"/>
                </syncfusion:DocumentContainer.Icon>
                                
                <!--TDI/MDI Children elements of the Document Container-->
                <FlowDocumentScrollViewer                      
                    syncfusion:DocumentContainer.AllowPin="True"  syncfusion:DocumentContainer.ShowPin="True"
                    syncfusion:DocumentContainer.Header="Document Container">
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left">
                        <Paragraph FontWeight="Bold" FontSize="15" TextAlignment="Center">
                            Syncfusion WPF Document Container</Paragraph>
                        <Paragraph>This  sample exhibits the special features 
                                of the Syncfusion Document Container Control for 
                                Windows Presentation Foundation(WPF).
                        </Paragraph>
                        <Paragraph>View this document to experience the features of the 
                                Document Container.Document Container supports both TDI and MDI.
                        </Paragraph>
                        <Paragraph>On certain occasions, users may need the data to be contained in 
                                the traditional MDI(Multiple Document Interface) and others where constant 
                                comparison needs to be made between the documents requires a 
                                TDI(Tabbed Document Interface).</Paragraph>
                    </FlowDocument>
                </FlowDocumentScrollViewer>
                <FlowDocumentScrollViewer  
                       syncfusion:DocumentContainer.AllowPin="False"  syncfusion:DocumentContainer.ShowPin="True"
                       syncfusion:DocumentContainer.Header="Features" >
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left" >
                        <Paragraph FontWeight="Bold"  FontSize="15" TextAlignment="Center">Document 
                                Container-Features</Paragraph>
                        <Paragraph>Document container comes with a set of features. They include
                        </Paragraph>
                        <List>
                            <ListItem>
                                <Paragraph>Provides options for both MDI and TDI container Mode
                                </Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Various window switching styles. Ctrl+tab could be used 
                                    to easily navigate through the windows</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Skins Support</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>State Persistence. Document container can be used to 
                                    load, save data in IS, BIN and in XML</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Huge set of properties, methods and events for easy 
                                    customization</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Document container can be resized and moved using the keyboard.
                                </Paragraph>
                            </ListItem>

                        </List>
                    </FlowDocument>
                </FlowDocumentScrollViewer >
                <FlowDocumentScrollViewer  
                        syncfusion:DocumentContainer.AllowPin="True"
                        syncfusion:DocumentContainer.Header="Window 1" >
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left">
                        <Paragraph>For ease of navigation, users can switch between the MDI and TDI modes.
                        </Paragraph>
                        <Paragraph>Most users prefers keyboard to mouse navigation. Thus, to 
                            satisfy all users, syncfusion Document Container is boosted by 
                            Window Switcher(CTRL+TAB keys) for smooth, fine and flexible navigation 
                            between interfaced windows. syncfusion ships five different modes of window 
                            switchers.
                        </Paragraph>
                        <Paragraph>
                            Hold down the CTRL key  and use the TAB keystroke repeatedly to 
                            experience active switchers in effect.
                        </Paragraph>
                    </FlowDocument>
                </FlowDocumentScrollViewer>
            </syncfusion:DocumentContainer>

{% endhighlight %}

{% endtabs %}

![Displaying PinButton to specific items](pin-unpin-tabs-images\displaying-pin-button.png)

If the property [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) is true, the pin button will be enabled and visible. If the property [ShowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_ShowPinProperty) is true and [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) is false, the pin button will be displayed as disabled button. 


### Functionality of PinButton

When the pin button of the tab item is visible, the corresponding tab item can be pinned or unpinned from the Tabcontrol. When the corresponding tab item is pinned, it will be inserted at first position of the tab items collection(if the pinned tab item collection has zero count. Otherwise, the pinned tab item will be added to the existing collection). When the tab item is unpinned, it will be removed from the pinned tab item collection and added to the first position of the unpinned tab item collection.

## Pin and Unpin the tab items programmatically

Tab items can be pinned or unpinned from the DocumentContainer using [IsPinned](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_IsPinnedProperty) attached property of DocumentContainer. If the property [IsPinned](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_IsPinnedProperty) is set to true, the corresponding item will be added to respective index. Also,if the property [IsPinned](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_IsPinnedProperty) is set as false, the tab item will be removed from pinned collection and added to unpinned tab item collection. The default value of the property is False.

## Pin and Unpin tab items through ContextMenu

The pin or unpin operations can be done through tab item's ContextMenu also. If the property [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) is true, and the tab item is not pinned, the "Pin Tab" option will be visible. If the tab item is pinned already, "Unpin Tab" will be visible. 

<syncfusion:DocumentContainer  
                Name="DocContainer"
	           Mode="TDI">
                <syncfusion:DocumentContainer.Icon>
                    <ImageBrush ImageSource="document.png"/>
                </syncfusion:DocumentContainer.Icon>
                                
                <!--TDI/MDI Children elements of the Document Container-->
                <FlowDocumentScrollViewer                      
                    syncfusion:DocumentContainer.AllowPin="True"  
                    syncfusion:DocumentContainer.Header="Document Container">
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left">
                        <Paragraph FontWeight="Bold" FontSize="15" TextAlignment="Center">
                            Syncfusion WPF Document Container</Paragraph>
                        <Paragraph>This  sample exhibits the special features 
                                of the Syncfusion Document Container Control for 
                                Windows Presentation Foundation(WPF).
                        </Paragraph>
                        <Paragraph>View this document to experience the features of the 
                                Document Container.Document Container supports both TDI and MDI.
                        </Paragraph>
                        <Paragraph>On certain occasions, users may need the data to be contained in 
                                the traditional MDI(Multiple Document Interface) and others where constant 
                                comparison needs to be made between the documents requires a 
                                TDI(Tabbed Document Interface).</Paragraph>
                    </FlowDocument>
                </FlowDocumentScrollViewer>
                <FlowDocumentScrollViewer  
                       syncfusion:DocumentContainer.AllowPin="True" 
                       syncfusion:DocumentContainer.Header="Features" >
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left" >
                        <Paragraph FontWeight="Bold"  FontSize="15" TextAlignment="Center">Document 
                                Container-Features</Paragraph>
                        <Paragraph>Document container comes with a set of features. They include
                        </Paragraph>
                        <List>
                            <ListItem>
                                <Paragraph>Provides options for both MDI and TDI container Mode
                                </Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Various window switching styles. Ctrl+tab could be used 
                                    to easily navigate through the windows</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Skins Support</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>State Persistence. Document container can be used to 
                                    load, save data in IS, BIN and in XML</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Huge set of properties, methods and events for easy 
                                    customization</Paragraph>
                            </ListItem>
                            <ListItem>
                                <Paragraph>Document container can be resized and moved using the keyboard.
                                </Paragraph>
                            </ListItem>

                        </List>
                    </FlowDocument>
                </FlowDocumentScrollViewer >
                <FlowDocumentScrollViewer  
                        syncfusion:DocumentContainer.AllowPin="True"
                        syncfusion:DocumentContainer.Header="Window 1" >
                    <FlowDocument FontFamily="Calibri" FontSize="13" TextAlignment="Left">
                        <Paragraph>For ease of navigation, users can switch between the MDI and TDI modes.
                        </Paragraph>
                        <Paragraph>Most users prefers keyboard to mouse navigation. Thus, to 
                            satisfy all users, syncfusion Document Container is boosted by 
                            Window Switcher(CTRL+TAB keys) for smooth, fine and flexible navigation 
                            between interfaced windows. syncfusion ships five different modes of window 
                            switchers.
                        </Paragraph>
                        <Paragraph>
                            Hold down the CTRL key  and use the TAB keystroke repeatedly to 
                            experience active switchers in effect.
                        </Paragraph>
                    </FlowDocument>
                </FlowDocumentScrollViewer>
            </syncfusion:DocumentContainer>

The following images illustrates the same,

![Displaying option to pin the tab itemExt](pin-unpin-tabs-images\pintab-option-contextmenu.png)

![Displaying option to Unpin the tab itemExt](pin-unpin-tabs-images\unpintab-option-contextmenu.png)
