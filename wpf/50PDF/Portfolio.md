---
layout: post
title: Portfolio
description: portfolio
platform: wpf
control: PDF
documentation: ug
---

# Portfolio

PDF Portfolio allows you to bring together content from a variety of sources (for example, PDF, Word, Excel, JPEG files) into one unified container. The original files retain their individual identities, but are assembled into a PDF Portfolio file. You can open, read, edit, and format each component file independently. 

PdfPortfolioInformation class is used to create the PDF portfolio. PdfPortfolioViewMode used to specify the view mode of the portfolio.

[C#]



//Creates a new instance of PdfDocument class.

PdfDocument document = new PdfDocument();

//Creates new portfolio.

document.PortfolioInformation = new PdfPortfolioInformation();

//Sets the view mode of portfolio.

document.PortfolioInformation.ViewMode = PdfPortfolioViewMode.Tile;

//Creates attachment.

PdfAttachment pdfFile = new PdfAttachment("CorporateBrochure.pdf");

pdfFile.FileName = "CorporateBrochure.pdf";

//Creates attachement.

PdfAttachment wordfile = new PdfAttachment("Stock.docx");

wordfile.FileName = "Stock.docx";

//Creates attachement.

PdfAttachment excelfile = new PdfAttachment("Chart.xlsx");

excelfile.FileName = "Chart.xlsx";

//Sets startup document to view.

document.PortfolioInformation.StartupDocument = pdfFile;

//Adds attachment to the document.

document.Attachments.Add(pdfFile);

document.Attachments.Add(wordfile);

document.Attachments.Add(excelfile);

//Adds new page to the document.

document.Pages.Add();

//Saves and closes the document.

document.Save("Sample.pdf");

document.Close(true);



[VB]



'Creates a new instance of PdfDocument class.

Dim document As New PdfDocument()

'Creates new portfolio.

document.PortfolioInformation = New PdfPortfolioInformation()

'Sets the view mode of the portfolio.

document.PortfolioInformation.ViewMode = PdfPortfolioViewMode.Tile

'Creates attachment.

Dim pdfFile As New PdfAttachment("CorporateBrochure.pdf")

pdfFile.FileName = "CorporateBrochure.pdf"

'Creates attachement.

Dim wordfile As New PdfAttachment("Stock.docx")

wordfile.FileName = "Stock.docx"

'Creates attachement.

Dim excelfile As New PdfAttachment("Chart.xlsx")

excelfile.FileName = "Chart.xlsx"

'Sets the startup document to view.

document.PortfolioInformation.StartupDocument = pdfFile

'Adds attachment into document.

document.Attachments.Add(pdfFile)

document.Attachments.Add(wordfile)

document.Attachments.Add(excelfile)

'Adds new page into the document.

document.Pages.Add()

'Saves and closes the document.

document.Save("Sample.pdf")

document.Close(True)

### Schema Field

Schema field is used to specify the file property such as Name, Description, and Size. You can create the custom shema using the PdfPortfolioSchema class and add the custom field into the schema using PdfPortfolioSchemaField class. Once the custom field is created, you must provide the attributes to the fields by using the PdfPortfolioAttributes class.

Please refer the following code sample.

[C#]



//Creates a new instance of PdfDocument class.

PdfDocument document = new PdfDocument();

//Creates new portfolio.

document.PortfolioInformation = new PdfPortfolioInformation();

//Sets the view mode of the portfolio.

document.PortfolioInformation.ViewMode = PdfPortfolioViewMode.Details;

//Creates portfolio schema.

PdfPortfolioSchema schema = new PdfPortfolioSchema();

//Creates portfolio schema field.

PdfPortfolioSchemaField fromField = new PdfPortfolioSchemaField();

fromField.Name =  "From";

fromField.Type = PdfPortfolioSchemaFieldType.String;

fromField.Order = 1;

fromField.Visible = true;

fromField.Editable = false;

schema.AddSchemaField(fromField);

PdfPortfolioSchemaField toField = new PdfPortfolioSchemaField();

toField.Name = "To";

toField.Type = PdfPortfolioSchemaFieldType.String;

toField.Order = 2;

toField.Visible = true;

toField.Editable = false;

schema.AddSchemaField(toField);

//Adds scehma to the portfolio.

document.PortfolioInformation.Schema = schema;

//Creates attachment.

PdfAttachment pdfFile = new PdfAttachment("CorporateBrochure.pdf");

pdfFile.FileName = "CorporateBrochure.pdf";

//Sets schema field attributed.

pdfFile.PortfolioAttributes = new PdfPortfolioAttributes();

pdfFile.PortfolioAttributes.AddAttributes("From", "steven");

pdfFile.PortfolioAttributes.AddAttributes("To", "Jhon");

//Creates attachement.

PdfAttachment wordfile = new PdfAttachment("Stock.docx");

wordfile.PortfolioAttributes = new PdfPortfolioAttributes();

wordfile.FileName = "Stock.docx";

wordfile.PortfolioAttributes.AddAttributes("From", "steven");

wordfile.PortfolioAttributes.AddAttributes("To", "Jhon");

//Creates attachement.

PdfAttachment excelfile = new PdfAttachment("Chart.xlsx");

excelfile.PortfolioAttributes = new PdfPortfolioAttributes();

excelfile.FileName = "Chart.xlsx";

excelfile.PortfolioAttributes.AddAttributes("From", "steven");

excelfile.PortfolioAttributes.AddAttributes("To", "Jhon");

//Sets the startup document to view.

document.PortfolioInformation.StartupDocument = pdfFile;

//Adds attachment to document.

document.Attachments.Add(pdfFile);

document.Attachments.Add(wordfile);

document.Attachments.Add(excelfile);

//Adds new page to document.

document.Pages.Add();

//Saves and closes the document.

document.Save("Sample.pdf");

document.Close(true);



[VB]



'Creates a new instance of PdfDocument class.

Dim document As New PdfDocument()

'Creates new portfolio.

document.PortfolioInformation = New PdfPortfolioInformation()

'Sets view mode of the portfolio.

document.PortfolioInformation.ViewMode = PdfPortfolioViewMode.Details

'Creates portfolio schema.

Dim schema As New PdfPortfolioSchema()

'Creates portfolio schema field.

Dim fromField As New PdfPortfolioSchemaField()

fromField.Name = "From"

fromField.Type = PdfPortfolioSchemaFieldType.String

fromField.Order = 1

fromField.Visible = True

fromField.Editable = False

schema.AddSchemaField(fromField)

Dim toField As New PdfPortfolioSchemaField()

toField.Name = "To"

toField.Type = PdfPortfolioSchemaFieldType.String

toField.Order = 2

toField.Visible = True

toField.Editable = False

schema.AddSchemaField(toField)

'Adds scehma to the portfolio.

document.PortfolioInformation.Schema = schema

'Creates attachment.

Dim pdfFile As New PdfAttachment("CorporateBrochure.pdf")

pdfFile.FileName = "CorporateBrochure.pdf"

'Sets schema field attributed.

pdfFile.PortfolioAttributes = New PdfPortfolioAttributes()

pdfFile.PortfolioAttributes.AddAttributes("From", "steven")

pdfFile.PortfolioAttributes.AddAttributes("To", "Jhon")

'Creates attachment.

Dim wordfile As New PdfAttachment("Stock.docx")

wordfile.PortfolioAttributes = New PdfPortfolioAttributes()

wordfile.FileName = "Stock.docx"

wordfile.PortfolioAttributes.AddAttributes("From", "steven")

wordfile.PortfolioAttributes.AddAttributes("To", "Jhon")

'Creates attachment.

Dim excelfile As New PdfAttachment("Chart.xlsx")

excelfile.PortfolioAttributes = New PdfPortfolioAttributes()

excelfile.FileName = "Chart.xlsx"

excelfile.PortfolioAttributes.AddAttributes("From", "steven")

excelfile.PortfolioAttributes.AddAttributes("To", "Jhon")

'Sets startup document to view.

document.PortfolioInformation.StartupDocument = pdfFile

'Adds attachment to document.

document.Attachments.Add(pdfFile)

document.Attachments.Add(wordfile)

document.Attachments.Add(excelfile)

'Adds new page to the document.

document.Pages.Add()

'Saves and closes the document.

document.Save("Sample.pdf")

document.Close(True)



