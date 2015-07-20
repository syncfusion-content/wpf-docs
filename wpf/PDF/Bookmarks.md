---
layout: post
title: Bookmarks
description: bookmarks
platform: wpf
control: PDF
documentation: ug
---

# Bookmarks

To ease navigation in large documents, PDF files can display a document outline in the viewer, allowing you to navigate from one page to another. The document outline consists of a tree like hierarchy of bookmark items. This tree serves as a visual table of content displaying the structure of the document. Each node in the outline can be opened or closed with the mouse. When a node is open, its immediate children are displayed. Each child can be opened or closed revealing further the parts of the hierarchy. When an item is clicked, the viewer displays the destination page associated with the item.

## Adding bookmarks

Essential PDF allows you to add bookmarks to the newly created PDF document and also to the existing PDF documents. The Add () method of PdfBookmarkBase collection class adds the bookmark to the document.

[C#]

//Creates a new document.

PdfDocument document = new PdfDocument();

//Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

float fontSize = 20f;

Font f = new Font("Arial", fontSize, FontStyle.Regular);

//Sets the font.

PdfFont font = new PdfTrueTypeFont(f, FontStyle.Regular, 12, false, true);

//Draws the text.

graphics.DrawString("Page 1", font, brush, new PointF(20, 20));

//Adds second page.

PdfPage page1 = document.Pages.Add();

page1.Graphics.DrawString("Page 2", font, brush, new PointF(0, 100));

//Creates document bookmarks.

PdfBookmark bookmark= document.Bookmarks.Add("Page 1");

//Sets the destination page.

bookmark.Destination = new PdfDestination(page);

//Sets the text style and color.

bookmark.TextStyle = PdfTextStyle.Bold;

bookmark.Color = Color.Red;

//Sets the destination location.

bookmark.Destination.Location = new PointF(20, 20);

//Creates another bookmark.

bookmark = document.Bookmarks.Add("Page 2");

//Sets the destination page and location.

bookmark.Destination = new PdfDestination(page1);

bookmark.Destination.Location = new PointF(20, 20);

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();



[VB]



'Creates a new document.

Dim document As New PdfDocument()

'Adds a page.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

Dim fontSize As Single = 20.0F

Dim f As New Font("Arial", fontSize, FontStyle.Regular)

'Sets the font.

Dim font As PdfFont = New PdfTrueTypeFont(f, FontStyle.Regular, 12, False, True)

'Draws the text.

graphics.DrawString("Page 1", font, brush, New PointF(20, 20))

'Adds second page.

Dim page1 As PdfPage = document.Pages.Add()

page1.Graphics.DrawString("Page 2", font, brush, New PointF(0, 100))

'Creates document bookmarks.

Dim bookmark As PdfBookmark = document.Bookmarks.Add("Page 1")

'Sets the destination page.

bookmark.Destination = New PdfDestination(page)

'Sets the text style and color.

bookmark.TextStyle = PdfTextStyle.Bold

bookmark.Color = Color.Red

'Sets the destination location.

bookmark.Destination.Location = New PointF(20, 20)

'Creates another bookmark.

bookmark = document.Bookmarks.Add("Page 2")

'Sets the destination page and location.

bookmark.Destination = New PdfDestination(page1)

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()



We can add new bookmarks to an existing document at any location such as in the front, middle, or at the end of the bookmarks tree. When loading an existing document, the Essential PDF loads all bookmarks of the document. Each loaded bookmark is represented by the PdfLoadedBookmark class, inherited from the PdfBookmark class. You can access the root collection of document bookmarks by using the Bookmark property of the PdfLoadedDocument class. This collection is represented by the PdfBookmarkBase class.

The following code example illustrates how to insert new bookmarks in the existing PDF document.

[C#]



//Creates a new document.

PdfLoadedDocument document = new PdfLoadedDocument("Input.pdf");

//Inserts a new bookmarks in the existing bookmark collection.

PdfBookmark bookmark = document.Bookmarks.Insert(1, "New Page 2");

//Sets the destination page and location.

bookmark.Destination = new PdfDestination(document.Pages[1]);

bookmark.Destination.Location = new PointF(0, 300);

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();



[VB]



'Creates a new document.

Dim document As New PdfLoadedDocument("Input.pdf")

'Insert a new bookmark in the existing bookmark collection.

Dim bookmark As PdfBookmark = document.Bookmarks.Insert(1, "New Page 2")

'Sets the destination page and location.

bookmark.Destination = New PdfDestination(document.Pages(1))

bookmark.Destination.Location = New PointF(0, 300)

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()

## Modifying bookmarks

Essential PDF allows you to modify the bookmarks in the existing PDF document. The Bookmarks can be modified in the following ways.

* Change the bookmark style, color, title, and destination.
* Add or insert new bookmarks into the root collection.
* Add or insert new bookmarks as a child of another bookmark.
* Assign the destination of the added bookmarks to a loaded page or a new page of the document.



[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument("Input.pdf");

//Gets all the bookmarks.

PdfBookmarkBase bookmarks = document.Bookmarks;

//Gets the first bookmark and changes the properties of the bookmark.

PdfLoadedBookmark bookmark = bookmarks[0] as PdfLoadedBookmark;

bookmark.Destination = new PdfDestination(document.Pages[1]);

bookmark.Color = Color.Green;

bookmark.TextStyle = PdfTextStyle.Bold;

bookmark.Title = "Changed title";

document.Save("Output.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument("Input.pdf")

'Gets all the bookmarks.

Dim bookmarks As PdfBookmarkBase = document.Bookmarks

'Gets the first bookmark and changes the properties of the bookmark.

Dim bookmark As PdfLoadedBookmark = TryCast(bookmarks(0), PdfLoadedBookmark)

bookmark.Destination = New PdfDestination(document.Pages(1))

bookmark.Color = Color.Green

bookmark.TextStyle = PdfTextStyle.Bold

bookmark.Title = "Changed title"

document.Save("Output.pdf")

document.Close()

## Adding Actions to Bookmark

Essential PDF allows you to add action to the specific bookmarks. You can perform action by clicking the bookmarks at the run time. You can add predefined actions to the bookmarks using the following classes.

_Class Table_

<table>
<tr>
<td>
Class Name</td><td>
Description</td></tr>
<tr>
<td>
PdfLaunchAction</td><td>
Launches an application, opens or prints a document.</td></tr>
<tr>
<td>
PdfUriAction</td><td>
Acts as a unique resource identifier.</td></tr>
<tr>
<td>
PdfJavaScriptAction</td><td>
Performs a JavaScript action in the PDF document.</td></tr>
<tr>
<td>
PdfDestination</td><td>
Represents an anchor in the document where bookmarks and annotations can direct when clicked.</td></tr>
<tr>
<td>
PdfGoToAction</td><td>
This action goes to a destination in the current document.</td></tr>
</table>


The following code sample illustrates you on how to add action to bookmarks.

[C#]



//Creates a new document.

PdfDocument document = new PdfDocument();

//Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

float fontSize = 20f;

Font f = new Font("Arial", fontSize, FontStyle.Regular);

//Sets the font.

PdfFont font = new PdfTrueTypeFont(f, FontStyle.Regular, 12, false, true);

//Draws the text.

graphics.DrawString("Page 1", font, brush, new PointF(20, 20));

//Creates JavaScript action.

PdfJavaScriptAction javaScriptAction = new PdfJavaScriptAction("app.alert(\"You are looking at Java script action of PDF \")");

//Creates document bookmarks.

PdfBookmark bookmark = document.Bookmarks.Add("Page 1");

//Sets the action to the bookmark.

bookmark.Action = javaScriptAction;

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();



[VB]



'Creates a new document.

Dim document As New PdfDocument()

'Adds a page.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

Dim fontSize As Single = 20.0F

Dim f As New Font("Arial", fontSize, FontStyle.Regular)

'Sets the font.

Dim font As PdfFont = New PdfTrueTypeFont(f, FontStyle.Regular, 12, False, True)

'Draws the text.

graphics.DrawString("Page 1", font, brush, New PointF(20, 20))

'Creates JavaSCript action.

Dim javaScriptAction As New PdfJavaScriptAction("app.alert(""You are looking at Java script action of PDF "")")

'Creates document bookmarks.

Dim bookmark As PdfBookmark = document.Bookmarks.Add("Page 1")

'Sets the action to the bookmark.

bookmark.Action = javaScriptAction

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()

## Removing a bookmarks 

You can also remove bookmarks from the existing PDF document by using the following methods of the PdfBookmarkBase class.

* Remove - This method allows you to remove the specified bookmark.
* RemoveAt - This method allows you to remove the bookmark at a specified index.



[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument("Input.pdf");

//Gets all the bookmarks.

PdfBookmarkBase bookmarks = document.Bookmarks;

//Removes bookmark by bookmark name.

bookmarks.Remove("Page 1");

//Removes bookmark by index.

bookmarks.RemoveAt(1);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument("Input.pdf")

'Gets all the bookmarks.

Dim bookmarks As PdfBookmarkBase = document.Bookmarks

'Removes bookmark by bookmark name.

bookmarks.Remove("Page 1")

'Removes bookmark by index.

bookmarks.RemoveAt(1)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()



