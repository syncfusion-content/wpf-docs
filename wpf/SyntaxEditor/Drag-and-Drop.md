---
layout: post
title: Drag and Drop | Syntax Editor | WPF | Syncfusion
description: This section explains about the drag and drop support in Syntax Editor control.
platform: wpf
control: Syntax Editor
documentation: ug
---

# Drag and Drop
The Edit control allows drag and drop file by setting `AllowDrop` property to true. User can drop any type of file which is supported for Edit control.

{% tabs %}
{% highlight c# %}
this.editControl.AllowDrop = true;
{% endhighlight %}
{% highlight vb %}
Me.editControl.AllowDrop = True
{% endhighlight %}
{% endtabs %} 

## DocumentClosing event
By default, existing file will not be saved while dropping the new file. We can use `DocumentClosing` event to set the save actions and we can use `HasUnsavedChanges` property to identify whether the existing file has changes or not. 

<table>
<tr>
<th>DocumentClosingEventArgs property</th>
<th>Description</th>
</tr>
<tr>
<th>HasUnsavedChanges</th>
<th>Represents a value indicating whether the file is modified or not.</th>
</tr>
<tr>
<th>Action</th>
<th>Represents a value to specify the save actions.</th>
</tr>
</table>

{% tabs %}
{% highlight c# %}

        public MainWindow()
        {
            InitializeComponent();
            editControl.DocumentClosing += EditControl_DocumentClosing;
        }

        private void EditControl_DocumentClosing(object sender, DocumentClosingEventArgs args)
        {
           
        }

{% endhighlight %}
{% highlight vb %}
        
        editControl.DocumentClosing += AddressOf EditControl_DocumentClosing

        Private Sub EditControl_DocumentClosing(ByVal sender As Object, ByVal args As DocumentClosingEventArgs)
        args.Action = SaveAction.Save
    End Sub

{% endhighlight %}
{% endtabs %}   

We can set the below actions while dropping the file.
*	Save
*	Discard
*	Cancel
*	Prompt

### Save
Save action type is set to save the existing file while dropping the new file in to the `EditControl`.

{% tabs %}
{% highlight c# %}
        
        private void EditControl_DocumentClosing(object sender, DocumentClosingEventArgs args)
        {
            args.Action = SaveAction.Save;
        }

{% endhighlight %}
{% highlight vb %}
            
            Private Sub EditControl_DocumentClosing(ByVal sender As Object, ByVal args As DocumentClosingEventArgs)
            args.Action = SaveAction.Save
            End Sub

{% endhighlight %}
{% endtabs %}   

### Discard
Discard action type is set to avoid the existing changes while dropping the new file in to the `EditControl`.

{% tabs %}
{% highlight c# %}
        
        private void EditControl_DocumentClosing(object sender, DocumentClosingEventArgs args)
        {
            args.Action = SaveAction.Discard;
        }

{% endhighlight %}
{% highlight vb %}
            
            Private Sub EditControl_DocumentClosing(ByVal sender As Object, ByVal args As DocumentClosingEventArgs)
            args.Action = SaveAction.Discard
            End Sub

{% endhighlight %}
{% endtabs %}   

### Cancel
Cancel action type is set to cancel the drop action so that dropped file will not be loaded.

{% tabs %}
{% highlight c# %}
        
        private void EditControl_DocumentClosing(object sender, DocumentClosingEventArgs args)
        {
            args.Action = SaveAction.Cancel;
        }

{% endhighlight %}
{% highlight vb %}
            
            Private Sub EditControl_DocumentClosing(ByVal sender As Object, ByVal args As DocumentClosingEventArgs)
            args.Action = SaveAction.Cancel
            End Sub

{% endhighlight %}
{% endtabs %}   

### Prompt  
Prompt action is set for deciding the save changes options dynamically by the user. Message box will be shown for asking save changes, so that user can save, discard or cancel the changes.

{% tabs %}
{% highlight c# %}
        
        private void EditControl_DocumentClosing(object sender, DocumentClosingEventArgs args)
        {
            args.Action = SaveAction.Prompt;
        }

{% endhighlight %}
{% highlight vb %}
            
            Private Sub EditControl_DocumentClosing(ByVal sender As Object, ByVal args As DocumentClosingEventArgs)
            args.Action = SaveAction.Prompt
            End Sub

{% endhighlight %}
{% endtabs %}   
 