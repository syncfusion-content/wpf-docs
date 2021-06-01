---
layout: post
title: Connect WCF Service by an additional Binding Type | OLAPCommon | Wpf | Syncfusion
description: connect wcf service by an additional binding type in silverlight application
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Connect WCF Service by an additional Binding Type in Silverlight application

OLAP Silverlight controls can be bound to _BasicHttpBinding_ support.

N>  Incorrect specification of endpoint address will lead to Initialize Component Error. The endpoint address should be set with respect to the type of bindings.



### Use case Scenario 

User can create Web service using the _BasicHttpBinding_ feature and bind the service to OLAP Silverlight controls. 

## BasicHttpBinding 

The following are steps to create a BasicHttpBinding: 

Include the Basic HTTP Binding and Service endpoint address in the Web.Config file as given in the   following code:

{% highlight xaml %}

<!--<Bindings>-->

<bindings>			

<basicHttpBinding>

<binding name="binaryHttpBinding" maxBufferSize="2147483647" 

maxReceivedMessageSize="2147483647">

<readerQuotas maxDepth="2147483647"/>

<security mode="None" />

</binding>

</basicHttpBinding>

</bindings>



<!--<Endpoint Address>-->

<services>

<service behaviorConfiguration="Services.OlapManagerBehavior" name="Services.OlapManager">

<endpoint address="basic" binding="basicHttpBinding"      

bindingConfiguration="binaryHttpBinding"    

contract="Syncfusion.OlapSilverlight.Manager.IOlapDataProvider" />

</service>

</services>



{% endhighlight  %}

## Instantiate the WCF service using Basic HTTP Binding and End Point Address values:

* Declare the _IOlapDataProvider_ for Service instantiation as given in the following code:



{% highlight c# %}

  // Declaring the IOlapDataProvider for service instantiation
IOlapDataProvider DataProvider = null;

{% endhighlight  %}

{% highlight vbnet %}

' Declaring the IOlapDataProvider for service instantiation

Dim DataProvider As IOlapDataProvider = Nothing

{% endhighlight  %}

* Specify the _basicHttpBinding_ and Instantiate the _DataProvider_ from the _ChannelFactory_ as given in the following code: 

{% tabs %}
{% highlight c# %}

private void InitializeConnection()

{

Binding basicHttpBinding = new BasicHttpBinding(BasicHttpSecurityMode.None)             

{ MaxBufferSize = 2147483647, MaxReceivedMessageSize = 2147483647 };

var Uri = App.Current.Host.Source.ToString();

////Address for Basic HTTP binding in corresponding Web configuration file

EndpointAddress address = new EndpointAddress (new Uri (Uri +  

"../../../../Services/OlapManager.svc/basic"));

ChannelFactory<IOlapDataProvider> clientChannel = new 

ChannelFactory<IOlapDataProvider>(basicHttpBinding, address);

DataProvider = clientChannel.CreateChannel();

}


{% endhighlight  %}


{% highlight vbnet %}

Private Sub InitializeConnection()

Dim basicHttpBinding As System.ServiceModel.Channels.Binding = New BasicHttpBinding (BasicHttpSecurityMode.None With {.MaxReceivedMessageSize = 2147483647})

  'Address for Basic HTTP binding in corresponding Web configuration file

Dim address As EndpointAddress = New EndpointAddress (New 

Uri(App.Current.Host.Source & "../../../../OlapManager.svc/basic"))

Dim clientChannel As ChannelFactory(Of IOlapDataProvider) = New ChannelFactory(Of IOlapDataProvider)(basicHttpBinding, address)

DataProvider = clientChannel.CreateChannel()

End Sub

{% endhighlight  %}
{% endtabs %}
