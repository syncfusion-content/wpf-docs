---
layout: post
title: Silverlight application in WPF OLAPCommon Control | Syncfusion
description: Connect wcf service in silverlight application in Syncfusion WPF OLAPCommon Control, its elements, and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Connect WCF Service in Silverlight application

The user can connect the above WCF service using Channel Factory by CustomBinding (Or BasicHttpBinding) and End Point Address values.

The below code snippet demonstrates how to connect the WCF service:

{% tabs %}
{% highlight c# %}

Binding customBinding = new CustomBinding(new BinaryMessageEncodingBindingElement(), new HttpTransportBindingElement { MaxReceivedMessageSize = 2147483647 });

EndpointAddress address = new EndpointAddress(new Uri(App.Current.Host.Source.ToString() + "../../../../Services/OlapManager.svc/binary"));

ChannelFactory<IOlapDataProvider> clientChannel = new ChannelFactory<IOlapDataProvider>(customBinding, address);

IOlapDataProvider _dataProvider = clientChannel.CreateChannel();



////Sets the data provider (WCF Service connection) in OlapDataManager

_olapDataManager.DataProvider = _dataProvider;

{% endhighlight  %}

{% highlight vbnet %}

Dim customBinding As Binding = New CustomBinding(New BinaryMessageEncodingBindingElement(),New HttpTransportBindingElement() With { _

Key .MaxReceivedMessageSize = 2147483647 _

})

Dim address As New EndpointAddress(New Uri(App.Current.Host.Source.ToString() & "../../../../Services/OlapManager.svc/binary"))

Dim clientChannel As New ChannelFactory(Of IOlapDataProvider)(customBinding, address)

Dim _dataProvider As IOlapDataProvider = clientChannel.CreateChannel()



'''Sets the data provider (WCF Service connection) in OlapDataManager

_olapDataManager.DataProvider = _dataProvider

{% endhighlight  %}
{% endtabs %}
