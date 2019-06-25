---
layout: post 
title: File Support Provided by Edit Control | WPF | Syncfusion 
description: File Support Provided by Edit Control
platform: wpf
control: Syntax Editor
documentation: ug
---

# File Support

Essential Edit WPF facilitates users to create, open, modify and save text files and programming language files. EditControl provides built-in support for a variety of text based file formats such as txt, cs, VB, SQL, XAML, and XML. It also enables to specify custom file types in the custom language configurations.

## Opening a file

Opening a file in EditControl can be done in three ways.

### Using file path

The `DocumentSource` property of EditControl is used to specify the file to be opened with EditControl. The following code can be used to set the DocumentSource property.

{% tabs %}

{% highlight XAML %}
<sfedit:EditControl x:Name="editControl" DocumentSource="C:\Content.txt" ShowLineNumber="False" EnableOutlining="False"/>



{% endhighlight %}



{% highlight C# %}

editControl.DocumentSource = @"C:\Content.txt";

{% endhighlight %}

{% endtabs %}

The following image displays the contents from file set as DocumentSource window.

![Open a file in syntax editor using file path](File-Support_images/File-Support_img1.jpeg)

### Through open file dialog

Files can also be opened using the LoadFile method. LoadFile method displays a FileOpenDialog to enable you to choose the file that needs to be opened in the EditControl.

{% tabs %}

{% highlight C# %}

editControl.LoadFile();

{% endhighlight %}

{% endtabs %}

The following image displays the file open dialog.

![Open a file in syntax editor using open file dialog](File-Support_images/File-Support_img2.jpeg)

### Drag and drop file.
The Edit control allows drag and drop file by setting `AllowDrop` property to true. User can drop any type of file which is supported for Edit control.

{% tabs %}
{% highlight c# %}
this.editControl.AllowDrop = true;
{% endhighlight %}
{% highlight vb %}
Me.editControl.AllowDrop = True
{% endhighlight %}
{% endtabs %} 

## Saving the text in a file


SaveFile method in the EditControl class is used to save the text in EditControl to a file. EditControl does support saving all the built-in languages, file types and custom language file type respectively.

Enable save file, by using the following code.

{% tabs %}

{% highlight C# %}

editControl.SaveFile();



{% endhighlight %}

{% endtabs %}

The following image displays the save file dialog.

![Saving changes in a file using save file dialog](File-Support_images/File-Support_img3.jpeg)

## DocumentClosing event
By default, existing file will not be saved while loading or dropping the new file. You can control this behavior using `Document Closing` event, which  will be rasied when closing a file. You can use `HasUnsavedChanges` property to identify whether the existing file has changes or not, based on that you can choose what action to perform.

| DocumentClosingEventArgs | Description |
|---------------|-------------|
| HasUnsavedChanges | Represents a value indicating whether the file has unsaved changes |
| Action| Represents a value to specify the save actions|

| SaveAction | Description |
|---|---|
| Save | Save the changes before closing document |
| Discard | Ignore the changes and close the document |
| Cancel | Cancel the current action that is being performed |
| Prompt | Open a dialog for the user to choose one of the above action |

{% tabs %}
{% highlight c# %}

        public MainWindow()
        {
            InitializeComponent();
            editControl.DocumentClosing += EditControl_DocumentClosing;
        }

        private void EditControl_DocumentClosing(object sender, DocumentClosingEventArgs args)
        {
           if(HasUnsavedChanges)
           {
               args.Action = SaveAction.Save;
           }
        }

{% endhighlight %}
{% highlight vb %}
        
        editControl.DocumentClosing += AddressOf EditControl_DocumentClosing

        Private Sub EditControl_DocumentClosing(ByVal sender As Object, ByVal args As DocumentClosingEventArgs)
        If HasUnsavedChanges Then
        args.Action = SaveAction.Save
        End Ifargs.Action = SaveAction.Save
        End Sub

{% endhighlight %}
{% endtabs %}   
