---
layout: post
title: Forms
description: forms
platform: wpf
control: PDF
documentation: ug
---

# Forms

An interactive form, sometimes referred to as an AcroForm is a collection of fields for gathering information. A PDF document can contain any number of fields appearing on any combination of pages, all of that make a single, globally interactive form spanning the entire document. Essential PDF allows you to create forms in the PDF document and also allows you to edit and fill the form fields in the existing PDF document.

## Add form fields in a PDF document

The PdfForm class provides a collection of named Fields that helps in managing form fields in PDF document. First, you create a form field to add to the PDF document, then you can add those form fields to the PDF document by calling the Fields collection’s Add method.

This section covers the following:

* Create a form field and set its properties
* Adding form fields to the Fields collection
### Adding TextBox field


A text field is a box or space where you can enter text through the keyboard. The text can be restricted to a single line or permitted to span multiple lines, depending on the value given to Multiline flag. PdfTextBoxField class is used to create a textbox field in PDF forms. This class also provides support to create password and multiline text boxes. 

The following code example illustrates this. 

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page to PDF document.

PdfPage page = document.Pages.Add();

//Creates a Text box field.

PdfTextBoxField textBoxField = new PdfTextBoxField(page, "FirstName");

//Sets properties to the textbox.

textBoxField.BorderColor = new PdfColor(Color.Gray);

textBoxField.BorderStyle = PdfBorderStyle.Beveled;

textBoxField.Bounds = new RectangleF(0, 0, 100, 20);

textBoxField.ToolTip = "First Name";

//Adds the form field to the document.

document.Form.Fields.Add(textBoxField);

//Saves the document.

document.Save("Form.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page to PDF document.

Dim page As PdfPage = document.Pages.Add()

'Creates a Text box field.

Dim textBoxField As New PdfTextBoxField(page, "FirstName")

'Sets properties to the textbox.

textBoxField.BorderColor = New PdfColor(Color.Gray)

textBoxField.BorderStyle = PdfBorderStyle.Beveled

textBoxField.Bounds = New RectangleF(0, 0, 100, 20)

textBoxField.ToolTip = "First Name"

'Adds the form field to the document.

document.Form.Fields.Add(textBoxField)

'Saves the PDF document.

document.Save("Form.pdf")

document.Close()

### Adding Button field

A button field represents an interactive control on the screen that you can manipulate using the mouse. PdfButtonField class is used to create Buttons fields.

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page to PDF document.

PdfPage page = document.Pages.Add();

//Creates a Button.

PdfButtonField button = new PdfButtonField(page, "Click");

//Sets properties to the Button field.

button.Bounds = new RectangleF(0, 150, 90, 20);

button.Text = "Click";

//Adds the form field to the document.

document.Form.Fields.Add(button);

//Saves the document.

document.Save("Form.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page to PDF document.

Dim page As PdfPage = document.Pages.Add()

'Creates a Button.

Dim button As New PdfButtonField(page, "Click")

'Sets properties to the Button field.

button.Bounds = New RectangleF(0, 150, 90, 20)

button.Text = "Click"

'Adds the form field to the document.

document.Form.Fields.Add(button)

'Saves the PDF document.

document.Save("Form.pdf")

document.Close()

### Adding Check Box field

A check box is a graphical user interface element that allows you to make binary choice i.e., a choice between one of two mutually exclusive options. 

PdfCheckBoxField class is used to create a check box in PDF forms. You can customize the check box style by using properties such as BorderStyle, HighlightMode, BorderWidth, etc.

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page to PDF document.

PdfPage page = document.Pages.Add();

//Creates Check Box field.

PdfCheckBoxField checkBoxField = new PdfCheckBoxField(page, "CheckBox");

//Sets check box properties.

checkBoxField.ToolTip = "Check Box";

checkBoxField.Bounds = new RectangleF(0, 20, 10, 10);

checkBoxField.BorderColor = new PdfColor(Color.Gray);

//Adds the form field to the document.

document.Form.Fields.Add(checkBoxField);

//Saves the document.

document.Save("Form.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()



'Adds a new page to PDF document.

Dim page As PdfPage = document.Pages.Add()

'Sets check box properties.

checkBoxField.ToolTip = "Check Box"

checkBoxField.Bounds = New RectangleF(0, 20, 10, 10)

checkBoxField.BorderColor = New PdfColor(Color.Gray)

'Adds the form field to the document.

document.Form.Fields.Add(checkBoxField)

'Saves the PDF document.

document.Save("Form.pdf")

document.Close()

### Adding Combo box field

A combo box represents a drop-down list of choices for selection, optionally accompanied by an editable text box where you can type a value other than the predefined choices. 

PdfComboBoxField class is used to create a combo box field in PDF forms. You can add a list of items to the combo box by using the PdfListFieldItem class.

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page to PDF document.

PdfPage page = document.Pages.Add();

//Creates a combo box for the first page.

PdfComboBoxField comboBox = new PdfComboBoxField(page, "JobTitle");

//Sets the combo box properties.

comboBox.Bounds = new RectangleF(0, 40, 100, 20);

comboBox.BorderWidth = 1;

comboBox.BorderColor = new PdfColor(Color.Gray);

//Sets tooltip.

comboBox.ToolTip = "Job Title";

//Adds list items.

comboBox.Items.Add(new PdfListFieldItem("Development", "accounts"));

comboBox.Items.Add(new PdfListFieldItem("Support", "advertise"));

comboBox.Items.Add(new PdfListFieldItem("Documentation", "agri"));

//Adds combo box to the form.

document.Form.Fields.Add(comboBox);

//Saves the document.

document.Save("Form.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page to PDF document.

Dim page As PdfPage = document.Pages.Add()

'Creates a combo box for the first page.

Dim comboBox As New PdfComboBoxField(page, "JobTitle")

'Sets the combo box properties.

comboBox.Bounds = New RectangleF(0, 40, 100, 20)

comboBox.BorderWidth = 1

comboBox.BorderColor = New PdfColor(Color.Gray)

'Sets tooltip

comboBox.ToolTip = "Job Title"

'Adds list items.

comboBox.Items.Add(New PdfListFieldItem("Development", "accounts"))

comboBox.Items.Add(New PdfListFieldItem("Support", "advertise"))

comboBox.Items.Add(New PdfListFieldItem("Documentation", "agri"))

'Adds combo box to the form.

document.Form.Fields.Add(comboBox)

'Saves the PDF document.

document.Save("Form.pdf")

document.Close()

### Adding List box field

A scrollable List Box contains several text items, one or more of that can be selected as the field value. PdfListBoxField is used to create the ListBox field in PDF forms.

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page to PDF document.

PdfPage page = document.Pages.Add();

//Creates list box.

PdfListBoxField listBox = new PdfListBoxField(page, "list1");

//Sets the properties.

listBox.Bounds = new RectangleF(100, 60, 100, 50);

listBox.HighlightMode = PdfHighlightMode.Outline;

//Adds the items to the list box.

listBox.Items.Add(new PdfListFieldItem("English", "English"));

listBox.Items.Add(new PdfListFieldItem("French", "French"));

listBox.Items.Add(new PdfListFieldItem("German", "German"));

//Selects the item.

listBox.SelectedIndex = 2;

//Sets the multiselect option.

listBox.MultiSelect = true;

document.Form.Fields.Add(listBox);

//Saves the document.

document.Save("Form.pdf");

document.Close();





[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page to PDF document.

Dim page As PdfPage = document.Pages.Add()

'Creates list box.

Dim listBox As New PdfListBoxField(page, "list1")

'Sets the properties.

listBox.Bounds = New RectangleF(100, 60, 100, 50)

listBox.HighlightMode = PdfHighlightMode.Outline

'Adds the items to the list box.

listBox.Items.Add(New PdfListFieldItem("English", "English"))

listBox.Items.Add(New PdfListFieldItem("French", "French"))

listBox.Items.Add(New PdfListFieldItem("German", "German"))

'Selects the item.

listBox.SelectedIndex = 2

'Sets the multiselect option.

listBox.MultiSelect = True

document.Form.Fields.Add(listBox)

'Saves the PDF document.

document.Save("Form.pdf")

document.Close()

### Adding Radio button field

Radio button fields contain a set of related buttons that can be set to ON or OFF individually. Typically, at most one radio button in a set can be ON at any given time, and selecting any one of the button automatically de-selects the others. 

PdfRadioButtonListField class is used to create a radio button in the PDF Forms. You can create the radio button list items by using the PdfRadioButtonListItem class.

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page to PDF document.

PdfPage page = document.Pages.Add();

//Creates a Radio button.

PdfRadioButtonListField employeesRadioList = new PdfRadioButtonListField(page, "employeesRadioList");

document.Form.Fields.Add(employeesRadioList);

//Creates radio button items.

PdfRadioButtonListItem radioItem1 = new PdfRadioButtonListItem("1-9");

radioItem1.Bounds = new RectangleF(100, 140, 20, 20);

PdfRadioButtonListItem radioItem2 = new PdfRadioButtonListItem("10-49");

radioItem2.Bounds = new RectangleF(100, 170, 20, 20);

//Adds the items to radio button group.

employeesRadioList.Items.Add(radioItem1);

employeesRadioList.Items.Add(radioItem2);

//Saves the document.

document.Save("Form.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page to PDF document.

Dim page As PdfPage = document.Pages.Add()

'Creates a Radio button.

Dim employeesRadioList As New PdfRadioButtonListField(page, "employeesRadioList")

document.Form.Fields.Add(employeesRadioList)

'Creates radio button items.

Dim radioItem1 As New PdfRadioButtonListItem("1-9")

radioItem1.Bounds = New RectangleF(100, 140, 20, 20)

Dim radioItem2 As New PdfRadioButtonListItem("10-49")

radioItem2.Bounds = New RectangleF(100, 170, 20, 20)

'Adds the items to radio button group.

employeesRadioList.Items.Add(radioItem1)

employeesRadioList.Items.Add(radioItem2)

'Saves the PDF document.

document.Save("Form.pdf")

document.Close()

### Adding Signature field

A signature field is a form field that contains a digital signature. PdfSignatureField class is used to create signature fields in PDF forms. PdfSignature class enables you to sign the signature field with the given certificate.

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page to PDF document.

PdfPage page = document.Pages.Add();

//Creates PDF Signature field.

PdfSignatureField signatureField = new PdfSignatureField(page, "Signature");

//Creates PDF Certificate.

PdfCertificate certificate = new PdfCertificate(@"sample.pfx", "syncfusion");

//Sets properties to the signature field.

signatureField.BorderColor = new PdfColor(Color.Gray);

signatureField.BorderStyle = PdfBorderStyle.Beveled;

signatureField.Bounds = new RectangleF(0, 400, 90, 20);

signatureField.Signature = new PdfSignature();

signatureField.Signature.Certificate = certificate;

signatureField.Signature.Reason = "Reason";

signatureField.ToolTip = "Signature";

//Adds the form field to the document.

document.Form.Fields.Add(signatureField);

//Saves the document.

document.Save("Form.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds a new page to PDF document.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF Signature field.

Dim signatureField As New PdfSignatureField(page, "Signature")

'Creates PDF Certificate.

Dim certificate As New PdfCertificate("sample.pfx", "syncfusion")

'Sets properties to the signature field.

signatureField.BorderColor = New PdfColor(Color.Gray)

signatureField.BorderStyle = PdfBorderStyle.Beveled

signatureField.Bounds = New RectangleF(0, 400, 90, 20)

signatureField.Signature = New PdfSignature()

signatureField.Signature.Certificate = certificate

signatureField.Signature.Reason = "Reason"

signatureField.ToolTip = "Signature"

'Adds the form field to the document.

document.Form.Fields.Add(signatureField)

'Saves the PDF document.

document.Save("Form.pdf")

document.Close()

## Modify Form Field in a PDF Document

Essential PDF allows you to modify the form field of the existing document. You can retrieve the bounds and value of the field, change the field location and size, and modify its value. Also you can get or set the available property.

PdfLoadedForm class contains collection of loaded fields, represented by the PdfLoadedFormFieldCollection class, and inherited from the PdfFieldCollection class. When you need to modify an existing form field, get the particular field from the PdfLoadedFormFieldCollection and set its properties. After that, you need to save the updated PDF document.

The following loaded fields are supported in the library: 

* Button fields 
* Push button field represented by PdfLoadedButtonField class 
* Check Box field represented by PdfLoadedCheckBoxField class 
* Radio button field represented by PdfLoadedRadioButtonListField class 
* Text fields 
* Text field represented by PdfLoadedTextBoxField class 
* Choice fields 
* List Box field represented by PdfLoadedListBoxField class 
* Combo Box field represented by PdfLoadedComboBoxField class 
* Signature fields 
* Signature field represented by PdfLoadedSignatureField class 

You can access each field by using its index or field name. The following code example illustrates this.

[C#]



PdfLoadedTextBoxField field1 = form.Fields["fieldname"] as PdfLoadedTextBoxField;

PdfLoadedTextBoxField field2 = form.Fields[0] as PdfLoadedTextBoxField;



[VB]



Dim field1 As PdfLoadedTextBoxField = form.Fields("fieldname")

Dim field2 As PdfLoadedTextBoxField = form.Fields(0)



The following code example illustrates how to change the bounds and value of the field.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

//Gets the loaded form field.

PdfLoadedTextBoxField ldField = form.Fields[0] as PdfLoadedTextBoxField;

RectangleF newBounds = new RectangleF(100, 100, 50, 50);

//Modifies the properties.

ldField.Bounds = newBounds;

ldField.SpellCheck = true;

ldField.Text = "New text of the field.";

ldField.Password = false;

document.Save("sample.pdf");

document.Close();



[VB]

'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

'Gets the loaded form field.

Dim ldField As PdfLoadedTextBoxField = form.Fields(0)

Dim newBounds As New RectangleF(100, 100, 50, 50)

'Modifies the properties.

ldField.Bounds = newBounds

ldField.SpellCheck = True

ldField.Text = "New text of the field."

ldField.Password = False

document.Save("sample.pdf")

document.Close()

## Fill Form Field in a PDF Document

Essential PDF provides you support to fill AcroForm fields. You can fill the form field value by using its field name or field index.

### Filling the text box field

The following code illustrates how to fill the Text Box Field.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

//Gets the loaded Text box field.

PdfLoadedTextBoxField ldField = form.Fields[0] as PdfLoadedTextBoxField;

ldField.Text = "First Name";

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

'Gets the loaded Text box field.

Dim ldField As PdfLoadedTextBoxField = TryCast(form.Fields(0), PdfLoadedTextBoxField)

ldField.Text = "First Name"

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

### Formatting the text box

The following table lists some of the properties of the TextBoxField.

_Property Table_

<table>
<tr>
<td>
TextBoxField Property </td><td>
Description </td></tr>
<tr>
<td>
BackColor </td><td>
Gets or sets the back color of the field. </td></tr>
<tr>
<td>
BorderColor </td><td>
Gets or sets the border color of the field. </td></tr>
<tr>
<td>
BorderStyle </td><td>
Gets or sets the border style for the field. </td></tr>
<tr>
<td>
Border </td><td>
Gets or sets the width of the field border. </td></tr>
<tr>
<td>
ForeColor </td><td>
Gets or sets the fore color of the field. </td></tr>
<tr>
<td>
HighlightMode </td><td>
Gets or sets the highlight mode of the field. It includes the following options. * Invert * Outline * Push * NoHighlighting </td></tr>
<tr>
<td>
<br>TextAlignment </td><td>
Gets or sets the alignment of the text in the field. It includes the following options. * Center * Left * Right * Justify </td></tr>
</table>



[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded text box field.

PdfLoadedTextBoxField textBoxField = form.Fields[0] as PdfLoadedTextBoxField;

//Modifies the property.

textBoxField.BorderColor = Color.SteelBlue;

textBoxField.BorderStyle = PdfBorderStyle.Solid;

textBoxField.BorderWidth = 1;

textBoxField.BackColor = new PdfColor(Color.AliceBlue);

textBoxField.ForeColor = new PdfColor(Color.Navy);

textBoxField.HighlightMode = PdfHighlightMode.Invert;

textBoxField.TextAlignment = PdfTextAlignment.Right;

Font font = new Font("Arial", 18f);

PdfTrueTypeFont txtfnt = new PdfTrueTypeFont(font, false);

//Sets text box font.

textBoxField.Font = txtfnt;

textBoxField.Text = "first Name";

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded text box field.

Dim textBoxField As PdfLoadedTextBoxField = TryCast(Form.Fields(0), PdfLoadedTextBoxField)

'Modifies the property.

textBoxField.BorderColor = Color.SteelBlue

textBoxField.BorderStyle = PdfBorderStyle.Solid

textBoxField.BorderWidth = 1

textBoxField.BackColor = New PdfColor(Color.AliceBlue)

textBoxField.ForeColor = New PdfColor(Color.Navy)

textBoxField.HighlightMode = PdfHighlightMode.Invert

textBoxField.TextAlignment = PdfTextAlignment.Right

Dim font As New Font("Arial", 18.0F)

Dim txtfnt As New PdfTrueTypeFont(font, False)

'Sets text box font.

textBoxField.Font = txtfnt

textBoxField.Text = "first Name"

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

### Filling the combo box field

The following code illustrates how to fill the Combo Box Field.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

//Gets the loaded combo box field.

PdfLoadedComboBoxField combo = form.Fields[1] as PdfLoadedComboBoxField;

combo.SelectedIndex = 1;

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

'Gets the loaded combo box field.

Dim combo As PdfLoadedComboBoxField = TryCast(form.Fields(1), PdfLoadedComboBoxField)

combo.SelectedIndex = 1

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

### Filling the Radio button field

The following code illustrates how to fill the Radio Button Field.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

//Gets the loaded radio button field.

PdfLoadedRadioButtonListField radio = form.Fields[3] as PdfLoadedRadioButtonListField;

radio.SelectedIndex = 1;

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]

'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

'Gets the loaded radio button field.

Dim radio As PdfLoadedRadioButtonListField = TryCast(form.Fields(3), PdfLoadedRadioButtonListField)

radio.SelectedIndex = 1

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

### Filling list box field

The following code illustrates how to fill the List Box Field.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

//Fills list box.

PdfLoadedListBoxField list = form.Fields[2] as PdfLoadedListBoxField;

list.SelectedIndex = new int[2] { 1, 2 };

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

'Fills list box.

Dim list As PdfLoadedListBoxField = TryCast(form.Fields(2), PdfLoadedListBoxField)

list.SelectedIndex = New Integer(1) {1, 2}

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

### Filling the check Box field

The following code illustrates how to fill the Check Box Field.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

//Fills check box.

PdfLoadedCheckBoxField checkBox = form.Fields[1] as PdfLoadedCheckBoxField;

//Checks the first item in the checkbox group.

checkBox.Items[0].Checked = true;

//Checks the checkbox if it is not grouped.

checkBox.Checked = true;

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

'Fills check box.

Dim checkBox As PdfLoadedCheckBoxField = TryCast(form.Fields(1), PdfLoadedCheckBoxField)

'Checks the first item in the checkbox group.

checkBox.Items(0).Checked = True

'Checks the checkbox if it is not grouped.

checkBox.Checked = True

'Saves the modified document.

document.Save("sample.pdf")

document.Close()



### Filling the signature field

The following code illustrates how to fill the Signature Field

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

//Creates PDF Certificate.

PdfCertificate certificate = new PdfCertificate(@"sample.pfx", "syncfusion");

//Fills PDF signature field.

PdfLoadedSignatureField sigField = form.Fields[0] as PdfLoadedSignatureField;

sigField.Signature = new PdfSignature();

sigField.Signature.Certificate = certificate;

sigField.Signature.Reason = "Reason";

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

'Creates PDF Certificate.

Dim certificate As New PdfCertificate("sample.pfx", "syncfusion")

'Fills PDF signature field.

Dim sigField As PdfLoadedSignatureField = TryCast(form.Fields(0), PdfLoadedSignatureField)

sigField.Signature = New PdfSignature()

sigField.Signature.Certificate = certificate

sigField.Signature.Reason = "Reason"

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

### Enumerate the form fields

You can also enumerate the fields and fill them. The following code example illustrates how to enumerate the text fields.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

PdfLoadedFormFieldCollection fields = form.Fields;

//Enumerates the form fields.

for (int i = 0; i < fields.Count; i++)

{

if (fields[i] is PdfLoadedTextBoxField)

{

PdfLoadedTextBoxField textBox = fields[i] as PdfLoadedTextBoxField;

textBox.Text = "Text";

}

}

//Saves the modified document.

document.Save("sample.pdf");

document.Close();



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

Dim fields As PdfLoadedFormFieldCollection = form.Fields

'Enumerates the form fields.

For i As Integer = 0 To fields.Count - 1

If TypeOf fields(i) Is PdfLoadedTextBoxField Then

Dim textBox As PdfLoadedTextBoxField = TryCast(fields(i), PdfLoadedTextBoxField)

textBox.Text = "Text"

End If

Next i

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

## Flatten Form Fields

You can flatten the loaded field by using the Flatten property of the PdfLoadedField class. A particular field or the whole form can be flattened using this class. While flattening a form field, Essential PDF removes the form field from the document and replaces it with graphical elements that picturizes the form field.

The following code example illustrates this.

[C#]



//Loads the PDF document.

PdfLoadedDocument document = new PdfLoadedDocument(fileName);

//Gets the loaded form.

PdfLoadedForm form = document.Form;

PdfLoadedFormFieldCollection fields = form.Fields;

PdfLoadedTextBoxField textBox = fields[0] as PdfLoadedTextBoxField;

textBox.Text = "Text";

//Flattens the whole form.

form.Flatten = true;

//Saves the modified document.

document.Save("sample.pdf");

document.Close();

//Flattens the first field.

form.Fields[0].Flatten = true;



[VB]



'Loads the PDF document.

Dim document As New PdfLoadedDocument(fileName)

'Gets the loaded form.

Dim form As PdfLoadedForm = document.Form

Dim fields As PdfLoadedFormFieldCollection = form.Fields

Dim textBox As PdfLoadedTextBoxField = TryCast(fields(0), PdfLoadedTextBoxField)

textBox.Text = "Text"

'Flattens the whole form.

form.Flatten = True

'Saves the modified document.

document.Save("sample.pdf")

document.Close()

'Flattens the first field.

form.Fields(0).Flatten = True

## Adding Actions to Form Fields 

Instead of simply jumping to a destination in the document, an annotation or outline item can specify the action for the viewer application to perform, such as launching an application, playing a sound, or changing an annotation appearance. Essential PDF provides you support to add the various actions to form fields.

The following code example illustrates this. 

[C#]



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds page to document.

PdfPage page = document.Pages.Add();

// Creates a Text box field.

PdfTextBoxField textBoxField = new PdfTextBoxField(page, "FirstName");

//Sets properties to the textbox.

textBoxField.BorderColor = new PdfColor(Color.Gray);

textBoxField.BorderStyle = PdfBorderStyle.Beveled;

textBoxField.Bounds = new RectangleF(0, 0, 100, 20);

textBoxField.ToolTip = "First Name";

//Adds the form field to the document.

document.Form.Fields.Add(textBoxField);

//Adds JavaScript action to the field.

PdfJavaScriptAction javaAction= new PdfJavaScriptAction("app.alert(\"You are looking at Java script action of PDF (PdfTextBoxField)\")");

textBoxField.Actions.LostFocus = javaAction;

//Creates a Button field.

PdfButtonField submitButton = new PdfButtonField(page, "Navigate to next Page");

submitButton.Bounds = new RectangleF(100,100,50,50);

submitButton.ToolTip = "Navigate";

document.Form.Fields.Add(submitButton);

//Adds a new page.

page = document.Pages.Add();

//Creates an instance of PdfDestination.

PdfDestination dest = new PdfDestination(page, new Point(0, 100));

//Creates an instance of GoTo action.

PdfGoToAction goToAction = new PdfGoToAction(page);

//Updates the destination for the action.

goToAction.Destination = dest;

//Sets action for the field.

submitButton.Actions.GotFocus = goToAction;

//Saves the PDF file

document.Save("sample.pdf");

document.Close();



[VB]



'Creates a new PDF document.

Dim document As New PdfDocument()

'Adds page to document.

Dim page As PdfPage = document.Pages.Add()

'Creates a Text box field.

Dim textBoxField As New PdfTextBoxField(page, "FirstName")

'Sets properties to the textbox.

textBoxField.BorderColor = New PdfColor(Color.Gray)

textBoxField.BorderStyle = PdfBorderStyle.Beveled

textBoxField.Bounds = New RectangleF(0, 0, 100, 20)

textBoxField.ToolTip = "First Name"

'Adds the form field to the document.

document.Form.Fields.Add(textBoxField)

'Adds JavaScript action to the field.

Dim javaAction As New PdfJavaScriptAction("app.alert(""You are looking at Java script action of PDF (PdfTextBoxField)"")")

textBoxField.Actions.LostFocus = javaAction

'Creates a Button field.

Dim submitButton As New PdfButtonField(page, "Navigate to next Page")

submitButton.Bounds = New RectangleF(100, 100, 50, 50)

submitButton.ToolTip = "Navigate"

document.Form.Fields.Add(submitButton)

'Adds a new page.

page = document.Pages.Add()

'Creates an instance of PdfDestination.

Dim dest As New PdfDestination(page, New Point(0, 100))

'Creates an instance of GoTo action.

Dim goToAction As New PdfGoToAction(page)

'Updates the destination for the action.

goToAction.Destination = dest

'Sets action for the field.

submitButton.Actions.GotFocus = goToAction

'Saves the PDF file.

document.Save("sample.pdf")

document.Close()



