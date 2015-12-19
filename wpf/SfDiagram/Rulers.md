# Rulers

The Ruler provides a horizontal and vertical guide for measuring in the Diagram control. The Ruler can be used to measure the Diagram objects, indicate positions, and align Diagram elements. This is especially useful in creating scale models. You can set the unit of measure, such as centimeters or inches. The default unit of measure is pixels.

Adding Rulers to the Diagram

Use the following code example to add the ruler to the Diagram.

<table>
<tr>
<td>
diagramcontrol.HorizontalRuler = new Ruler();<br/><br/>diagramcontrol.VerticalRuler = new Ruler() { Orientation = Orientation.Vertical };<br/><br/><br/><br/></td></tr>
</table>
![](Rulers_images/Rulers_img1.jpeg)


__Default__ __ruler______

Customizing the Ruler

By default, ruler segments are arranged based on measurement units.

Segment width, the textual description of the ruler segment, and the appearance of the ruler ticks can be customized. Use the following code example to customize the ruler.

<table>
<tr>
<td>
{{'__//__ '| markdownify }}{{'__Customizing__ '| markdownify }}{{'__the__ '| markdownify }}{{'__Ruler__'| markdownify }}{{'____'| markdownify }}<br/><br/>public class CustomRuler : Ruler<br/><br/>{<br/><br/>protected override RulerSegment GetNewSegment()<br/><br/>{<br/><br/>//Creating a custom segment with 12 intervals.<br/><br/>return new CustomSegment() { Intervals = 12 };<br/><br/>}<br/><br/>}<br/><br/>{{'____'| markdownify }}{{'__//__ '| markdownify }}{{'__Customizing__ '| markdownify }}{{'__RulerSegment__'| markdownify }}{{'____'| markdownify }}<br/><br/>public class CustomSegment : RulerSegment<br/><br/>{<br/><br/>protected override Tick GetNewTick()<br/><br/>{<br/><br/>return new CustomTick();<br/><br/>}<br/><br/>public override double GetSegmentWidth()<br/><br/>{<br/><br/>// Customizing the ruler segment width.<br/><br/>return 200;<br/><br/>}<br/><br/>// Customizing the label of the RulerSegment<br/><br/>protected override void UpdateLabel(TextBlock label)<br/><br/>{<br/><br/>base.UpdateLabel(label);<br/><br/>}<br/><br/>}<br/><br/>// Customizing the Ruler ticks.<br/><br/>public class CustomTick : Tick<br/><br/>{<br/><br/>// <summary><br/><br/>/// To update the ticks values start value, length, alignment<br/><br/>/// </summary><br/><br/>/// <param name="start">Start value</param><br/><br/>/// <param name="length">Length of the tick</param><br/><br/>/// <param name="align">Alignment of the tick</param><br/><br/><br/><br/>protected override void ArrangeTick(out double start, out double length, out  <br/><br/>TickAlignment align)<br/><br/>{<br/><br/>start = 0;<br/><br/>if (Value % 200 == 0)<br/><br/>{<br/><br/>length = 20;<br/><br/>}<br/><br/>else if (Value % 100 == 0 || Value % 100 < 2)<br/><br/>{<br/><br/>length = 14;<br/><br/>}<br/><br/>else if (Value % 50 == 0)<br/><br/>{<br/><br/>length = 9;<br/><br/>}<br/><br/>else<br/><br/>{<br/><br/>length = 5;<br/><br/>}<br/><br/>align = TickAlignment.RightOrBottom;<br/><br/>}<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
![](Rulers_images/Rulers_img2.jpeg)


__Customized__ __ruler__ __segments______

