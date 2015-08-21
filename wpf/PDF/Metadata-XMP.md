---
layout: post
title: Metadata-XMP
description: metadata (xmp)
platform: wpf
control: PDF
documentation: ug
---

# Metadata (XMP)

Metadata__is a data that describes the characteristics or properties of a document. It can be distinguished from the main contents__of a document. Metadata includes document information properties such as author, modification date, and copyright status.

In order to work multiple applications effectively with metadata, there must be a common standard that they understand. XMP-the Extensible Metadata Platform is designed to provide such a standard.

XMP standardizes the definition, creation, and processing of metadata.

XMP is provided with the following schemas:

* Basic Schema 
* Dublin Core Schema 
* Rights Management Schema 
* Basic Job Ticket Schema 
* Paged-Text Schema 
* PDF Schema 
## Basic Schema


Basic Schema contains properties that provide basic descriptive information such as, 

* Base URL
* Creation date
* Creator tool
* Label
* Modified date.
* Meta data date
* Nickname
* Rating

BasicSchema class is used to create the basic schema properties.

Refer the following code sample to create XMP basic schema.

{% highlight c# %}



PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

//Gets XMP object.

XmpMetadata xmp = pdfDoc.DocumentInformation.XmpMetadata;

//XMP Basic Schema.

BasicSchema basic = xmp.BasicSchema;

//Sets the basic details of the document.

basic.Advisory.Add("advisory");

basic.BaseURL = new Uri("http://google.com");

basic.CreateDate = DateTime.Now;

basic.CreatorTool = "creator tool";

basic.Identifier.Add("identifier");

basic.Label = "label";

basic.MetadataDate = DateTime.Now;

basic.ModifyDate = DateTime.Now;

basic.Nickname = "nickname";

basic.Rating.Add(-25);

//Saves the document.

pdfDoc.Save("DocumentInformation.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim pdfDoc As PdfDocument = New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Gets XMP object.

Dim xmp As XmpMetadata = pdfDoc.DocumentInformation.XmpMetadata

'XMP Basic Schema.

Dim basic As BasicSchema = xmp.BasicSchema

'set the basic details of the document

basic.Advisory.Add("advisory")

basic.BaseURL = New Uri("http://google.com")

basic.CreateDate = DateTime.Now

basic.CreatorTool = "creator tool"

basic.Identifier.Add("identifier")

basic.Label = "label"

basic.MetadataDate = DateTime.Now

basic.ModifyDate = DateTime.Now

basic.Nickname = "nickname"

basic.Rating.Add(-25)

'Saves the document.

pdfDoc.Save("DocumentInformation.pdf")
{% endhighlight %}

## Dublin Core Schema

The Dublin Core schema provides a set of commonly used properties such as,

* Contributor
* Coverage
* Creator
* Date
* Description
* Format
* Language
* Publisher
* Title

DublinCoreSchema class is used to create the Dublincore schema properties.

{% highlight c# %}



PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

//Gets XMP object.

XmpMetadata xmp = pdfDoc.DocumentInformation.XmpMetadata;

//XMP Dublincore Schema.

DublinCoreSchema dublin = xmp.DublinCoreSchema;

//Sets the Dublin Core Schema details of the document.

dublin.Creator.Add("Syncfusion");

dublin.Description.Add("Title", "Essential PDF creator");

dublin.Title.Add("Resource name", "Documentation");

dublin.Type.Add("PDF");

dublin.Publisher.Add("Essential PDF");

//Saves the document.

pdfDoc.Save("DocumentInformation.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim pdfDoc As New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Gets XMP object.

Dim xmp As XmpMetadata = pdfDoc.DocumentInformation.XmpMetadata

'XMP Dublincore Schema.

Dim dublin As DublinCoreSchema = xmp.DublinCoreSchema

'Sets the Dublin Core Schema details of the document.

dublin.Creator.Add("Syncfusion")

dublin.Description.Add("Title", "Essential PDF creator")

dublin.Title.Add("Resource name", "Documentation")

dublin.Type.Add("PDF")

dublin.Publisher.Add("Essential PDF")

'Saves the document.

pdfDoc.Save("DocumentInformation.pdf")
{% endhighlight %}

## Rights Management Schema

This schema includes properties related to rights management. These properties provide information regarding the legal restrictions associated with a resource.

* Certificate
* Marked
* Owner
* UsageTerm
* WebStatement



{% highlight c# %}



PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

//Gets XMP object.

XmpMetadata xmp = pdfDoc.DocumentInformation.XmpMetadata;

//XMP Rights Management Schema.

RightsManagementSchema rights = xmp.RightsManagementSchema;

//Sets the Dublin rights Schema details of the document.

rights.Certificate=new Uri("http://syncfusion.com");

rights.Owner.Add("Syncfusion");

rights.Marked = true;

//Saves the document.

pdfDoc.Save("DocumentInformation.pdf");

pdfDoc.Close();
{% endhighlight %}


{% highlight vbnet %}



Dim pdfDoc As New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Gets xmp object.

Dim xmp As XmpMetadata = pdfDoc.DocumentInformation.XmpMetadata

'XMP Rights Management Schema.

Dim rights As RightsManagementSchema = xmp.RightsManagementSchema

'Sets the Dublin rights Schema details of the document.

rights.Certificate = New Uri("http://syncfusion.com")

rights.Owner.Add("Syncfusion")

rights.Marked = True

'Saves the document.

pdfDoc.Save("DocumentInformation.pdf")

pdfDoc.Close()
{% endhighlight %}

## Basic Job Ticket Schema

This schema describes very simple workflow or job information.

* JobRef

{% highlight c# %}



PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

// Gets XMP object.

XmpMetadata xmp = pdfDoc.DocumentInformation.XmpMetadata;

// XMP Rights Management Schema.

BasicJobTicketSchema basicJob = xmp.BasicJobTicketSchema;

//SetS the Dublin rights Schema details of the document.

basicJob.JobRef.Add("PDF document creation");

//Saves the document.

pdfDoc.Save("DocumentInformation.pdf");

pdfDoc.Close();

{% endhighlight %}

{% highlight vbnet %}



Dim pdfDoc As New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Get XMP object.

Dim xmp As XmpMetadata = pdfDoc.DocumentInformation.XmpMetadata

'XMP Rights Management Schema.

Dim basicJob As BasicJobTicketSchema = xmp.BasicJobTicketSchema

'Sets the Dublin rights Schema details of the document.

basicJob.JobRef.Add("PDF document creation")

'Saves the document.

pdfDoc.Save("DocumentInformation.pdf")

pdfDoc.Close()
{% endhighlight %}

## Paged-Text Schema

The Paged-Text schema is used for text appearence on page in a document.

* MaxPageSize
* NPages
* Colorants
* PlateNames



{% highlight c# %}



PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

//Gets XMP object.

XmpMetadata xmp = pdfDoc.DocumentInformation.XmpMetadata;

//XMP Page text Schema.

PagedTextSchema pagedText = xmp.PagedTextSchema;

//Sets the Page text Schema details of the document.

pagedText.MaxPageSize.Width = 500;

pagedText.MaxPageSize.Height = 750;

pagedText.NPages = 1;

pagedText.PlateNames.Add("Sample page");

//Saves the document.

pdfDoc.Save("DocumentInformation.pdf");

pdfDoc.Close();

{% endhighlight %}

{% highlight vbnet %}



Dim pdfDoc As New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Gets XMP object.

Dim xmp As XmpMetadata = pdfDoc.DocumentInformation.XmpMetadata

'XMP Page text Schema.

Dim pagedText As PagedTextSchema = xmp.PagedTextSchema

'Sets the Page text Schema details of the document.

pagedText.MaxPageSize.Width = 500

pagedText.MaxPageSize.Height = 750

pagedText.NPages = 1

pagedText.PlateNames.Add("Sample page")

'Saves the document.

pdfDoc.Save("DocumentInformation.pdf")

pdfDoc.Close()
{% endhighlight %}

## PDF Schema

This schema specifies properties used with Adobe PDF documents.

PDFSchema class is used to create the PDF Schema. It has the following set of properties.

{% highlight c# %}



PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

//Gets XMP object.

XmpMetadata xmp = pdfDoc.DocumentInformation.XmpMetadata;

//XMP PDF Schema.

PDFSchema pdfSchema = xmp.PDFSchema;

//Sets the PDF Schema details of the document.

pdfSchema.Producer = "Syncfusion";

pdfSchema.PDFVersion = "1.5";

pdfSchema.Keywords = "Essential PDF";

//Saves the document.

pdfDoc.Save("DocumentInformation.pdf");

pdfDoc.Close();

{% endhighlight %}

{% highlight vbnet %}



Dim pdfDoc As New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Gets XMP object.

Dim xmp As XmpMetadata = pdfDoc.DocumentInformation.XmpMetadata

'XMP PDF Schema.

Dim pdfSchema As PDFSchema = xmp.PDFSchema

'Sets the PDF Schema details of the document.

pdfSchema.Producer = "Syncfusion"

pdfSchema.PDFVersion = "1.5"

pdfSchema.Keywords = "Essential PDF"

'Saves the document.

pdfDoc.Save("DocumentInformation.pdf")

pdfDoc.Close()
{% endhighlight %}

## Custom Schema

A custom schema defines the structure of the customized information records. You can use the CustomSchema class to: 

* Define custom metadata files and, 
* Add them to the PDF document 

Add the following code to define a custom schema. 

{% highlight c# %}



//Creates PDF document.

PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

//Gets XMP object.

XmpMetadata xmp = pdfDoc.DocumentInformation.XmpMetadata;

//Creates custom schema field.

CustomSchema cs = new CustomSchema(xmp, "custom", "http://www.syncfusion.com");

cs["Author"] = "Syncfusion";

cs["creationDate"] = DateTime.Now.ToString();

cs["DOCID"] = "SYNCSAM001";

cs["Encryption"] = "Standard";

cs["Project"] = "Data processing";

//Saves the document.

pdfDoc.Save("DocumentInformation.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates PDF document.

Dim pdfDoc As New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Gets XMP object.

Dim xmp As XmpMetadata = pdfDoc.DocumentInformation.XmpMetadata

'Creates custom schema field.

Dim cs As New CustomSchema(xmp, "custom", "http://www.syncfusion.com")

cs("Author") = "Syncfusion"

cs("creationDate") = DateTime.Now.ToString()

cs("DOCID") = "SYNCSAM001"

cs("Encryption") = "Standard"

cs("Project") = "Data processing"

'Saves the document.

pdfDoc.Save("DocumentInformation.pdf")
{% endhighlight %}

## Adding Custom Metadata

Essential PDF allows you to add required metadata (custom metadata) to a PDF document. Custom metadata can be an information about the document that cannot fit in the predefined metadata fields. For example, when a metadata field “Link” is available, you can only provide a link there. But, Essential PDF allows you to add additional information like Author, date of creation, etc. about the link. This feature allows you to add as many new metadata fields as you want. You cannot add metadata fields under the predefined metadata fields.

### How to add a custom Metadata Field

To add a custom metadata field, 

* Create an XML document container 
* Create a custom schema 
### Create an XML Document container


The custom metadata to be created has to be stored and linked to the PDF document in use. Here XML document is used as a container to save the custom metadata fields for the PDF document. 

You can add the following code to create an XML document to store custom metadata fields. 

{% highlight c# %}



XmpMetadata xmp = new XmpMetadata(pdfDoc.DocumentInformation.XmpMetadata.XmlData); 

{% endhighlight %}

{% highlight vbnet %}



Dim xmp As New XmpMetadata(pdfDoc.DocumentInformation.XmpMetadata.XmlData)

{% endhighlight %}

The following table provides more information on the code.

Property Table

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Value it accepts</th></tr>
<tr>
<td>
XmlData</td><td>
XmlElement</td><td>
XmlElement</td></tr>
</table>

### Create custom schema

Custom schema defines the structure of the customized information records. 

You can use the CustomSchema class to: 

* Define custom metadata files
* Add them to the PDF document



{% highlight c# %}



//Creates custom schema.

CustomSchema cs = new CustomSchema(xmp, "custom", "http://www.syncfusion.com");

cs["Author"] = "Syncfusion";

cs["creationDate"] = DateTime.Now.ToString();

cs["DOCID"] = "SYNCSAM001";

{% endhighlight %}

{% highlight vbnet %}



'Creates custom schema.

Dim cs As New CustomSchema(Xmp, "custom", "http://www.syncfusion.com")

cs("Author") = "Syncfusion"

cs("creationDate") = DateTime.Now.ToString()

cs("DOCID") = "SYNCSAM001"

{% endhighlight %}

The above code sample illustrates creation of custom schema or first-level metadata field [www.syncfusion.com](http://www.syncfusion.com), which is a link. The second-level metadata fields under the link are Author, creation date, and DocID.

### Full code

Full code is used to create a custom meatadata field as illustrated in the following code.

{% highlight c# %}



PdfDocument pdfDoc = new PdfDocument();

PdfPage page = pdfDoc.Pages.Add();

//Creates XML Document container.

XmpMetadata xmp = new XmpMetadata(pdfDoc.DocumentInformation.XmpMetadata.XmlData);

//Creates custom schema.

CustomSchema cs = new CustomSchema(xmp, "custom", "http://www.syncfusion.com");

cs["Author"] = "Syncfusion";

cs["creationDate"] = DateTime.Now.ToString();

cs["DOCID"] = "SYNCSAM001";

//Saves the document.

pdfDoc.Save("CustomMetaField.pdf");

pdfDoc.Close();
{% endhighlight %}


{% highlight vbnet %}



'Loads the PDF document.

Dim doDim pdfDoc As New PdfDocument()

Dim page As PdfPage = pdfDoc.Pages.Add()

'Creates XML Document container.

Dim xmp As New XmpMetadata(pdfDoc.DocumentInformation.XmpMetadata.XmlData)

'Creates custom schema.

Dim cs As New CustomSchema(xmp, "custom", "http://www.syncfusion.com")

cs("Author") = "Syncfusion"

cs("creationDate") = DateTime.Now.ToString()

cs("DOCID") = "SYNCSAM001"

'Saves the document.

pdfDoc.Save("CustomMetaField.pdf")

pdfDoc.Close()
{% endhighlight %}

Security

Essential PDF allows you to create a secure PDF document with support for user password and owner password, document encryption and access right of the document.

The document can be encrypted with 40, 128 and 256 bit key to protect its contents from unauthorized access.

The document can be protected using 2 passwords; a user password and an owner password.

User Password

The user password allows you to view the document and the access to document is restricted based on the access rights that have been set.

Owner Password

The owner password allows you to get full control over the PDF document. When both passwords are identical, you are considered to log in as owner.

Allow Print 

If this flag is not set, then you are not allowed to print the document. If this property is true, then you are allowed to print the document, depending on the value of FullQualityPrint flag and encryption key size. If encryption key size is 40 bit, then FullQualityPrint flag property is ignored. If encryption key size is 128 bit and if FullQualityPrint flag is set, then the document is printed at full quality, otherwise printing of the document is limited to a low-level representation of the document, of degraded quality. This degraded quality printing is viewer implementation dependent.

Full Quality Print 

This property has effect only when AllowPrint flag is set and encryption key size is 128 bit.

EditAnnotations

If this flag is set, it allows you to add or modify text annotations and fill in interactive forms fields.

Fill Fields

This flag is effective only when using 128 bit encryption. If this flag is set, it allows you to fill in existing interactive form fields.

Copy Content 

When document is encrypted using 128 bit and if this flag is set, it allows you to copy or otherwise extract text and graphics from the document by operations other than those controlled by AccessibilityCopyContent flag. When using a 40 bit encryption, this flag controls extraction of text and graphics to provide accessibility to disabled users and for other purposes. 

Accessibility Copy Content 

This property is effective only while using 128 bit encryption and flag set. It allows you to copy or otherwise extract text and graphics from the document to provide accessibility to disabled users and for other purposes.

## RC4 Encryption

Essential PDF allows you to encrypt your document in RC4 encryption. 

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

PdfPage page = document.Pages.Add();

PdfGraphics graphics = page.Graphics;

PdfStandardFont font = new PdfStandardFont(PdfFontFamily.TimesRoman, 20f, PdfFontStyle.Bold);

PdfBrush brush = PdfBrushes.Black;

//Document security.

PdfSecurity security = document.Security;

//Specifies key size and encryption algorithm using 40 bit key in RC4 mode.

security.KeySize = PdfEncryptionKeySize.Key40Bit;

security.Algorithm = PdfEncryptionAlgorithm.RC4;

security.OwnerPassword = "syncfusion";

security.Permissions = PdfPermissionsFlags.Print | PdfPermissionsFlags.AccessibilityCopyContent;

security.UserPassword = "password";

string text = "Security options:\n\n" + String.Format("KeySize: {0}\n\nEncryption Algorithm: {4}\n\nOwner Password: {1}\n\nPermissions: {2}\n\n" +

 "UserPassword: {3}", security.KeySize, security.OwnerPassword, security.Permissions, security.UserPassword, security.Algorithm);

graphics.DrawString("Document is Encrypted with following settings", font, brush, PointF.Empty);

font = new PdfStandardFont(PdfFontFamily.TimesRoman, 16f, PdfFontStyle.Bold);

graphics.DrawString(text, font, brush, new PointF(0, 40));

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

Dim page As PdfPage = document.Pages.Add()

Dim graphics As PdfGraphics = page.Graphics

Dim font As New PdfStandardFont(PdfFontFamily.TimesRoman, 20.0F, PdfFontStyle.Bold)

Dim brush As PdfBrush = PdfBrushes.Black

'Document security.

Dim security As PdfSecurity = document.Security

'Specifies key size and encryption algorithm, using 40 bits key in RC4 mode.

security.KeySize = PdfEncryptionKeySize.Key40Bit

security.Algorithm = PdfEncryptionAlgorithm.RC4

security.OwnerPassword = "syncfusion"

security.Permissions = PdfPermissionsFlags.Print Or PdfPermissionsFlags.AccessibilityCopyContent

security.UserPassword = "password"

Dim text As String = "Security options:" & vbLf & vbLf + [String].Format("KeySize: {0}" & vbLf & vbLf & "Encryption Algorithm: {4}" & vbLf & vbLf & "Owner Password: {1}" & vbLf & vbLf & "Permissions: {2}" & vbLf & vbLf + "UserPassword: {3}", security.KeySize, security.OwnerPassword, security.Permissions, security.UserPassword, security.Algorithm)

graphics.DrawString("Document is Encrypted with following settings", font, brush, PointF.Empty)

font = New PdfStandardFont(PdfFontFamily.TimesRoman, 16.0F, PdfFontStyle.Bold)

graphics.DrawString(text, font, brush, New PointF(0, 40))

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## AES Encryption

Essential PDF allows you to create an AES encrypted PDF document.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

PdfPage page = document.Pages.Add();

PdfGraphics graphics = page.Graphics;

PdfStandardFont font = new PdfStandardFont(PdfFontFamily.TimesRoman, 20f, PdfFontStyle.Bold);

PdfBrush brush = PdfBrushes.Black;

//Document security.

PdfSecurity security = document.Security;

//Specifies key size and encryption algorithm, using 256 bits key in AES mode.

security.KeySize = PdfEncryptionKeySize.Key256Bit;

security.Algorithm = PdfEncryptionAlgorithm.AES;

security.OwnerPassword = "syncfusion";

security.Permissions = PdfPermissionsFlags.Print | PdfPermissionsFlags.FullQualityPrint;

security.UserPassword = "password";

string text = "Security options:\n\n" + String.Format("KeySize: {0}\n\nEncryption Algorithm: {4}\n\nOwner Password: {1}\n\nPermissions: {2}\n\n" +

"UserPassword: {3}", security.KeySize, security.OwnerPassword, security.Permissions, security.UserPassword, security.Algorithm);

graphics.DrawString("Document is Encrypted with following settings", font, brush, PointF.Empty);

font = new PdfStandardFont(PdfFontFamily.TimesRoman, 16f, PdfFontStyle.Bold);

graphics.DrawString(text, font, brush, new PointF(0, 40));

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

Dim page As PdfPage = document.Pages.Add()

Dim graphics As PdfGraphics = page.Graphics

Dim font As New PdfStandardFont(PdfFontFamily.TimesRoman, 20.0F, PdfFontStyle.Bold)

Dim brush As PdfBrush = PdfBrushes.Black

'Document security.

Dim security As PdfSecurity = document.Security

'Specifies key size and encryption algorithm, using 256 bits key in AES mode.

security.KeySize = PdfEncryptionKeySize.Key256Bit

security.Algorithm = PdfEncryptionAlgorithm.AES

security.OwnerPassword = "syncfusion"

security.Permissions = PdfPermissionsFlags.Print Or PdfPermissionsFlags.FullQualityPrint

security.UserPassword = "password"

Dim text As String = "Security options:" & vbLf & vbLf + [String].Format("KeySize: {0}" & vbLf & vbLf & "Encryption Algorithm: {4}" & vbLf & vbLf & "Owner Password: {1}" & vbLf & vbLf & "Permissions: {2}" & vbLf & vbLf + "UserPassword: {3}", security.KeySize, security.OwnerPassword, security.Permissions, security.UserPassword, security.Algorithm)

graphics.DrawString("Document is Encrypted with following settings", font, brush, PointF.Empty)

font = New PdfStandardFont(PdfFontFamily.TimesRoman, 16.0F, PdfFontStyle.Bold)

graphics.DrawString(text, font, brush, New PointF(0, 40))

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

Digitally Sign the new PDF document

A digital signature is an electronic signature that is used to authenticate the identity of the sender of a message or the signer of a document, and to ensure that the original content of the message or document is unchanged. It stores information about the signee and the state of the document at the moment of signing.

Digital signatures are easily transportable, cannot be imitated by someone else, and can be automatically time-stamped. It has the ability to ensure that once the original signed message is received, the sender cannot easily repudiate it later.

List of Elements in Digital Signature

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
Appearance</td><td>
Gets the signature appearance. PdfAppearance allows you to draw and create custom appearance on the PdfSignature field.</td></tr>
<tr>
<td>
Bounds</td><td>
Gets or sets bounds of signature.</td></tr>
<tr>
<td>
Certificate</td><td>
Gets signing certificate.</td></tr>
<tr>
<td>
Certificated</td><td>
Gets or sets a value indicating certificate document or not. Allows document recipients to know if changes have been made contrary to the author's intent. Note: Works only with Adobe Reader 7.0.8 or higher.</td></tr>
<tr>
<td>
ContactInfo</td><td>
Gets or sets information provided by the signee to enable a recipient to contact the signer to verify signature; for example, a phone number.</td></tr>
<tr>
<td>
DocumentPermissions</td><td>
Gets or sets the permission for certificated document. Allows you to set permissions on certificated document with the help of PdfCertificationFlags.</td></tr>
<tr>
<td>
Field</td><td>
Gets PDF signature field.</td></tr>
<tr>
<td>
Location</td><td>
Gets or sets signature location on the page.</td></tr>
<tr>
<td>
LocationInfo</td><td>
Gets or sets the physical location of the signing.</td></tr>
<tr>
<td>
Reason</td><td>
Gets or sets the reason for signing.</td></tr>
<tr>
<td>
Visible</td><td>
Gets a value indicating whether the signature is visible or not. Allows you to create visible or invisible signatures by enabling the Visible property.</td></tr>
<tr>
<td>
TimeStampServer</td><td>
Sets the timestamp for the signature. Allows you to include timestamp for the digital signature.</td></tr>
</table>


Standard Signature

PdfCertificate class is used to get the certificates from disk or another device such as PFX file. The PFX file type is an encrypted security file that stores secure certificates that are used to authenticate a PDF document. One needs a password to access these files. The PFX files are supported with private keys.

PdfSignature class has methods and properties that allow setting the signature information such as reason, location information, bounds where the signature has to be placed, and contact information.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page.

PdfPage page = document.Pages.Add();

PdfGraphics graphics = page.Graphics;

//Creates a certificate instance from PFX file with private key.

PdfCertificate pdfCert = new PdfCertificate(@"PDF.pfx", "syncfusion");

//Creates a digital signature.

PdfSignature signature = new PdfSignature(page, pdfCert, "Signature");

//Sets an image for signature field.

PdfBitmap bmp = new PdfBitmap(@"syncfusion_logo.gif");

//Sets signature info.

signature.Bounds = new RectangleF(new PointF(0, 0), bmp.PhysicalDimension);

signature.ContactInfo = "johndoe@owned.us";

signature.LocationInfo = "Honolulu, Hawaii";

signature.Reason = "I am author of this document.";

//Draws the signature image.

graphics.DrawImage(bmp, 0, 0);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = document.Pages.Add()

Dim graphics As PdfGraphics = page.Graphics

'Creates a certificate instance from PFX file with private key.

Dim pdfCert As New PdfCertificate("PDF.pfx", "syncfusion")

'Creates a digital signature.

Dim signature As New PdfSignature(page, pdfCert, "Signature")

'Sets an image for signature field.

Dim bmp As New PdfBitmap("syncfusion_logo.gif")

'Sets signature info.

signature.Bounds = New RectangleF(New PointF(0, 0),                 bmp.PhysicalDimension)

signature.ContactInfo = "johndoe@owned.us"

signature.LocationInfo = "Honolulu, Hawaii"

signature.Reason = "I am author of this document."

'Draws the signature image.

graphics.DrawImage(bmp, 0, 0)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()

{% endhighlight %}

Author Signature

By default, documents are signed with standard signature types. Certificated property of PdfSignature is used to create author’s signature. When signed with this type of signature, any modification after signing is detected, and hence do not support added multiple signatures.

> Note: This implementation of certification will only work with Acrobat 7 and higher versions.



{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page.

PdfPage page = document.Pages.Add();

PdfGraphics graphics = page.Graphics;

//Creates a certificate instance from PFX file with private key.

PdfCertificate pdfCert = new PdfCertificate(@"PDF.pfx", "syncfusion");

//Creates a digital signature.

PdfSignature signature = new PdfSignature(page, pdfCert, "Signature");

//Sets author’s signature.

signature.Certificated = true;

//Sets an image for signature field.

PdfBitmap bmp = new PdfBitmap(@"syncfusion_logo.gif");

//Sets signature info.

signature.Bounds = new RectangleF(new PointF(0, 0), bmp.PhysicalDimension);

signature.ContactInfo = "johndoe@owned.us";

signature.LocationInfo = "Honolulu, Hawaii";

signature.Reason = "I am author of this document.";

//Draws the signature image.

graphics.DrawImage(bmp, 0, 0);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = document.Pages.Add()

Dim graphics As PdfGraphics = page.Graphics

'Creates a certificate instance from PFX file with private key.

Dim pdfCert As New PdfCertificate("PDF.pfx", "syncfusion")

'Creates a digital signature.

Dim signature As New PdfSignature(page, pdfCert, "Signature")

'Sets author’s signature.

signature.Certificated = True

'Sets an image for signature field.

Dim bmp As New PdfBitmap("syncfusion_logo.gif")

'Sets signature info.

signature.Bounds = New RectangleF(New PointF(0, 0), bmp.PhysicalDimension)

signature.ContactInfo = "johndoe@owned.us"

signature.LocationInfo = "Honolulu, Hawaii"

signature.Reason = "I am author of this document."

'Draws the signature image.

graphics.DrawImage(bmp, 0, 0)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## Digitally Sign the existing PDF document

Essential PDF allows you to put signature in an existing PDF document as in a newly created PDF.

{% highlight c# %}



//Creates a new PDF document.

PdfLoadedDocument document = new PdfLoadedDocument("Input.pdf");

//Adds a new page.

PdfPageBase page = document.Pages[0];

PdfGraphics graphics = page.Graphics;

//Creates a certificate instance from PFX file with private key.

PdfCertificate pdfCert = new PdfCertificate(@"PDF.pfx", "syncfusion");

//Creates a digital signature.

PdfSignature signature = new PdfSignature(document, page, pdfCert, "Signature");

//Sets an image for signature field.

PdfBitmap bmp = new PdfBitmap(@"syncfusion_logo.gif");

//Sets signature info.

signature.Bounds = new RectangleF(new PointF(0, 0), bmp.PhysicalDimension);

signature.ContactInfo = "johndoe@owned.us";

signature.LocationInfo = "Honolulu, Hawaii";

signature.Reason = "I am author of this document.";

//Draws the signature image.

graphics.DrawImage(bmp, 0, 0);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = document.Pages.Add()

Dim graphics As PdfGraphics = page.Graphics

'Creates a certificate instance from PFX file with private key.

Dim pdfCert As New PdfCertificate("PDF.pfx", "syncfusion")

'Creates a digital signature.

Dim signature As New PdfSign.ature(page, pdfCert, "Signature")

'Sets author’s signature.

signature.Certificated = True

'Sets an image for signature field.

Dim bmp As New PdfBitmap("syncfusion_logo.gif")

'Sets signature info.

signature.Bounds = New RectangleF(New PointF(0, 0), bmp.PhysicalDimension)

signature.ContactInfo = "johndoe@owned.us"

signature.LocationInfo = "Honolulu, Hawaii"

signature.Reason = "I am author of this document."

'Draws the signature image.

graphics.DrawImage(bmp, 0, 0)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## Timestamp in Digital signature

Essential PDF supports addition of timestamp in digital signatures. The date and time on which the document is signed can be added as part of the signature. Timestamps are easier to verify when they are associated with timestamp authority’s trusted certificate.  It also helps establish exactly when the document was signed and reduces the chances of an invalid signature. The timestamp can be obtained from a third-party timestamp authority or from the certificate authority that issued the digital ID.

Timestamps appear in the signature field and in the Signature Properties dialog box. When the timestamp is included, the certificate appears in the Date or Time tab of the Signature Properties dialog box. When no timestamp is added, then the signature field displays the local time of the computer at the moment of signing.

To apply timestamp using Essential PDF, the TimeStampServer property of the PdfSignature class has to be used. The parameters for the TimeStampMethod are the URI of digital server, username, and password.

The following code illustrates the method for adding timestamp in the digital signature.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page.

PdfPage page = document.Pages.Add();

PdfGraphics graphics = page.Graphics;

//Creates a certificate instance from PFX file with private key.

PdfCertificate pdfCert = new PdfCertificate(@"PDF.pfx", "syncfusion");

//Creates a digital signature.

PdfSignature signature = new PdfSignature(page, pdfCert, "Signature");

//Sets an image for signature field

PdfBitmap bmp = new PdfBitmap(@"syncfusion_logo.gif");

//Adds time stamp using the server URI and credentials.

signature.TimeStampServer = new TimeStampServer(new Uri("http://digistamp.syncfusion.com"), "user", "123456");

//Sets signature info.

signature.Bounds = new RectangleF(new PointF(0, 0), bmp.PhysicalDimension);

signature.ContactInfo = "johndoe@owned.us";

signature.LocationInfo = "Honolulu, Hawaii";

signature.Reason = "I am author of this document.";

//Draws the signature image.

graphics.DrawImage(bmp, 0, 0);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = document.Pages.Add()

Dim graphics As PdfGraphics = page.Graphics

'Creates a certificate instance from PFX file with private key.

Dim pdfCert As New PdfCertificate("PDF.pfx", "syncfusion")

'Creates a digital signature.

Dim signature As New PdfSignature(page, pdfCert, "Signature")

'Adds time stamp using the server URI and credentials.

signature.TimeStampServer = New TimeStampServer(New Uri("http://digistamp.syncfusion.com"), "user", "123456")

'Sets an image for signature field.

Dim bmp As New PdfBitmap("syncfusion_logo.gif")

'Sets signature info.

signature.Bounds = New RectangleF(New PointF(0, 0), bmp.PhysicalDimension)

signature.ContactInfo = "johndoe@owned.us"

signature.LocationInfo = "Honolulu, Hawaii"

signature.Reason = "I am author of this document."

'Draws the signature image.

graphics.DrawImage(bmp, 0, 0)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close()

{% endhighlight %}



