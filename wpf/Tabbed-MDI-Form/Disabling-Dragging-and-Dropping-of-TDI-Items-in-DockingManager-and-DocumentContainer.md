---
layout: post
title: Disabling Dragging and Dropping of TDI Items in DockingManager and DocumentContainer| DocumentContainer | Wpf | Syncfusion
description: disabling dragging and dropping of tdi items in dockingmanager and documentcontainer
platform: wpf
control: DocumentContainer
documentation: ug
---

# Disabling Dragging and Dropping of TDI Items in DockingManager and DocumentContainer

By default, TDI items in DockingManager and DocumentContainer are can be dragged. The IsTDIDragDropEnabled property is available to disable the dragging and dropping of TDI items, as demonstrated in the following code:



{% tabs %}
{% highlight xaml %}        
<syncfusion:DockingManager Name="dockingmanager1" 
UseDocumentContainer="True" 
IsTDIDragDropEnabled="False">          
  <Grid syncfusion:DockingManager.Header="Tab1" syncfusion:DockingManager.State="Document"/>        
  <Grid syncfusion:DockingManager.Header="Tab2" syncfusion:DockingManager.State="Document"/>    
  </syncfusion:DockingManager>
  {% endhighlight %}

{% highlight C# %}
 dockingmanager1.IsTDIDragDropEnabled=false;
 {% endhighlight %}
 {% endtabs %}



This property is also applicable to DocumentContainer, as shown in the following code.



{% tabs %}
{% highlight xaml %}      
  <syncfusion:DocumentContainer Name="documentcontainer1" Mode="TDI" IsTDIDragDropEnabled="False" >      
  <Grid syncfusion:DockingManager.Header="Tab1" syncfusion:DockingManager.State="Document"/>     
  <Grid syncfusion:DockingManager.Header="Tab2" syncfusion:DockingManager.State="Document"/>   
  </syncfusion:DocumentContainer>
  {% endhighlight %}
 

{% highlight C# %}
documentcontainer1.IsTDIDragDropEnabled=false;
{% endhighlight %}
{% endtabs %}


