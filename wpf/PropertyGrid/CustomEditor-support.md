---
layout: post
title: CustomEditor-support
description: customeditor support
platform: wpf
control: PropertyGrid 
documentation: ug
---

# CustomEditor support

The PropertyGrid control supports several built-in editors, to give a good look and feel for the application (like in Expression Blend). Using CustomEditors or CategoryEditors. CustomEditor support enables you to set custom value editors for particular properties, instead of default editors.

Adding CustomEditor support to an Application 

Using CustomEditorCollection property user can add custom editors to PropertyGrid control. To create CustomEditor user needs to implement ITypeEditor interface. In the below example for Background(Type – Brush), by default ColorPicker will be displayed as ValueEditor. By setting CustomEditor for Background, ColorEdit will be displayed as ValueEditor instead of ColorPicker.



<table>
<tr>
<td>
[XAML]    &lt;Grid x:Name="LayoutRoot" Background="White" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"&gt;<br>        &lt;Button Height="25" Width="100" VerticalAlignment="Top" x:Name="Btn"/&gt;<br>        &lt;syncfusion:PropertyGrid x:Name="propertyGrid" SelectedObject="{Binding ElementName=Btn}" Margin="50" Width="500" BorderBrush="Gray" BorderThickness="3" HorizontalAlignment="Center" VerticalAlignment="Center"/&gt;<br>    &lt;/Grid&gt;</td></tr>
<tr>
<td>
[C#]    /// &lt;summary&gt;<br>    /// Interaction logic for MainWindow.xaml.<br>    /// &lt;/summary&gt;<br>    public partial class MainWindow : Window<br>    {<br>        /// &lt;summary&gt;<br>        /// Initializes a new instance of the &lt;see cref="MainWindow"/&gt; class.<br>        /// &lt;/summary&gt;<br>        public MainWindow()<br>        {<br>            InitializeComponent();<br>            // Creating CustomEditor for Background.<br>            CustomEditor editor = new CustomEditor();<br>            editor.Properties.Add("Background");<br>            editor.Editor = new ColorEditEditor();<br>            this.propertyGrid.CustomEditorCollection.Add(editor);<br>        }<br>    }<br><br>    public class ColorEditEditor : ITypeEditor<br>    {<br>        public void Attach(PropertyViewItem property, PropertyItem info)<br>        {<br>            if (info.CanWrite)<br>            {<br>                var binding = new Binding("Value")<br>                {<br>                    Mode = BindingMode.TwoWay,<br>                    Source = info,<br>                    ValidatesOnExceptions = true,<br>                    ValidatesOnDataErrors = true<br>                };<br>                BindingOperations.SetBinding(colorEdit, ColorEdit.BrushProperty, binding);<br>            }<br>            else<br>            {<br>                var binding = new Binding("Value")<br>                {<br>                    Mode = BindingMode.OneWayToSource,<br>                    Source = info,<br>                    ValidatesOnExceptions = true,<br>                    ValidatesOnDataErrors = true<br>                };<br>                BindingOperations.SetBinding(colorEdit, ColorEdit.BrushProperty, binding);<br>            }<br>        }<br><br>        public ColorEdit colorEdit;<br>        public object Create(System.Reflection.PropertyInfo PropertyInfo)<br>        {<br>            colorEdit = new ColorEdit();<br>            return colorEdit;<br>        }<br><br>        public void Detach(PropertyViewItem property)<br>        {<br>            throw new NotImplementedException();<br>        }<br>    }</td></tr>
</table>


![](CustomEditor-support_images/CustomEditor-support_img1.png)
{:.image }




Properties



_CustomEditor Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
<tr>
<td>
CustomEditorCollection</td><td>
CustomEditor support enables you to set custom value editors for particular properties, instead of default editors.</td><td>
DependencyProperty</td><td>
CustomEditorCollection</td><td>
</td></tr>
</table>


Sample Link

1. Select Start -> Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.
2. Select   Run Locally Installed Samples in WPF Button.
3. Now expand the PropertyGrid treeview item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



