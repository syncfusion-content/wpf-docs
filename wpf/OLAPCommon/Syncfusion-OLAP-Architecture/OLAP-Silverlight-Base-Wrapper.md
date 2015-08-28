---
layout: post
title: OLAP-Silverlight-Base-Wrapper
description: olap silverlight base wrapper
platform: wpf
control: OLAP Common 
documentation: ug
---

# OLAP Silverlight Base Wrapper

The OLAP Silverlight Base Wrapper is a class library, which contains several namespaces and classes. This library helps to perform data conversion between OLAP Silverlight Base and OLAP Base. Data Conversion process is used to achieve the following features: 

1. Establishing the connection, retrieving data by converting the OLAP Silverlight Base information to OLAP Base information.
2. Send retrieved data to OLAP Silverlight Base by converting the OLAP Base data to OLAP Silverlight Base data.





![C:/Users/dwarageshmb/Desktop/Doc Images/OlapSilverlight Base/SIlverlight.png](OLAP-Silverlight-Base-Wrapper_images/OLAP-Silverlight-Base-Wrapper_img1.png)





_Figure3: Dataflow in Silverlight_



> Note: This class library was organized under Syncfusion.OlapSilverlight.BaseWrapper assembly.

## WCF Service

In order to query the database, OLAP Silverlight controls use WCF Service. The DataProvider property of OlapDataManager performs the service call operations. 

## Creating and connecting a WCF Service.

