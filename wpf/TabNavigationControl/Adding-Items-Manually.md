---
layout: post
title: Adding-Items-Manually
description: adding items manually
platform: wpf
control: TabNavigationControl
documentation: ug
---

# Adding Items Manually

Tab Navigation control is based on Items control. Therefore, items can be added through the property Items in Tab Navigation control. Any kind of items can be added into Tab Navigation control, which will be wrapped by the container Tab Navigation Item.


{% highlight xml %}
XAML

  <syncfusion:TabNavigationControl TransitionEffect="Slide" >

            <syncfusion:TabNavigationItem Header="1">

                <syncfusion:TabNavigationItem.Content>

                    <Grid>

                        <TextBlock Text="Item 1"/>

                    </Grid>

                </syncfusion:TabNavigationItem.Content>

            </syncfusion:TabNavigationItem>

            <syncfusion:TabNavigationItem Header="2">

                <syncfusion:TabNavigationItem.Content>

                    <Grid>

                        <TextBlock Text="Item 2"/>

                    </Grid>

                </syncfusion:TabNavigationItem.Content>

            </syncfusion:TabNavigationItem>

            <syncfusion:TabNavigationItem Header="3">

                <syncfusion:TabNavigationItem.Content>

                    <Grid>

                        <TextBlock Text="Item 3"/>

                    </Grid>

                </syncfusion:TabNavigationItem.Content>

            </syncfusion:TabNavigationItem>

            <syncfusion:TabNavigationItem Header="4">

                <syncfusion:TabNavigationItem.Content>

                    <Grid>

                        <TextBlock Text="Item 4"/>

                    </Grid>

                </syncfusion:TabNavigationItem.Content>

            </syncfusion:TabNavigationItem>



        </syncfusion:TabNavigationControl>
{% endhighlight %}



{% highlight  %}
C#

TabNavigationControl tabNavControl = new TabNavigationControl();



            TabNavigationItem item1 = new TabNavigationItem();

            item1.Header = "1";

            item1.Content = "Item 1";



            TabNavigationItem item2 = new TabNavigationItem();

            item2.Header = "2";

            item2.Content = "Item 2";



            TabNavigationItem item3 = new TabNavigationItem();

            item3.Header = "3";

            item3.Content = "Item 3";



            TabNavigationItem item4 = new TabNavigationItem();

            item4.Header = "4";

            item4.Content = "Item 4";



            tabNavControl.Items.Add(item1);

            tabNavControl.Items.Add(item2);

            tabNavControl.Items.Add(item3);

            tabNavControl.Items.Add(item4);

{% endhighlight  %}


{% highlight vbnet %}
[VB.NET]



    Dim tabNavControl As New TabNavigationControl()



    Dim item1 As New TabNavigationItem()

item1.Header = "1"

item1.Content = "Item 1"



    Dim item2 As New TabNavigationItem()

item2.Header = "2"

item2.Content = "Item 2"



    Dim item3 As New TabNavigationItem()

item3.Header = "3"

item3.Content = "Item 3"



    Dim item4 As New TabNavigationItem()

item4.Header = "4"

item4.Content = "Item 4"



tabNavControl.Items.Add(item1)

tabNavControl.Items.Add(item2)

tabNavControl.Items.Add(item3)

tabNavControl.Items.Add(item4)
{% endhighlight %}




![](Adding-Items-Manually_images/Adding-Items-Manually_img1.png)





