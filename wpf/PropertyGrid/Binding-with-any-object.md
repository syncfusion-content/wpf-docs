---
layout: post
title: Binding-with-any-object
description: binding with any object
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Binding with any object

Denotes the object for which PropertyGrid displays Properties. You can set the SelectedObject property to any object.

Binding SelectedObject in an Application

When the SelectedObject property binds to an object, the properties of that object is then parsed and displayed in the PropertyGrid. In the below example, properties of the Customer class is parsed and displayed in the PropertyGrid.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:PropertyGrid x:Name="propertyGrid" Width="350" BorderBrush="Gray" BorderThickness="3" HorizontalAlignment="Center" VerticalAlignment="Center"/&gt;</td></tr>
<tr>
<td>
[C#]    /// &lt;summary&gt;<br>    /// Interaction logic for MainWindow.xaml<br>    /// &lt;/summary&gt;<br>    public partial class MainWindow : Window<br>    {<br>        public MainWindow()<br>        {<br>            InitializeComponent();<br>            this.propertyGrid.SelectedObject = new Customer();<br>        }<br>    }<br><br>    public class Customer<br>    {<br>        private string _name;<br>        private int _age;<br>        private DateTime _dateOfBirth;<br>        private string _SSN;<br>        private string _address;<br>        private string _email;<br>        private bool _frequentBuyer;<br>        [CategoryAttribute("ID Settings"), DescriptionAttribute("Name of the customer")]<br>        public string Name<br>        {<br>            get<br>            {<br>                return _name;<br>            }<br>            set<br>            {<br>                _name = value;<br>            }<br>        }<br><br>        [CategoryAttribute("ID Settings"),<br>        DescriptionAttribute("Social Security Number of the customer")]<br>        public string SSN<br>        {<br>            get<br>            {<br>                return _SSN;<br>            }<br>            set<br>            {<br>                _SSN = value;<br>            }<br>        }<br>        [CategoryAttribute("ID Settings"),<br>        DescriptionAttribute("Address of the customer")]<br>        public string Address<br>        {<br>            get<br>            {<br>                return _address;<br>            }<br>            set<br>            {<br>                _address = value;<br>            }<br>        }<br>        [CategoryAttribute("ID Settings"),<br>        DescriptionAttribute("Date of Birth of the Customer (optional)")]<br>        public DateTime DateOfBirth<br>        {<br>            get<br>            {<br>                return _dateOfBirth;<br>            }<br>            set<br>            {<br>                _dateOfBirth = value;<br>            }<br>        }<br>        [CategoryAttribute("ID Settings"), DescriptionAttribute("Age of the customer")]<br>        public int Age<br>        {<br>            get<br>            {<br>                return _age;<br>            }<br>            set<br>            {<br>                _age = value;<br>            }<br>        }<br>        [CategoryAttribute("Marketting Settings"), DescriptionAttribute("If the customer as bought more than 10 times, this is set to true")]<br>        public bool FrequentBuyer<br>        {<br>            get<br>            {<br>                return _frequentBuyer;<br>            }<br>            set<br>            {<br>                _frequentBuyer = value;<br>            }<br>        }<br>        [CategoryAttribute("Marketting Settings"), DescriptionAttribute("Most current e-mail of the customer")]<br>        public string Email<br>        {<br>            get<br>            {<br>                return _email;<br>            }<br>            set<br>            {<br>                _email = value;<br>            }<br>        }<br>    } <br>}</td></tr>
</table>


![](Binding-with-any-object_images/Binding-with-any-object_img1.png)
{:.image }




Properties

_SelectedObject Table_

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
SelectedObject</td><td>
Denotes the object for which PropertyGrid displays properties. User can set the SelectedObject property to any object.</td><td>
DependencyProperty</td><td>
ObjectDefault Value : Null</td><td>
</td></tr>
</table>


Sample Link

1. Select Start -> Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.
2. Select   Run Locally Installed Samples in WPF Button.
3. Now expand the PropertyGrid treeview item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



