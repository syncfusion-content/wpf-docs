---
layout: post
title: Precision
description: precision
platform: wpf
control: Rating
documentation: ug
---

# Precision

Precision defines the accuracy level of the rating control. It provides the following three types of precision:

1. Standard
2. Half
3. Exact



Standard

The rating item will be filled completely based on the value of the Rating control when the mouse enters the rating item.

In the following example, 1.3 has been set for the value. The rating item has been filled completely for standard precision.

[XAML]



<editors:SfRating ItemsCount="5" Value="1.3" 

Precision="Standard/>



{ ![C:/Users/ApoorvahR/Desktop/3.png](Precision_images/Precision_img1.png) | markdownify }
{:.image }


Half

The rating item will be filled partially based on the value of the Rating control when the mouse enters the rating item.

In this case, 0.3 has been set for the value. The rating item was filled partially.

[XAML]



&lt;editors:SfRating ItemsCount="5" Value="1.3" Precision="Half"/&gt;



{ ![C:/Users/ApoorvahR/Desktop/4.png](Precision_images/Precision_img2.png) | markdownify }
{:.image }


Exact

The rating item will be filled exactly based on the value of the Rating control and when mouse enters the rating item.

In this case, 1.3 has been set for the Value. Rating item was filled to reflect the exact value.

[XAML]



<editors:SfRating ItemsCount="5" Value="1.3" 

Precision="Exact"/>



{ ![C:/Users/ApoorvahR/Desktop/5.png](Precision_images/Precision_img3.png) | markdownify }
{:.image }


