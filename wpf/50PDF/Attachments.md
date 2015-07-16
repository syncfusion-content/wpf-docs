---
layout: post
title: Attachments
description: attachments
platform: wpf
control: PDF
documentation: ug
---

# Attachments

File attachment contains a reference to a file that is typically embedded in the PDF file. It can be viewed in the attachment pane of the Adobe reader. Activating the attachment extracts the embedded file and gives you an opportunity to view or store it in the file system. Essential PDF provides support for adding, deleting, and extracting annotations from PDF document.

## Add attachment in a PDF document

In order to add attachment to a PDF document, you need to create PdfAttachment object for the file, with description. After that the PdfAttachment object can be added to attachment collection of document object using collection’s Add method. 

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates an attachment.

PdfAttachment attachment = new PdfAttachment("Input.txt");

attachment.ModificationDate = DateTime.Now;

attachment.Description = "Input.txt";

attachment.MimeType = "application/txt";

//Adds the attachment to the document

document.Attachments.Add(attachment);

//Adds a page to the document.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics g = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

//Sets the font.

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 12);

//Draws the text.

g.DrawString("This document contains attachments. To view the attachment click on attachment in Acrobat/Adobe Reader in Navigation tab", font, brush, new RectangleF(0, 0,page.GetClientSize().Width, page.GetClientSize().Height));

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates an attachment.

Dim attachment As New PdfAttachment("Input.txt")

attachment.ModificationDate = DateTime.Now

attachment.Description = "Input.txt"

attachment.MimeType = "application/txt"

'Adds attachment to the document.

document.Attachments.Add(attachment)

'Adds a page to the document.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim g As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

'Sets the font.

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, 12)

'Draws the text.

g.DrawString("This document contains attachments. To view the attachment click on attachment in Acrobat/Adobe Reader in Navigation tab", font, brush, New RectangleF(0, 0, page.GetClientSize().Width, page.GetClientSize().Height))

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()





Essential PDF allows you to add attachments to the existing PDF document.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument("Input.pdf");

//Checks whether the PDF document already has attachments.

if (document.Attachments == null)

document.CreateAttachment();

//Creates an attachment.

PdfAttachment attachment = new PdfAttachment("Input.txt");

attachment.ModificationDate = DateTime.Now;

attachment.Description = "Input.txt";

attachment.MimeType = "application/txt";

//Adds the attachment to the document.

document.Attachments.Add(attachment);

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument("Input.pdf")

'Checks whether the PDF document already has attachments.

If document.Attachments Is Nothing Then

document.CreateAttachment()

End If

'Creates an attachment.

Dim attachment As New PdfAttachment("Input.txt")

attachment.ModificationDate = DateTime.Now

attachment.Description = "Input.txt"

attachment.MimeType = "application/txt"

'Adds the attachment to the document.

document.Attachments.Add(attachment)

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()

## Delete attachments from PDF LoadedDocument

In order to remove an attachment from an existing PDF document, you need to use the remove method of the PdfAttachmentCollection class. 

* Remove
* RemoveAt



[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument("Input.pdf");

//Removes attachments.

PdfAttachment attachment = document.Attachments[0];

document.Attachments.Remove(attachment);

document.Attachments.RemoveAt(1);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument("Input.pdf")

'Removes attachments.

Dim attachment As PdfAttachment = document.Attachments(0)

document.Attachments.Remove(attachment)

document.Attachments.RemoveAt(1)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()

## Extracting the attachments

In order to get all the attachments from the PDF file, you need to loop through the PdfAttachmentCollection of the Document object. Each element of this collection represents a PdfAttachment object. All iterations in for-each loop through the PdfAttachmentCollection collection will return a PdfAttachment object. Once this object is available, you can retrieve either all the properties of the attached file or the file itself.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument("Input.pdf");

//Iterates the attachments.

foreach (PdfAttachment attachment in document.Attachments)

{

//Creates attachment file.

FileStream s = new FileStream(attachment.FileName, FileMode.Create);

s.Write(attachment.Data, 0, attachment.Data.Length);

s.Dispose();

}

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument("Input.pdf")

'Iterates the attachments.

 For Each attachment As PdfAttachment In document.Attachments

'Creates attachment file.

Dim s As New FileStream(attachment.FileName, FileMode.Create)

s.Write(attachment.Data, 0, attachment.Data.Length)

s.Dispose()

Next

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()



