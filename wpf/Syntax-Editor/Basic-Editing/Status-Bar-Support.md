---
layout: post
title: Status Bar | Syntax Editor | WPF | Syncfusion
description: The Status Bar in Edit Control shows file path, encoding type, line number and column number. Customization can aslo be achieved in status Bar.
platform: WPF
control: Syntax Editor
documentation: ug
---

# Status Bar Support

 The edit control status bar option is used to view primary information such as the loaded document's file path, encoding type, line number and column number based on the cursor position. By default, status bar visibility is set to be false 

The Status Bar can be enabled/disabled by setting it's visibility and the default properties are displayed in it by enabling the status bar. The Status Bar can be enabled by,

{% tabs %}

{% highlight XAML %}

<!--Adding EditControl to application and setting its StatusBarVisiblity to Visible-->

<syncfusion:EditControl Background="White" Name="EditControl1">
   <syncfusion:EditControl.StatusBarSettings >
      <syncfusion:StatusBarSettings Visibility="Visible"/>
   </syncfusion:EditControl.StatusBarSettings>
</syncfusion:EditControl> 


{% endhighlight %}

{% highlight C# %}

public partial class MainWindow : Window

{

public MainWindow()

{

InitializeComponent();

this.EditControl1.DocumentSource = "../../Source.cs";

this.EditControl1.StatusBarSettings.Visibility = Visibility.Visible;

}

}

{% endhighlight %}

{% highlight VB %}

public partial class MainWindow : Window

{

public MainWindow()

{

InitializeComponent();

Me.EditControl1.DocumentSource = "../../Source.cs";

Me.EditControl1.StatusBarSettings.Visibility = Visibility.Visible;

}

}

{% endhighlight %}

{% endtabs %}

When application executes the following screenshot displays how the Status Bar is added in Edit Control,

![Status Bar](Status-Bar_images/StatusBar_Visibility.png)

**Status Bar Properties**

Status bar shows the file path, encoding type, line number and column number. The visibility of each item in the status bar can be customized by using the below properties.
 
  * **ShowFilePath**: It shows the exact application directory and the file path which was loaded in Edit Control. File Path property can be enabled/disabled by changing it's Visibility property.
  * **ShowLineNumber**: It shows the current line number where the cursor is placed on Edit Control. By changing it's visibility user can enable/disable the line number property.
  * **ShowColumnNumber**: It shows the current column number where the cursor is placed on Edit Control. By changing it's visibility user can enable/disable the Column number property.
  * **ShowEncoding**: It shows the current Encoding type of the loaded file in Edit Control. Encoding property can be enable/disable by changing it's visibility property.

User can also able to handle the default properties by changing it's visibility property and it can be achieved by,

{% tabs %}

{% highlight XAML %}

<!--Adding EditControl to application and setting its StatusBarVisiblity to Visible-->

<syncfusion:EditControl Background="White" Name="EditControl1">
   <syncfusion:EditControl.StatusBarSettings >
      <syncfusion:StatusBarSettings Visibility="Visible" ShowFilePath="Visible" ShowLineNumber="Visible" ShowColumnNumber="Visible" ShowEncoding="Visible"/>
   </syncfusion:EditControl.StatusBarSettings>
</syncfusion:EditControl> 


{% endhighlight %}

{% highlight C# %}

public partial class MainWindow : Window

{

public MainWindow()

{

InitializeComponent();

this.EditControl1.DocumentSource = "../../Source.cs";

this.EditControl1.StatusBarSettings.Visibility = Visibility.Visible;
this.EditControl1.StatusBarSettings.ShowFilePath = Visibility.Visible;
this.EditControl1.StatusBarSettings.ShowLineNumber = Visibility.Visible;
this.EditControl1.StatusBarSettings.ShowColumnNumber = Visibility.Visible;
this.EditControl1.StatusBarSettings.ShowEncoding = Visibility.Visible;

}

}

{% endhighlight %}

{% highlight VB %}

public partial class MainWindow : Window

{

public MainWindow()

{

InitializeComponent();

Me.EditControl1.DocumentSource = "../../Source.cs";

Me.EditControl1.StatusBarSettings.Visibility = Visibility.Visible;
Me.EditControl1.StatusBarSettings.ShowFilePath = Visibility.Visible;
Me.EditControl1.StatusBarSettings.ShowLineNumber = Visibility.Visible;
Me.EditControl1.StatusBarSettings.ShowColumnNumber = Visibility.Visible;
Me.EditControl1.StatusBarSettings.ShowEncoding = Visibility.Visible;

}

}

{% endhighlight %}

{% endtabs %}

User can able to customize the default properties by changing it's Visibility. The following screenshot displays after changing the Show Encoding visibility property changed to Collapsed,

![Status Bar](Status-Bar_images/StatusBar_Properties.png)


### Status Bar Customization

Status Bar can be customized by enabling the context menu on right clicking the designer XAML file and in that click edit control template then user can append that template to the current edit control class or can able to create a copy on it. In that, user can be able to modify the status bar template according to their needed.

Then user can able to add a Progress Bar or a TextBox as needed to be displayed in that Status Bar by modifying the default template in it.

The following Screenshots shows how the Status Bar in Edit Control template can be modified and displayed. In this, the Progress Bar and TextBox is added by editing the template of Edit Control,

**Status Bar Edit Template**

![Status Bar](Status-Bar_images/StatusBar_Template.png)

**Creating a template copy to Edit Control**

![Status Bar](Status-Bar_images/StatusBar_Copy.png)

**Modifying the codes in XAML**

![Status Bar](Status-Bar_images/StatusBar_Template_XAML.png)

**Status Bar Customization**

![Status Bar](Status-Bar_images/StatusBar_Customization.png)


### Styling in Status Bar

Styling for Status Bar can be applied through the Skin Storage set in XAML. This feature supports the following built-in styles,

* Blend

* Default

* Metro

* Office2007Black

* Office2007Blue

* Office2007Silver

* VS2010

The following illustrations shows how the Status Bar is applied with different built-in styles.

**Blend**

![Status Bar](Status-Bar_images/StatusBar_BlendStyle.png)

**Default**

![Status Bar](Status-Bar_images/StatusBar_DefaultStyle.png)

**Metro**

![Status Bar](Status-Bar_images/StatusBar_MetroStyle.png)

**Office2007Black**

![Status Bar](Status-Bar_images/StatusBar_Office2007BlackStyle.png)

**Office2007Blue**

![Status Bar](Status-Bar_images/StatusBar_Office2007BlueStyle.png)

**Office2007Silver**

![Status Bar](Status-Bar_images/StatusBar_Office2007SilverStyle.png)

**VS2010**

![Status Bar](Status-Bar_images/StatusBar_VS2010Style.png)
