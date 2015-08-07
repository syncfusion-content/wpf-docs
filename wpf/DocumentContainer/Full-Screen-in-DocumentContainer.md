---
layout: post
title: Full-Screen-in-DocumentContainer
description: full screen in documentcontainer
platform: wpf
control: DocumentContainer
documentation: ug
---

# Full Screen in DocumentContainer

TDIFullScreenMode is the property used to define the full-screen mode for TDI items. When a value is set for this property, the parent window will be displayed as a full screen and the tab item header will be visible only when the cursor passes over the top of the window. This property is an enum type with the following values:

* ControlMode—Makes the tab header visible on mouseover.
* WindowMode—Performs the full-screen operation and makes the tab header visible on mouseover.
* None—Does not do anything; it is the default value.



<table>
<tr>
<td>
{% highlight xml %}<syncfusion:DocumentContainer Name="documentcontainer1" Mode="TDI" TDIFullScreenMode="WindowMode" />{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %}documentcontainer1. TDIFullScreenMode=FullScreenMode.WindowMode;{% endhighlight %}</td></tr>
</table>


Note: This feature also applicable for the TabControlExt.


<table>
<tr>
<td>
{% highlight xml %}<syncfusion:TabControlExt Name="tabcontrol1" FullScreenMode="WindowMode"/>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} tabcontrol1. FullScreenMode= FullScreenMode.WindowMode; {% endhighlight %}</td></tr>
</table>


###Toolbar in DocumentContainer

A toolbar can be placed with headers in the header panel of TDI items in DocumentContainer; for this, the TDIToolBarTray property is used. 



![](Full-Screen-in-DocumentContainer_images/Full-Screen-in-DocumentContainer_img1.jpeg)





<table>
<tr>
<td>
{% highlight xml %}        <syncfusion:DocumentContainer Name="documentcontainer1" Mode="TDI" >            <syncfusion:DocumentContainer.TDIToolBarTray>                <ToolBarTray>                    <ToolBar>                        <Button Content="Tool" />                    </ToolBar>                </ToolBarTray>            </syncfusion:DocumentContainer.TDIToolBarTray>            <Grid syncfusion:DocumentContainer.Header="tab1" />            <Grid syncfusion:DocumentContainer.Header="tab2"/>        </syncfusion:DocumentContainer>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} ToolBarTray tooltray = new ToolBarTray();ToolBar toolbar = new ToolBar(); toolbar.Items.Add(new Button{Content="Tool"}); tooltray.ToolBars.Add(toolbar);documentcontainer1.TDIToolBarTray = tooltray;{% endhighlight %}</td></tr>
</table>


This feature is also applicable to TabControlExt, as demonstrated in the following code.



<table>
<tr>
<td>
{% highlight xml %}        <syncfusion:TabControlExt Name="tabcontrol">            <syncfusion:TabControlExt.ToolBarTray>                <ToolBarTray>                    <ToolBar>                        <Button Content="Tool" />                    </ToolBar>                </ToolBarTray>            </syncfusion:TabControlExt.ToolBarTray>        </syncfusion:TabControlExt>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} ToolBarTray tooltray = new ToolBarTray();ToolBar toolbar = new ToolBar(); toolbar.Items.Add(new Button{Content="Tool"}); tooltray.ToolBars.Add(toolbar);tabcontrol.ToolBarTray = tooltray;{% endhighlight %}</td></tr>
</table>
## SizeToContent for MDI Window in DocumentContainer

SizetoContentInMDI is used to resize an MDI window to its child size. This is an attached property and can be applied to individual children inside DocumentContainer.



<table>
<tr>
<td>
{% highlight xml %}        <syncfusion:DocumentContainer Mode="MDI">            <Grid Name="grid1" syncfusion:DocumentContainer.SizetoContentInMDI="True" Width="200"  Height="200" />        </syncfusion:DocumentContainer>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} DocumentContainer.SetSizetoContentInMDI(grid1,true);{% endhighlight %}</td></tr>
</table>


