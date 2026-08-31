---
layout: post
title: Pin and Unpin TabItems in WPF DocumentContainer | Syncfusion®
description: Pin or unpin tab items in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control so important documents stay readily available.
platform: wpf
control: DocumentContainer
documentation: ug
---
# Pin and Unpin TabItems in WPF DocumentContainer

This section explains how to pin and unpin tab items in a DocumentContainer.

## Enabling or Disabling Pinning Behavior

The [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) attached property of DocumentContainer determines whether a tab item can be pinned. The corresponding tab item is pinnable only when the [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) property is `true`. When the property is `false`, the pin and unpin behavior of the tab item is disabled. The default value of the [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) property is `false`. This property is set on each child element (it is an attached property), not on the DocumentContainer itself.

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

## Pin and Unpin Tab Items Using the PinButton

The PinButton is visible in the tab items only when the [ShowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_ShowPinProperty) property is `true`. The default value of the property is `false`, so the pin button is collapsed in the tab item.

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

![Displaying PinButton to specific items](Pin-Unpin-tabs-images/displaying-pin-button.png)

If the property [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) is `true`, the pin button is enabled and visible. If the property [ShowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_ShowPinProperty) is `true` and [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) is `false`, the pin button is displayed as a disabled button. 

### Functionality of the PinButton

When the pin button of the tab item is visible, the corresponding tab item can be pinned or unpinned from the TabControl. When the corresponding tab item is pinned, it is inserted at the first position of the pinned tab items collection (or, if the pinned tab items collection is non-empty, the pinned tab item is added to the existing collection). When the tab item is unpinned, it is removed from the pinned tab items collection and added to the first position of the unpinned tab items collection.

## Pin and Unpin Tab Items Programmatically

Tab items can be pinned or unpinned from the DocumentContainer using the [IsPinned](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_IsPinnedProperty) attached property of DocumentContainer. When [IsPinned](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_IsPinnedProperty) is set to `true`, the corresponding item is added to the pinned tab items collection. When [IsPinned](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_IsPinnedProperty) is set to `false`, the tab item is removed from the pinned collection and added to the unpinned tab items collection. The default value of the property is `false`.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer x:Name="DocContainer" Mode="TDI">
    <FlowDocumentScrollViewer x:Name="viewer1"
                              syncfusion:DocumentContainer.Header="Document 1"
                              syncfusion:DocumentContainer.AllowPin="True"
                              syncfusion:DocumentContainer.IsPinned="True" />
    <FlowDocumentScrollViewer x:Name="viewer2"
                              syncfusion:DocumentContainer.Header="Document 2"
                              syncfusion:DocumentContainer.AllowPin="True" />
</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
// Pin a tab item programmatically
DocumentContainer.SetIsPinned(viewer1, true);

// Unpin a tab item programmatically
DocumentContainer.SetIsPinned(viewer1, false);
{% endhighlight %}
{% endtabs %}

## Pin and Unpin Tab Items Through the Context Menu

The pin and unpin operations can also be performed through the tab item's context menu. If the [AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_AllowPinProperty) property is `true` and the tab item is not pinned, the "Pin Tab" option is visible. If the tab item is already pinned, the "Unpin Tab" option is visible.

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

The following images illustrate the same.

![Displaying the Pin Tab option in the context menu](Pin-Unpin-tabs-images/pintab-option-contextmenu.png)

![Displaying the Unpin Tab option in the context menu](Pin-Unpin-tabs-images/unpintab-option-contextmenu.png)
