# Page Settings

Page settings enable to customize the appearance, width, and height of the Diagram pa page.

![](PageSettings_images/PageSettings_img1.jpeg)


Page size and appearance

The size and appearance of the Diagram pages can be customized with the PageSettings property.

The PageWidth and PageHeight properties of page settings define the size of the page. In addition to that, you can customize the appearance of the page with a set of appearance specific properties. 

You can also customize the appearance of off-page regions with the property BackgroundColor.

The following code illustrates how to customize the page size and the appearance of page and off-page.

[XAML]

<table>
<tr>
<td>
<diagram:SfDiagram x:Name="diagram" Background="WhiteSmoke"><br/><br/><diagram:SfDiagram.PageSettings><br/><br/><diagram:PageSettings PageWidth="500" PageHeight="500" <br/><br/>PageBorderThickness="4" PageBackground="White"<br/><br/>PageBorderBrush="LightGray" ShowPageBreaks="True"     <br/><br/>MultiplePage="True" PageOrientation="Portrait"/><br/><br/></diagram:SfDiagram.PageSettings> <br/><br/><diagram:SfDiagram.SnapSettings><br/><br/><diagram:SnapSettings SnapConstraints="ShowLines"/><br/><br/></diagram:SfDiagram.SnapSettings><br/><br/></diagram:SfDiagram><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
diagram.Background = new SolidColorBrush(Colors.WhiteSmoke);<br/><br/>diagram.PageSettings.PageWidth = 500;<br/><br/>diagram.PageSettings.PageHeight = 500;<br/><br/>diagram.PageSettings.PageBorderThickness = new Thickness(4);<br/><br/>diagram.PageSettings.PageBackground = new SolidColorBrush(Colors.White);<br/><br/>diagram.PageSettings.PageBorderBrush = new SolidColorBrush(Colors.LightGray);<br/><br/>diagram.PageSettings.ShowPageBreaks = true;<br/><br/>diagram.PageSettings.MultiplePage = true;<br/><br/>diagram.PageSettings.PageOrientation = PageOrientation.Portrait;<br/><br/>diagram.SnapSettings.SnapConstraints = SnapConstraints.ShowLines;<br/><br/><br/><br/></td></tr>
</table>
![](PageSettings_images/PageSettings_img2.jpeg)


![](PageSettings_images/PageSettings_img3.jpeg)


MultiplePage and PageBreaks

When MutiplePage is enabled, size of the page dynamically increases or decreases in multiple of page width and height and completely fits diagram within the page boundaries. Page Breaks is used as a visual guide to see how pages are split into multiple pages.

![](PageSettings_images/PageSettings_img4.jpeg)


MultiplePage and ShowPageBreak properties of page settings allow you to enable/disable multiple pages and page breaks respectively. The following code illustrates how to enable multiple page and page break lines.

<table>
<tr>
<td>
diagram.PageSettings.ShowPageBreaks = true;<br/><br/>diagram.PageSettings.MultiplePage = true;<br/><br/><br/><br/></td></tr>
</table>
