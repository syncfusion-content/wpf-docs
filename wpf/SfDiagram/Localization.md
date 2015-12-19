# Localization

Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.

Customizing Context Menu

![](Localization_images/Localization_img1.jpeg)


The following code illustrates how to provide localization support for Context Menu items.

<table>
<tr>
<td>
System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr");//French<br/><br/>System.Resources.ResourceManager manager;<br/><br/>Assembly assembly = Application.Current.GetType().Assembly;<br/><br/>manager = new System.Resources.ResourceManager("Localization.Resources.Syncfusion.SfDiagram.WPF", <br/><br/>assembly);<br/><br/><br/><br/></td></tr>
</table>
![](Localization_images/Localization_img2.jpeg)


