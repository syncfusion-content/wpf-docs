---
layout: post
title: SplitMenuButton-Popup-KeyTip
description: splitmenubutton popup keytip
platform: wpf
control: Ribbon
documentation: ug
---

# SplitMenuButton Popup KeyTip

SplitMenuButton has now comes with separate key tip for pop-up menu. Separate keytips can be assigned for SplitMenuButton to:

* Invoke the SplitMenuButton
* Open the popup



The following code snippet illustrates how to set keytip for SplitMenuButton Popup.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:SplitMenuButton Label="Print" Name="printBtn" syncfusion:Ribbon.SplitMenuKeyTip="U" syncfusion:Ribbon.KeyTip="PR"&gt;</td></tr>
<tr>
<td>
[C#]Ribbon.SetKeyTip(printBtn, "PR");Ribbon.SetSplitMenuKeyTip(printBtn, "U");</td></tr>
</table>


{ ![](SplitMenuButton-Popup-KeyTip_images/SplitMenuButton-Popup-KeyTip_img1.jpeg) | markdownify }
{:.image }




