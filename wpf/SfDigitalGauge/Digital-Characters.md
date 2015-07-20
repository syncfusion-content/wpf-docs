---
layout: post
title: Digital-Characters
description: digital characters
platform: wpf
control: Digital Gauge 
documentation: ug
---

## Digital Characters

The Digital Characters in the Digital Gauge can be viewed in different types of segments. The digital characters are set to the Digital Gauge by using the Value property of type string.



[XAML]

   <syncfusion:SfDigitalGauge Value="GAUGE" />    



[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "GAUGE";

            this.Grid.Children.Add(digitalgauge);





Screenshot:

{{ '![](Digital-Characters_images/Digital-Characters_img1.png)' | markdownify }}
{:.image }


7-Segments

The digital characters set with the value property of the Digital Gauge are displayed by default 7-segments. Rather than using the alphabets, these are mainly used to display numbers. The type of segments can be set by using the CharacterType property.



[XAML]

<syncfusion:SfDigitalGauge Value="12345"  CharacterType="SegmentSeven" />



[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "12345";

            digitalgauge.CharacterType = CharacterType.SegmentSeven;

            this.Grid.Children.Add(digitalgauge);



Screenshot:



{{ '![](Digital-Characters_images/Digital-Characters_img2.png)' | markdownify }}
{:.image }




14-Segments

The digital characters set with the value property of the Digital Gauge are displayed by 14 segments. It is used to display both alphabets and numbers. 



[XAML]  

<syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="SegmentFourteen" />



[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "SYNCFUSION";

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);





Screenshot:



{{ '![](Digital-Characters_images/Digital-Characters_img3.png)' | markdownify }}
{:.image }


16-Segments

The digital characters set with the value property of the digital gauge are displayed by 16 segments. It is used to display both alphabets and numbers. 



[XAML]

  <syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="SegmentSixteen" /> 



[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "SYNCFUSION";

            digitalgauge.CharacterType = CharacterType.SegmentSixteen;

            this.Grid.Children.Add(digitalgauge);





Screenshot:



{{ '![](Digital-Characters_images/Digital-Characters_img4.png)' | markdownify }}
{:.image }


8*8 Dot Matrix Segments

The digital characters set with the value property of the Digital Gauge are displayed by eight cross eight dot matrix segments. It is used to display special characters along with the alphabets and numbers. 



[XAML]

<syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="EightCrossEightDotMatrix" />



[XAML]  

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "SYNCFUSION";

            digitalgauge.CharacterType = CharacterType.EightCrossEightDotMatrix;

            this.Grid.Children.Add(digitalgauge);





Screenshot:



{{ '![](Digital-Characters_images/Digital-Characters_img5.png)' | markdownify }}
{:.image }


