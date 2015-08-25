---
layout: post
title: Table
description: table
platform: wpf
control: PDF
documentation: ug
---

# Table

Tables are useful for presenting a large quantity of information clearly and concisely. In PDF, tables are drawn as a series of rectangles with text and image correctly positioned within them. Essential PDF also offers two types of table models. They are:

* PdfLightTable
* PdfGrid
## Light Table


Light table allows you to create a table with inputs from DataTable, arrays, or any other entity class. It allows you to perform simple formatting using events.  As this class allows minimal customization options, rendering is faster than PDF Grid and is recommended to draw a simple table. 

### Properties, Methods and Events

#### Properties

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
AllowRowBreakAcrossPages</td><td>
Setting this property to true enables breaking table across the pages of the PDF document.</td><td>
Boolean</td></tr>
<tr>
<td>
Columns</td><td>
Acquires the columns from the light table.</td><td>
PdfColumnCollection</td></tr>
<tr>
<td>
DataMember</td><td>
Gets or sets the value to the light table DataMember.</td><td>
String</td></tr>
<tr>
<td>
DataSource</td><td>
Gets or sets the DataSource to the light table.</td><td>
Object</td></tr>
<tr>
<td>
DataSourceType</td><td>
Gets or sets the type of data source assigned to the PdfLightTable.</td><td>
PdfLightTableDataSourceType (enum)</td></tr>
<tr>
<td>
IgnoreSorting</td><td>
Gets or sets a value indicating whether PdfLightTable should ignore sorting in the DataTable or not.</td><td>
Boolean</td></tr>
<tr>
<td>
Rows</td><td>
Acquires the rows of the light table.</td><td>
PdfRowCollection</td></tr>
<tr>
<td>
Style</td><td>
Gets or sets the style of the light table.</td><td>
PdfLightTableStyle</td></tr>
</table>

#### Methods

Methods Table

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th></tr>
<tr>
<td rowspan = "17">
Draw</td><td rowspan = "17">
Draws PdfLightTable into the PDF document</td><td>
Overloads:Draw(PdfGraphics graphics)</td><td>
Void</td></tr>
<tr>
<td>
Draw (PdfPage page, PointF location)</td><td>
PdfLightTableLayoutResult</td></tr>
<tr>
<td>
Draw (PdfPage page, RectangleF bounds)</td><td>
PdfLightTableLayoutResult</td></tr>
<tr>
<td>
Draw (PdfGraphics graphics, PointF location)</th><th>
Void</td></tr>
<tr>
<td>
Draw (PdfGraphics graphics, RectangleF bounds)</td><td>
Void</td></tr>
<tr>
<td>
Draw (PdfPage page, float x, float y)</td><td>
PdfLightTableLayoutResult</td></tr>
<tr>
<td>
Draw (PdfPage page, PointF location, PdfLightTableLayoutFormat format)</td><td>
PdfLightTableLayoutResult</td></tr>
<tr>
<td>
Draw (PdfPage page, PointF location, PdfLayoutFormat format)</td><td>
PdfLayoutResult</td></tr>
<tr>
<td>
Draw (PdfPage page, RectangleF bounds, PdfLightTableLayoutFormat format)</td><td>
PdfLightTableLayoutResult</td></tr>
<tr>
<td>
Draw (PdfPage page, PointF location, PdfLayoutFormat format)</td><td>
PdfLayoutResult</td></tr>
<tr>
<td>
Draw (PdfGraphics graphics, float x, float y)</td><td>
void</td></tr>
<tr>
<td>
Draw (PdfGraphics graphics, PointF location, float width)</td><td>
void</td></tr>
<tr>
<td>
Draw (PdfPage page, float x, float y, float width)</td><td>
PdfLightTableLayoutResult</td></tr>
<tr>
<td>
Draw PdfPage page, float x, float y, PdfLightTableLayoutFormat format)</td><td>
PdfLightTableLayoutResult</td></tr>
<tr>
<td>
Draw (PdfPage page, float x, float y, PdfLayoutFormat format)</td><td>
PdfLayoutResult</td></tr>
<tr>
<td>
Draw (PdfGraphics graphics, float x, float y, float width)</td><td>
void</td></tr>
<tr>
<t>
Draw (PdfPage page, float x, float y, float width, PdfLightTableLayoutFormat format)</td><td>
PdfLightTableLayoutResult</td></tr>
</table>

#### Events

Events Table

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
BeginCellLayout</td><td>
This event is raised before starting the cell layout.</td></tr>
<tr>
<td>
BeginPageLayout</td><td>
This event is raised before the element is rendered on the page.(Inherited from PdfLayoutElement.)</td></tr>
<tr>
<td>
BeginRowLayout</td><td>
This event is raised before starting the row layout.</td></tr>
<tr>
<td>
EndCellLayout</td><td>
This event is raised after the completion of cell layout.</td></tr>
<tr>
<td>
EndPageLayout</td><td>
This event is raised after the element is rendered on the page.(Inherited from PdfLayoutElement.)</td></tr>
<tr>
<td>
EndRowLayout</td><td>
This event is raised after the completion of row layout.</td></tr>
<tr>
<td>
QueryColumnCount</td><td>
This event is raised when the column number is requested.</td></tr>
<tr>
<td>
QueryNextRow</td><td>
This event is raised when the next row data is requested.</td></tr>
<tr>
<td>
QueryRowCount</td><td>
This event is raised when the row number is requested.</td></tr>
</table>

### Creating a light table

PdfLightTable is a table consisting of rows and columns that can be filled with data and rendered into the Page of the PDF Document. You can create a PdfLightTable with the following code sample.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics

PdfGraphics graphics = page.Graphics;

// Creates a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

// Initializes DataTable to assign as DateSource to the light table.

DataTable table = new DataTable();

//Includes columns to the DataTable.

table.Columns.Add("Name");

table.Columns.Add("Age");

table.Columns.Add("Sex");

//Includes rows to the DataTable.

table.Rows.Add(new string[] { "abc", "21", "Male" });

//Assigns data source.

pdfLightTable.DataSource = table;

//Includes the style to display the header of the light table.

pdfLightTable.Style.ShowHeader = true;

//Draws PdfLightTable.

pdfLightTable.Draw(graphics);            

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Creates a PdfLightTable.

Dim pdfLightTable As New PdfLightTable()

'Initializes DataTable to assign as DateSource to the light table.

Dim table As New DataTable()

'Includes columns to the DataTable.

table.Columns.Add("Name")

table.Columns.Add("Age")

table.Columns.Add("Sex")

'Includes rows to the DataTable.

table.Rows.Add(New String() {"abc", "21", "Male"})

'Assigns data source.

pdfLightTable.DataSource = table

'Includes the style to display the header of the light table.

pdfLightTable.Style.ShowHeader = True

'Draws PdfLightTable.

pdfLightTable.Draw(graphics)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

#### Assigning DataSource to PdfLightTable

Data to the PdfLightTable is assigned using DataSource property. This is achieved through:

* External DataSource: By assigning the External data source
* Table Direct : By adding columns and rows to the PdfLightTable
* Event Handlers : By adding columns and rows by using the event handlers

##### External DataSource


Data source is an object that can be an array (two-dimensional, one-dimensional or nested), a DataTable, DataColumn, DataView, or a DataSet. To draw an external data source, you need to set DataSourceType property to PdfLightTableDataSourceType.External.

The following code example illustrates how to assign external data source to PdfLightTable:

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Creates a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Initializes DataTable to assign as DateSource to the light table.

DataTable table = new DataTable();

//Includes columns to the DataTable.

table.Columns.Add("Name");

table.Columns.Add("Age");

table.Columns.Add("Sex");

//Includes rows to the DataTable.

table.Rows.Add(new string[] { "abc", "21", "Male" });

//Sets DataSourceType to the light table.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.External;

//Assigns data source.

pdfLightTable.DataSource = table;

//Includes the style to display the header of the light table.

pdfLightTable.Style.ShowHeader = true;

// Draws PdfLightTable.

pdfLightTable.Draw(graphics);            

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Creates a PdfLightTable.

Dim pdfLightTable As New PdfLightTable()

'Initializes DataTable to assign as DateSource to the light table.

Dim table As New DataTable()

'Includes columns to the DataTable.

table.Columns.Add("Name")

table.Columns.Add("Age")

table.Columns.Add("Sex")

'Includes rows to the DataTable.

table.Rows.Add(New String() {"abc", "21", "Male"})

'Sets DataSourceType to the light table.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.External

'Assigns data source.

pdfLightTable.DataSource = table

'Includes the style to display the header of the light table.

pdfLightTable.Style.ShowHeader = True

'Draws PdfLightTable.

pdfLightTable.Draw(graphics)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

##### Table Direct

You can directly add rows and columns to PdfLightTable. To achieve this, set DataSourceType property to PdfLightTableDataSourceType .TableDirect. The following code example illustrates this:

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);          

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Declares PdfLightTable.

Dim pdfLightTable As PdfLightTable = New PdfLightTable()

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates Columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds Rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

##### Event Handler

Data to PdfLightTable can also be set using the following three events:

* QueryColumnCount – Sets the number of columns.
* QueryRowCount – Sets the number of rows.
* QueryNextRow – Sets data to the PdfLightTable.



N> These events acts only when the DataSource property is not set.

The following code sample illustrates this:

{% highlight c# %}



static string[][] datastring = new string[2][];

static void Main(string[] args)

{

//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

// Gives it some column arrays.

datastring[0] = new string[] { "111", "Maxim", "100" };

datastring[1] = new string[] { "222", "Calvin", "95" };

//Creates PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

pdfLightTable.QueryColumnCount += new QueryColumnCountEventHandler(pdfLightTable_QueryColumnCount);

pdfLightTable.QueryNextRow += new QueryNextRowEventHandler(pdfLightTable_QueryNextRow);

pdfLightTable.QueryRowCount += new QueryRowCountEventHandler(pdfLightTable_QueryRowCount);

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

}

//Gets the number of columns.

static void pdfLightTable_QueryColumnCount(object sender, QueryColumnCountEventArgs args)

{

args.ColumnCount = 3;

}

//Gets the number of rows.

static void pdfLightTable_QueryRowCount(object sender, QueryRowCountEventArgs args)

{

args.RowCount = 2;

}

//Gets the row data.

static void pdfLightTable_QueryNextRow(object sender, QueryNextRowEventArgs args)

{

if (args.RowIndex < datastring.Length)

args.RowData = new string[] { datastring[args.RowIndex][0], datastring[args.RowIndex][1], datastring[args.RowIndex][2] };

}
{% endhighlight %}


{% highlight vbnet %}



Shared datastring As String()() = New String(1)() {}

    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load

        'Creates a new PDF document.

        Dim doc As New PdfDocument()

        'Adds a page.

        Dim page As PdfPage = doc.Pages.Add()

        ' Gives it some column arrays.

        datastring(0) = New String() {"111", "Maxim", "100"}

        datastring(1) = New String() {"222", "Calvin", "95"}

        'Creates PdfLightTable.

        Dim pdfLightTable As New PdfLightTable()

        AddHandler pdfLightTable.QueryColumnCount, AddressOf pdfLightTable_QueryColumnCount

        AddHandler pdfLightTable.QueryNextRow, AddressOf pdfLightTable_QueryNextRow

        AddHandler pdfLightTable.QueryRowCount, AddressOf pdfLightTable_QueryRowCount



        'Draws the PdfLightTable.

        pdfLightTable.Draw(page, PointF.Empty)

        'Saves the document.

        doc.Save("Output.pdf")

        doc.Close(True)

    End Sub



    'Gets the number of columns.

    Private Sub pdfLightTable_QueryColumnCount(sender As Object, args As QueryColumnCountEventArgs)

        args.ColumnCount = 3

    End Sub

    'Gets the number of rows.

    Private Sub pdfLightTable_QueryRowCount(sender As Object, args As QueryRowCountEventArgs)

        args.RowCount = 2

    End Sub

    'Gets the row data.

    Private Sub pdfLightTable_QueryNextRow(sender As Object, args As QueryNextRowEventArgs)

        If args.RowIndex < datastring.Length Then

            args.RowData = New String() {datastring(args.RowIndex)(0), datastring(args.RowIndex)(1), datastring(args.RowIndex)(2)}

        End If

    End Sub
{% endhighlight %}

### Formatting a light table

The PDF light table contains the most direct and indirect (through events) formatting options. The PdfLightTableStyle class, accessed through Style property of PdfLightTable instance contains a number of properties that allows formatting of the entire PdfLightTable or parts of it. Border and few other properties are discussed as follows.

#### Border

Border of the light table can be customized with two different properties available in the Style of the PdfLightTable. They are

* BorderPen
* BorderOverlapStyle

Customizing BorderPen

BorderPen allows you to customize the color of the table border, it is of type PdfPen. The following code sample allows you to customize the border color of the light table.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Customizes the color of the table broder.

pdfLightTable.Style.BorderPen = new PdfPen(Color.Red);

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Declares a PdfLightTable.

Dim pdfLightTable As PdfLightTable = New PdfLightTable()

'Customizes the color of the table broder.

pdfLightTable.Style.BorderPen = New PdfPen(Color.Red)

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)

{% endhighlight %}

Customizing BorderOverlapStyle

BorderOverlapStyle decides whether the cell border overlaps the neighboring cells or if it should be drawn inside the cell.

N> This property applies for all cells in the PdfLightTable. You need to be careful when using overlapping borders, because they can produce bad results if they are not the same width and color.

The following code sample allows you to customize the BoderOverlapStyle of the light table.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Customizes BorderOverlapStyle of the table broder.

pdfLightTable.Style.BorderOverlapStyle = PdfBorderOverlapStyle.Overlap;

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Declares a PdfLightTable.

Dim pdfLightTable As PdfLightTable = New PdfLightTable()

'Customizes BorderOverlapStyle of the table broder.

pdfLightTable.Style.BorderOverlapStyle = PdfBorderOverlapStyle.Overlap

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})        

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

#### Padding and Spacing

Customization of the Cell padding and Cell spacing are also possible with access to the properties CellPadding and CellSpacing available in the Style of the light table.

The following code illustrates the customization of the cell padding and spacing in the light table.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Customizes cell padding and spacing.

pdfLightTable.Style.CellPadding = 4;

pdfLightTable.Style.CellSpacing = 10;

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics

Dim graphics As PdfGraphics = page.Graphics

'Declares a PdfLightTable.

Dim pdfLightTable As PdfLightTable = New PdfLightTable()

'Customizes cell padding and spacing.

pdfLightTable.Style.CellPadding = 4

pdfLightTable.Style.CellSpacing = 10

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

#### Header

Header is a set of rows that repeat on each page and has its own style. Rows for the header can be taken from column captions or from ordinary rows. In the latter case, the rows are treated as headers and do not appear in the body of the PdfLightTable.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Header from column captions.

pdfLightTable.Style.ShowHeader = true;

pdfLightTable.Style.HeaderSource = PdfHeaderSource.ColumnCaptions;

pdfLightTable.Style.RepeatHeader = true;

pdfLightTable.Style.HeaderStyle = new PdfCellStyle(new PdfStandardFont(PdfFontFamily.Helvetica, 14), new PdfSolidBrush(Color.Gray), new PdfPen(Color.Black));

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Declares a PdfLightTable.

Dim pdfLightTable As PdfLightTable = New PdfLightTable()

'Header from column captions.

pdfLightTable.Style.ShowHeader = true;

pdfLightTable.Style.HeaderSource = PdfHeaderSource.ColumnCaptions;

pdfLightTable.Style.RepeatHeader = true;

pdfLightTable.Style.HeaderStyle = new PdfCellStyle(new PdfStandardFont(PdfFontFamily.Helvetica, 14), new PdfSolidBrush(Color.Gray), new PdfPen(Color.Black));

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates Columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds Rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

#### Row

You can access and edit the rows of the light table using the Rows property. The values of existing row, entered with DataSourceType as PdfLightTableDataSourceType.TableDirect can be edited using the Values property. Following is the code that alters the content.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

//Edits the value of the 1st row.

pdfLightTable.Rows[0].Values = new string[] { "333", "John", "II" };

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Declares a PdfLightTable.

Dim pdfLightTable As PdfLightTable = New PdfLightTable()

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

'Edits the value of the 1st row.

pdfLightTable.Rows[0].Values = new string[] { "333", "John", "II" };

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

#### Column

Properties in the column

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
ColumnName</td><td>
Gets or sets the column name.</td><td>
String</td></tr>
<tr>
<td>
StringFormat</td><td>
Gets of sets the string format for the column.</td><td>
PdfStringFormat</td></tr>
<tr>
<td>
Width</td><td>
Gets of sets the width of the column.</td><td>
float</td></tr>
</table>

ColumnName

By default, PdfLightTable displays the column text as the DataSource column name. You can change the column text with the help of the ColumnName property. The following code sample illustrates the same:

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Acquires page's graphics.

PdfGraphics graphics = page.Graphics;

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));  

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

// Specifies column name.

pdfLightTable.Columns[1].ColumnName = "Student Name";

//Styles to display header.

pdfLightTable.Style.ShowHeader = true;

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Acquires page's graphics.

Dim graphics As PdfGraphics = page.Graphics

'Declares a PdfLightTable.

Dim pdfLightTable As New PdfLightTable()

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

'Specifies column name.

pdfLightTable.Columns(1).ColumnName = "Student Name"

'Styles to display header.

pdfLightTable.Style.ShowHeader = True

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)

{% endhighlight %}

StringFormat

You can change the format of the data for a single column using the StringFormat property. Check String Formatting in DrawingText for more details.

Width

By default, all the columns in a PdfLightTable have equal width, and the columns automatically fill the entire width of the PdfLightTable. When the width of the column(s) is increased or decreased, the width of other columns changes appropriately.

To customize the column width, you can use the Width property for each column of the PdfLightTable. The following code sample illustrates the same.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adding rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

//Sets width for third column.

pdfLightTable.Columns[1].Width = 5;

//Styles to display header.

pdfLightTable.Style.ShowHeader = true;

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Declares a PdfLightTable.

Dim pdfLightTable As New PdfLightTable()

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

'Sets width for third column.

pdfLightTable.Columns(1).Width = 5

'Styles to display header.

pdfLightTable.Style.ShowHeader = True

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)

{% endhighlight %}

N> The unit of the Width property is always in points, and PDF units can be set only as points.  You can also use the PdfUnitConvertor class to convert the other units to points.

#### Cell

You can specify the default cell style by using the DefaultStyle property. You can set the style for the header cell using the HeaderStyle property.  An alternate style can also be specified using the AlternateStyle property. This property is used to customize the appearance of the cells in the odd row.

Properties of a cell
_Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
BackgroundBrush</td><td>
Gets or sets the brush with which the background of the cell is drawn.</td><td>
PdfBrush</td></tr>
<tr>
<td>
Border</td><td>
Gets or sets the pen with which the border of the cell is drawn.</td><td>
PdfPen</td></tr>
<tr>
<td>
Font</td><td>
Gets or sets the font with which the text content of the cell is drawn.</td><td>
PdfFont</td></tr>
<tr>
<td>
StringFormat</td><td>
Gets or sets the string format of the text.</td><td>
PdfStringFormat</td></tr>
<tr>
<td>
TextBrush</td><td>
Gets or sets the brush with which the text is rendered.</td><td>
PdfBrush</td></tr>
<tr>
<td>
TextPen</td><td>
Gets or sets the pen, which will be used to draw text outlines.</td><td>
PdfPen</td></tr>
</table>


The Style property enables you to customize the font along with its appearance (brush, pen and string format), and border along with the background of cells. Although there are fixed properties for styles, you can specify different styles using BeginCellLayout and EndCellLayout events.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds Rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

pdfLightTable.Rows.Add(new object[] { "112", "Minim", "III" });

//Creates the font for setting the style.

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 14);

//Declares and defines the alternate style.

PdfCellStyle altStyle = new PdfCellStyle(font, PdfBrushes.White, PdfPens.Green);

altStyle.BackgroundBrush = PdfBrushes.DarkGray;

//Declares and defines the header style.

PdfCellStyle headerStyle = new PdfCellStyle(font, PdfBrushes.White, PdfPens.Brown);

headerStyle.BackgroundBrush = PdfBrushes.Red;

pdfLightTable.Style.AlternateStyle = altStyle;

pdfLightTable.Style.HeaderStyle = headerStyle;

//Styles to display header.

pdfLightTable.Style.ShowHeader = true;

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Declares a PdfLightTable.

Dim pdfLightTable As New PdfLightTable()

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

pdfLightTable.Rows.Add(New Object() {"112", "Minim", "III"})

'Creates the font for setting the style.

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, 14)

'Declares and defines the alternate style.

Dim altStyle As New PdfCellStyle(font, PdfBrushes.White, PdfPens.Green)

altStyle.BackgroundBrush = PdfBrushes.DarkGray

'Declares and defines the header style.

Dim headerStyle As New PdfCellStyle(font, PdfBrushes.White, PdfPens.Brown)

headerStyle.BackgroundBrush = PdfBrushes.Red

pdfLightTable.Style.AlternateStyle = altStyle

pdfLightTable.Style.HeaderStyle = headerStyle

'Styles to display header.

pdfLightTable.Style.ShowHeader = True

'Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}

### Customization a light table

PdfLightTable offers a set of events that helps in changing the look and feel of the PDF. The following are the list of events.

* BeginPageLayout
* EndPageLayout
* BeginRowLayout
* EndRowLayout
* BeginCellLayout
* EndCellLayout



#### BeginPageLayout

This event is raised before beginning the page layout. The arguments of this event are as follows.

* Page (read-only): Page on which layout should be performed.
* Bounds: Size of the PdfLightTable part that should be laid out on the page.
* Cancel: Enables to cancel layout.

EndPageLayhis event is raised when layout on a page is finished. The arguments of this event are as follows:

* Result (read-only): Layout result for the current page
* NextPage: Page on which layout should continue
#### BeginRowLayout


This event is raised before beginning the row layout of the light table. The arguments of this event are as follows:

* RowIndex (read-only): Index of the row (zero based)
* CellStyle : Style of the cells within the row.
* ColumnSpanMap : Array of integers specifying column span.
* Cancel: Enables to cancel layout.
* IgnoreColumnFormat: Gets or sets a value indicating whether column string format should be ignored.
* Skip: Enables to skip the entire row.
* MinimalHeight: Enables to specify the minimal row height, which is used to preserve space for images.

The following code example illustrates how to set the row height using BeginRowLayout event:

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Declares a PdfLightTable.

PdfLightTable pdfLightTable = new PdfLightTable();

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

 pdfLightTable.Rows.Add(new object[] { "112", "Minim", "III" });

pdfLightTable.BeginRowLayout += pdfLightTable_BeginRowLayout;

//Styles to display header.

pdfLightTable.Style.ShowHeader = true;

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);



void pdfLightTable_BeginRowLayout(object sender, BeginRowLayoutEventArgs args)

{

if (args.RowIndex == 0)

{

args.MinimalHeight = 25;

}

}
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Declares PdfLightTable.

Dim pdfLightTable As New PdfLightTable()

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

pdfLightTable.Rows.Add(New Object() {"112", "Minim", "III"})

AddHandler pdfLightTable.BeginRowLayout, AddressOf pdfLightTable_BeginRowLayout

'Styles to display header.

pdfLightTable.Style.ShowHeader = True

'Draws PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)

Private Sub pdfLightTable_BeginRowLayout(sender As Object, args As BeginRowLayoutEventArgs)

If args.RowIndex = 0 Then

args.MinimalHeight = 25

End If

End Sub
{% endhighlight %}

#### EndRowLayout

This event is raised when row layout is finished. The arguments of this event are as follows:

* RowIndex (read-only): Index of the row (zero based),
* Cancel: Enables to cancel layout.
* LayoutCompleted (read-only):  Gets a value indicating whether the row was drawn completely.
* Bounds (read-only): Bounds of the row on the page.
#### BeginCellLayout


This event is raised when cell layout starts. The arguments of this event are as follows:

* RowIndex (read-only): Index of the current row
* CellIndex (read-only): Index of the current cell within the row
* Value (read-only): Text value of the cell
* Bounds (read-only): Bounds of the cell
* Graphics : Graphics on which the cell should be drawn
* Skip: Indicates if the cell should be skipped

The following code example illustrates how to draw the graphics elements inside the cell.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Declares a PdfLightTable

PdfLightTable pdfLightTable = new PdfLightTable();

//Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect;

//Creates columns.

pdfLightTable.Columns.Add(new PdfColumn("Roll Number"));

pdfLightTable.Columns.Add(new PdfColumn("Name"));

pdfLightTable.Columns.Add(new PdfColumn("Class"));

//Adds rows.

pdfLightTable.Rows.Add(new object[] { "111", "Maxim", "III" });

pdfLightTable.Rows.Add(new object[] { "112", "Minim", "III" });

pdfLightTable.BeginCellLayout += pdfLightTable_BeginCellLayout;

//Styles to display header.

pdfLightTable.Style.ShowHeader = true;

//Draws the PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty);

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);



void pdfLightTable_BeginCellLayout(object sender, BeginCellLayoutEventArgs args)

{

if (args.RowIndex == 0 && args.CellIndex == 1)

{

args.Graphics.DrawEllipse(PdfBrushes.Red, args.Bounds);

}

}

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Declares a PdfLightTable.

Dim pdfLightTable As New PdfLightTable()

'Sets the DataSourceType as Direct.

pdfLightTable.DataSourceType = PdfLightTableDataSourceType.TableDirect

'Creates columns.

pdfLightTable.Columns.Add(New PdfColumn("Roll Number"))

pdfLightTable.Columns.Add(New PdfColumn("Name"))

pdfLightTable.Columns.Add(New PdfColumn("Class"))

'Adds rows.

pdfLightTable.Rows.Add(New Object() {"111", "Maxim", "III"})

pdfLightTable.Rows.Add(New Object() {"112", "Minim", "III"})

AddHandler pdfLightTable.BeginCellLayout, AddressOf pdfLightTable_BeginCellLayout

'Styles to display header.

pdfLightTable.Style.ShowHeader = True

'Draws PdfLightTable.

pdfLightTable.Draw(page, PointF.Empty)

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)



Private Sub pdfLightTable_BeginCellLayout(sender As Object, args As BeginCellLayoutEventArgs)

        If args.RowIndex = 0 AndAlso args.CellIndex = 1 Then

            args.Graphics.DrawEllipse(PdfBrushes.Red, args.Bounds)

        End If

    End Sub
{% endhighlight %}

#### EndCellLayout

This event is raised when cell layout finishes. The arguments of this event are as follows:

* RowIndex (read-only): Index of the current row.
* CellIndex (read-only): Index of the current cell within the row.
* Value (read-only): Text value of the cell.
* Bounds (read-only): Bounds of the cell.
* Graphics: Graphics on which the cell should be drawn.
## Grid


Grid is based on cell model that offers rich API for formatting and layout options API for formatting and layout options. It can take input from DataTable, arrays, or any other entity class. Formatting can be done at all levels of PdfGrid. More features like Nested Grids, Row, and Column Spanning are also supported. It offers full control over the appearance and is recommended to draw complex table structures. 

### Properties, Methods and Events

Properties

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
AllowRowBreakAcrossPages</td><td>
Gets or sets whether to split or move rows that overflow a page. By default, this Boolean property is set to True that allows splitting the row across pages when the row cannot accommodate within the bounds of the page. If set to false, the entire row is shifted to the next page.</td><td>
Boolean</td></tr>
<tr>
<td>
Columns</td><td>
Gets access to the columns.</td><td>
PdfGridColumnCollection</td></tr>
<tr>
<td>
DataMember</td><td>
Gets or sets the data member.</td><td>
String</td></tr>
<tr>
<td>
DataSource</td><td>
Gets or sets the data source.</td><td>
Object</td></tr>
<tr>
<td>
Headers</td><td>
Gets the headers.</td><td>
PdfGridHeaderCollection</td></tr>
<tr>
<td>
RepeatHeader</td><td>
Gets or sets a value indicating whether to repeat header.</td><td>
Boolean</td></tr>
<tr>
<td>
Rows</td><td>
Gets access to the rows.</td><td>
PdfGridRowCollection</td></tr>
<tr>
<td>
Style</td><td>
Gets or sets the style.</td><td>
PdfGridStyle</td></tr>
</table>
Methods

Methods Table

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th></tr>
<tr>
<td rowspan = "17">
Draw</td><td rowspan = "17">
Draws PdfGrid</td><td>
Overloads:(PdfGraphics graphics)</td><td>
Void</td></tr>
<tr>
<td>
(PdfPage page, PointF location)</td><td>
PdfGridLayoutResult</td></tr>
<tr>
<td>
(PdfPage page, RectangleF bounds)</td><td>
PdfGridLayoutResult</td></tr>
<tr>
<td>
(PdfGraphics graphics, PointF location)</td><td>
Void</td></tr>
<tr>
<td>
(PdfGraphics graphics, RectangleF bounds)</td><td>
Void</td></tr>
<tr>
<td>
(PdfPage page, float x, float y)</td><td>
PdfGridLayoutResult</td></tr>
<tr>
<td>
(PdfPage page, PointF location, PdfGridLayoutFormat format)</td><td>
PdfGridLayoutResult</td></tr>
<tr>
<td>
(PdfPage page, PointF location, PdfLayoutFormat format)</td><td>
PdfLayoutResult</td></tr>
<tr>
<td>
(PdfPage page, RectangleF bounds, PdfGridLayoutFormat format)</td><td>
PdfGridLayoutResult</td></tr>
<tr>
<td>
(PdfPage page, PointF location, PdfLayoutFormat format)</td><td>
PdfLayoutResult</td></tr>
<tr>
<td>
(PdfGraphics graphics, float x, float y)</td><td>
void</td></tr>
<tr>
<td>
(PdfGraphics graphics, PointF location, float width)</td><td>
void</td></tr>
<tr>
<td>
(PdfPage page, float x, float y, float width)</td><td>
PdfGridLayoutResult</td></tr>
<tr>
<td>
PdfPage page, float x, float y, PdfGridLayoutFormat format)</td><td>
PdfGridLayoutResult</td></tr>
<tr>
<td>
(Pd
fPage page, float x, float y, PdfLayoutFormat format)</td><td>
PdfLayoutResult</td></tr>
<tr>
<td>
(PdfGraphics graphics, float x, float y, float width)</td><td>
void</td></tr>
<tr>
<td>
(PdfPage page, float x, float y, float width, PdfGridLayoutFormat format)</td><td>
PdfGridLayoutResult</td></tr>
</table>

Events

Events Table

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
BeginPageLayout</td><td>
This event is raised before the element is printed on the page.(Inherited from PdfLayoutElement.)</td></tr>
<tr>
<td>
EndPageLayout</td><td>
This event is raised after the element is printed on the page.(Inherited from PdfLayoutElement.)</td></tr>
</table>

### Creating a grid

N> You must add Syncfusion.Pdf.Grid namespace to work with PdfGrid.

You can create a PdfGrid by simply specifying the new operator with a proper constructor. After assigning data source to the grid, it can be drawn using one of the overloads available in its Draw method.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Creates a PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Adds rows to the DataTable.

 dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;

//Draws grid to the page of PDF document.

pdfGrid.Draw(page, new PointF(10, 10));

//Saves the document.

 doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Creates a PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Adds rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable

'Draws grid to the page of PDF document.

pdfGrid.Draw(page, New PointF(10, 10))

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}


You can enter the data to PdfGrid manually or from an external data source. Also, the draw method helps you to control the layout of the PdfGrid and returns information after rendering the grid. The following topics discuss them.

* Data
* Layout

#### Data


External Data Source

You can bind data to a PdfGrid by associating it with an external data source. You can set the external data source by using the DataSource property. The following code example illustrates the same.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Creates a PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Adds rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;

//Draws grid to the page of PDF document.

pdfGrid.Draw(page, new PointF(10, 10));

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Creates a PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Adds rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable.

'Draws grid to the page of PDF document.

pdfGrid.Draw(page, New PointF(10, 10))

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True)
{% endhighlight %}


Direct Rows and Columns

Alternatively, you can bind data to a PdfGrid without setting any data source. This is achieved using the PdfGridRow and PdfGridColumn classes. The following code example illustrates this.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Adds three columns.

pdfGrid.Columns.Add(3);

//Adds header.

pdfGrid.Headers.Add(1);

PdfGridRow pdfGridHeader = pdfGrid.Headers[0];

pdfGridHeader.Cells[0].Value = "Employee ID";

pdfGridHeader.Cells[1].Value = "Employee Name";

pdfGridHeader.Cells[2].Value = "Salary";

//Adds rows.

PdfGridRow pdfGridRow = pdfGrid.Rows.Add();

pdfGridRow.Cells[0].Value = "E01";

pdfGridRow.Cells[1].Value = "Clay";

pdfGridRow.Cells[2].Value = "$10,000";

//Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Adds three columns.

pdfGrid.Columns.Add(3)

'Adds header.

pdfGrid.Headers.Add(1)

Dim pdfGridHeader As PdfGridRow = pdfGrid.Headers(0)

pdfGridHeader.Cells(0).Value = "Employee ID"

pdfGridHeader.Cells(1).Value = "Employee Name"

pdfGridHeader.Cells(2).Value = "Salary"

'Adds rows.

Dim pdfGridRow As PdfGridRow = pdfGrid.Rows.Add()

pdfGridRow.Cells(0).Value = "E01"

pdfGridRow.Cells(1).Value = "Clay"

pdfGridRow.Cells(2).Value = "$10,000"

'Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)
{% endhighlight %}

#### Layout

PdfGridLayoutFormat

You can create the layout of PdfGrid  using the PdfGridLayoutFormat class. Overload accepting pages can accept standard formats as other layout elements. However, they treat the PdfLayoutBreakType.FitElement value of Format.Break property for a single row and not for the entire PdfGrid. 

Properties

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
Break</td><td>
Gets or sets the break type.</td><td>
PdfLayoutBreakType</td></tr>
<tr>
<td>
Layout</td><td>
Gets or sets the layout type.</td><td>
PdfLayoutType</td></tr>
<tr>
<td>
PaginateBounds</td><td>
Gets or sets the PdfGrid bounds for the following page.</td><td>
RectangleF</td></tr>
</table>


The PdfLayoutType class is used to specify the type of pagination. The Paginate LayoutType draws the PdfGrid to the next following pages, when the element exceeds the page. The OnePage layout draws the element only on one page. The following code example illustrates this.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

PdfGridLayoutFormat format = new PdfGridLayoutFormat();

format.Layout = PdfLayoutType.Paginate;

format.Break = PdfLayoutBreakType.FitElement;

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Adds rows to the DataTable.

for (int i = 0; i < 150;i++ )

{

dataTable.Rows.Add(new object[] { "E" + i.ToString(), "Name" + i.ToString() });

}

//Assigns data source.

pdfGrid.DataSource = dataTable;

//Draws the grid in to the page of the PDF document.

pdfGrid.Draw(pdfPage, new PointF(10, 10),format);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

Dim format As New PdfGridLayoutFormat()

format.Layout = PdfLayoutType.Paginate

format.Break = PdfLayoutBreakType.FitElement

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Adds rows to the DataTable.

For i As Integer = 0 To 149

dataTable.Rows.Add(New Object() {"E" + i.ToString(), "Name" + i.ToString()})

Next

'Assigns data source.

 pdfGrid.DataSource = dataTable

'Draws grid to the page of the PDF document.

pdfGrid.Draw(pdfPage, New PointF(10, 10), format)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

PdfGridLayoutResult

You can get layout settings for the drawn PdfGrid with the help of PdfGridLayoutResult class. You can also get the bounds and the last page where the PdfGrid is drawn using the Bounds and Page properties. This is mainly used to render the PDF element with respect to the position of the Grid.

Properties

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
Bounds</td><td>
Gets the bounds in the last page it was drawn.</td><td>
RectangleF</td></tr>
<tr>
<td>
Page</td><td>
Gets the last page where PdfLightTable was drawn.</td><td>
PdfPage</td></tr>
</table>


{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;

//Draws the PdfGrid.

PdfGridLayoutResult result = pdfGrid.Draw(pdfPage, PointF.Empty);

//Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString());

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Adds rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable

'Draws the PdfGrid.

Dim result As PdfGridLayoutResult = pdfGrid.Draw(pdfPage, PointF.Empty)

'Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString())

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)
{% endhighlight %}

### Formatting a grid

This section explains you the direct options available to format PdfGrid. The PdfGridStyle class, accessible through Style property of PdfGrid provides options to format entire PdfGrid or parts of it. Formatting applicable for the entire PdfGrid using PdfGridStyle class is discussed here. Header, Row, Column, and Cell are discussed in the following sections.

N> If the style properties are applied to both PdfGridCell and PdfGridRow, PdfGridCell takes the precedence. Following is an example for the exact order of precedence.

PdfBrush backgroundBrush = Cell.BackgroundBrush ?? Row.Style.BackgroundBrush ?? Row.Grid.Style.BackgroundBrush

Properties

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
AllowHorizontalOverflow</td><td>
Gets or sets a value indicating whether to allow horizontal overflow.</td><td>
Boolean</td></tr>
<tr>
<td>
BackgroundBrush</td><td>
Gets or sets background brush.</td><td>
PdfBrush</td></tr>
<tr>
<td>
BorderOverlapStyle</td><td>
Gets or sets border overlap style.</td><td>
PdfBorderOverlapStyle</td></tr>
<tr>
<td>
CellPadding</td><td>
Gets or sets cell padding.</td><td>
PdfPaddings</td></tr>
<tr>
<td>
CellSpacing</td><td>
Gets or sets cell spacing.</td><td>
Float</td></tr>
<tr>
<td>
Font</td><td>
Gets or sets the font.</td><td>
PdfFont</td></tr>
<tr>
<td>
HorizontalOverflowType</td><td>
Gets or sets the type of horizontal overflow.</td><td>
PdfHorizontalOverflowType</td></tr>
<tr>
<td>
TextBrush</td><td>
Gets or sets the text brush.</td><td>
PdfBrush</td></tr>
<tr>
<td>
TextPen</td><td>
Gets or sets the text pen.</td><td>
PdfPen</td></tr>
</table>


AllowHorizontalOverflow

When you set AllowHorizontalOverflow to True, the columns exceeding the current page width gets wrapped and drawn to the next or last page. The default value is false. It should be used along with HorizontalOverflowType property. The default value of HorizontalOverflowType is PdfHorizontalOverflowType.LastPage.

BorderOverlapStyle

This property decides if the cell border should overlap with neighboring cells or to draw the interior of cell.

N> This property applies for all cells in the PdfGrid. Be careful while using overlapping borders, because they may produce bad results if they are not of the same width and color.

CellPadding 

The distance between text and border inside a cell otherwise known as CellPadding, can be set to all cells in the PdfGrid. The PdfPaddings class allows setting padding to individual or all sides.

CellSpacing 

The distance between the cells otherwise known as CellSpacing, can be set to all cells in PdfGrid using CellSpacing property.

#### Header

Header

Header is a set of rows that can be optionally repeated on each page and has its own style. You can add header as follows:

* Directly from column captions.
* By using Add method of the PdfGridHeaderCollection class.



N> When you bind data source to PdfGrid, column captions will be automatically added to header collection. It can be removed at any time using Clear method of PdfGridHeaderCollection.

The following code example illustrates how to add headers to PdfGrid by using the Add method.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add();

dataTable.Columns.Add();

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;

//Add a new header to PdfGrid.

pdfGrid.Headers.Add(1);

//Get the first header row.

PdfGridCellCollection collection = pdfGrid.Headers[0].Cells;

//Set the header names.

collection[0].Value = "ID";

collection[1].Value = "Name";

//Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add()

dataTable.Columns.Add()

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable

'Add a new header to PdfGrid.

pdfGrid.Headers.Add(1)

'Get the first header row.

Dim collection As PdfGridCellCollection = pdfGrid.Headers(0).Cells

'Set the header names.

collection(0).Value = "ID"

collection(1).Value = "Name"

'Draws the PdfGrid.

Dim result As PdfGridLayoutResult = pdfGrid.Draw(pdfPage, PointF.Empty)

'Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString())

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

RepeatHeader

Header can be set to repeat on each page where PdfGrid is paginated. You can achieve this by setting RepeatHeader property as true.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add();

dataTable.Columns.Add();

//Add rows to the DataTable.

for (int i = 0; i < 100; i++)

{

     dataTable.Rows.Add(new object[] { "E01", "Clay" });

     dataTable.Rows.Add(new object[] { "E02", "Thomas" });

}

//Assigns data source.

pdfGrid.DataSource = dataTable;

// Add a new header to PdfGrid.

pdfGrid.Headers.Add(1);

// Get the first header row.

PdfGridCellCollection collection = pdfGrid.Headers[0].Cells;

//Set the header names.

collection[0].Value = "ID";

collection[1].Value = "Name";



//Set RepeatHeader to true

pdfGrid.RepeatHeader = true;



//Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add()

dataTable.Columns.Add()

'Add rows to the DataTable.

For i As Integer = 0 To 99

    dataTable.Rows.Add(New Object() {"E01", "Clay"})

    dataTable.Rows.Add(New Object() {"E02", "Thomas"})

Next

'Assigns data source.

pdfGrid.DataSource = dataTable

'Add a new header to PdfGrid.

pdfGrid.Headers.Add(1)

'Get the first header row.

Dim collection As PdfGridCellCollection = pdfGrid.Headers(0).Cells

'Set the header names.

collection(0).Value = "ID"

collection(1).Value = "Name"



'Set RepeatHeader to true

pdfGrid.RepeatHeader = True



'Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

Style

You can specify the header style for the PdfGrid by using the PdfGridRowStyle or PdfGridCellStyle classes. The style applied at the collection is applied to all rows in the header. Following code example illustrates how to specify the header style.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add();

dataTable.Columns.Add();

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;

//Add a new header to PdfGrid.

pdfGrid.Headers.Add(1);

//Get the first header row.

PdfGridCellCollection collection = pdfGrid.Headers[0].Cells;

//Set the header names.

collection[0].Value = "ID";

collection[1].Value = "Name";

pdfGrid.RepeatHeader = true;



//Create an instance of PdfGridRowStyle

PdfGridRowStyle pdfGridRowStyle = new PdfGridRowStyle();

pdfGridRowStyle.BackgroundBrush = PdfBrushes.LightYellow;

pdfGridRowStyle.Font = new PdfStandardFont(PdfFontFamily.Courier, 10);

pdfGridRowStyle.TextBrush = PdfBrushes.Blue;

pdfGridRowStyle.TextPen = PdfPens.Pink;

pdfGrid.Headers.ApplyStyle(pdfGridRowStyle);



//Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add()

dataTable.Columns.Add()

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable

'Add a new header to PdfGrid.

pdfGrid.Headers.Add(1)

'Get the first header row.

Dim collection As PdfGridCellCollection = pdfGrid.Headers(0).Cells

'Set the header names.

collection(0).Value = "ID"

collection(1).Value = "Name"

pdfGrid.RepeatHeader = True



'Create an instance of PdfGridRowStyle

Dim pdfGridRowStyle As New PdfGridRowStyle()

pdfGridRowStyle.BackgroundBrush = PdfBrushes.LightYellow

pdfGridRowStyle.Font = New PdfStandardFont(PdfFontFamily.Courier, 10)

pdfGridRowStyle.TextBrush = PdfBrushes.Blue

pdfGridRowStyle.TextPen = PdfPens.Pink

pdfGrid.Headers.ApplyStyle(pdfGridRowStyle)



'Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

N> Styles for each PdfGridRow in Header can be individually applied using PdfGridRowStyle class.

Refer to the following topics for more details:

* PdfGridRowStyle
* PdfGridCellStyle

#### Row


Row

Height

The Height property of the PdfGridRow class is used to specify the row height for the PdfGrid rows. The following code example illustrates you how to set this property.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



//Set row height

pdfGrid.Rows[0].Height = 30;



//Draws the PdfGrid.

PdfGridLayoutResult result = pdfGrid.Draw(pdfPage, PointF.Empty);

//Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString());

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);


{% endhighlight %}


{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Set row height

pdfGrid.Rows(0).Height = 30



'Draws the PdfGrid.

Dim result As PdfGridLayoutResult = pdfGrid.Draw(pdfPage, PointF.Empty)

'Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString())

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}



N> The unit of the Height property is always points. You can set the PDF units only as points. Also, you can use the PdfUnitConvertor class to convert the other units to points.

Row Span

PdfGrid enables you to merge cells within a row. You can specify the number of cells to be merged using the RowSpan property of PdfGridCell class. The following code example illustrates this.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



//Merging row cells.

pdfGrid.Rows[0].Cells[0].RowSpan = 2;



//Draws the PdfGrid.

PdfGridLayoutResult result = pdfGrid.Draw(pdfPage, PointF.Empty);

//Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString());

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Merging row cells.

pdfGrid.Rows(0).Cells(0).RowSpan = 2



'Draws the PdfGrid.

Dim result As PdfGridLayoutResult = pdfGrid.Draw(pdfPage, PointF.Empty)

'Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString())

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

Style

The PdfGridRowStyle class, accessed through Style property of PdfGridRow class is used to specify the row style for the PdfGrid rows.

N> If the style properties are applied to both PdfGridCell and PdfGridRow, PdfGridCell takes over the precedence. Following is an example for the exact order of precedence.

PdfBrush backgroundBrush = Cell.BackgroundBrush ?? Row.Style.BackgroundBrush ?? Row.Grid.Style.BackgroundBrush

The following code example illustrates you on how to specify the row style for the PdfGrid rows:

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



//Create an instance of PdfGridRowStyle

PdfGridRowStyle pdfGridRowStyle = new PdfGridRowStyle();

pdfGridRowStyle.BackgroundBrush = PdfBrushes.LightYellow;

pdfGridRowStyle.Font = new PdfStandardFont(PdfFontFamily.Courier, 10);

pdfGridRowStyle.TextBrush = PdfBrushes.Blue;

pdfGridRowStyle.TextPen = PdfPens.Pink;



//Set style for the PdfGridRow.

pdfGrid.Rows[0].Style = pdfGridRowStyle;



//Draws the PdfGrid.

PdfGridLayoutResult result = pdfGrid.Draw(pdfPage, PointF.Empty);

//Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString());

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Create an instance of PdfGridRowStyle

Dim pdfGridRowStyle As New PdfGridRowStyle()

pdfGridRowStyle.BackgroundBrush = PdfBrushes.LightYellow

pdfGridRowStyle.Font = New PdfStandardFont(PdfFontFamily.Courier, 10)

pdfGridRowStyle.TextBrush = PdfBrushes.Blue

pdfGridRowStyle.TextPen = PdfPens.Pink



'Set style for the PdfGridRow.

pdfGrid.Rows(0).Style = pdfGridRowStyle



'Draws the PdfGrid.

Dim result As PdfGridLayoutResult = pdfGrid.Draw(pdfPage, PointF.Empty)

'Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString())

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)


{% endhighlight %}


You can also apply PdfGridCellStyle to a PdfGridRow using the ApplyStyle property. The following code sample illustrates this:

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



PdfGridCellStyle pdfGridCellStyle = new PdfGridCellStyle();

pdfGridCellStyle.BackgroundBrush = PdfBrushes.LightYellow;

pdfGridCellStyle.Font = new PdfStandardFont(PdfFontFamily.Courier, 10);

pdfGridCellStyle.TextBrush = PdfBrushes.Blue;

pdfGridCellStyle.TextPen = PdfPens.Pink;



//Set style for the PdfGridRow.

pdfGrid.Rows[0].ApplyStyle(pdfGridCellStyle);



//Draws the PdfGrid.

PdfGridLayoutResult result = pdfGrid.Draw(pdfPage, PointF.Empty);

//Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString());

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Create an instance of PdfGridRowStyle

Dim pdfGridCellStyle As New PdfGridCellStyle()

pdfGridCellStyle.BackgroundBrush = PdfBrushes.LightYellow

pdfGridCellStyle.Font = New PdfStandardFont(PdfFontFamily.Courier, 10)

pdfGridCellStyle.TextBrush = PdfBrushes.Blue

pdfGridCellStyle.TextPen = PdfPens.Pink



'Set style for the PdfGridRow.

pdfGrid.Rows(0).ApplyStyle(pdfGridCellStyle)



'Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

You can set all rows in the PdfGrid with same style using the ApplyStyle method of PdfGridRowCollection. This style can be a PdfGridRowStyle or PdfGridCellStyle. The following is the code sample.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



PdfGridCellStyle pdfGridCellStyle = new PdfGridCellStyle();

pdfGridCellStyle.BackgroundBrush = PdfBrushes.LightYellow;

pdfGridCellStyle.Font = new PdfStandardFont(PdfFontFamily.Courier, 10);

pdfGridCellStyle.TextBrush = PdfBrushes.Blue;

pdfGridCellStyle.TextPen = PdfPens.Pink;



//Set style for the PdfGridRow.

pdfGrid.Rows.ApplyStyle(pdfGridCellStyle);



//Draws the PdfGrid.

PdfGridLayoutResult result = pdfGrid.Draw(pdfPage, PointF.Empty);

//Returns the rectangle value for the last page.

Console.WriteLine(result.Bounds.ToString());

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Create an instance of PdfGridRowStyle

Dim pdfGridCellStyle As New PdfGridCellStyle()

pdfGridCellStyle.BackgroundBrush = PdfBrushes.LightYellow

pdfGridCellStyle.Font = New PdfStandardFont(PdfFontFamily.Courier, 10)

pdfGridCellStyle.TextBrush = PdfBrushes.Blue

pdfGridCellStyle.TextPen = PdfPens.Pink



'Set style for the PdfGridRow.

pdfGrid.Rows.ApplyStyle(pdfGridCellStyle)



'Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

Refer to the following topic for more details:

PdfGridCellStyle

#### Column

Width

By default, all the columns in PdfGrid have equal width, and the columns automatically fill the entire width of the PdfGrid. If the width of the PdfGrid is increased or decreased, the column width also changes appropriately.

You can specify the width for a particular column by using the Width property. The following code example illustrates how to set the width.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



//Set Width for first column.

pdfGrid.Columns[0].Width = 20f;



//Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Set Width for first column.

pdfGrid.Columns(0).Width = 20.0F



'Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}



N> The unit of the Width property is always points. You can set the PDF units only as points. Also, you can use the PdfUnitConvertor class to convert the other units to points.

Column Span

PdfGrid enables you to merge cells within a column. You can specify the number of cells to be merged by using the ColumnSpan property PdfGridCell class. The following code example illustrates this.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a new PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Add rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



// Merging column cells.

pdfGrid.Rows[0].Cells[0].ColumnSpan = 2;



//Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a new PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Add rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Merging column cells.

pdfGrid.Rows(0).Cells(0).ColumnSpan = 2



'Draws the PdfGrid.

pdfGrid.Draw(pdfPage, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

Format 

You can specify the content format for the PdfGrid columns by using the Format property. Check String Formatting in DrawingText for more details

#### Cell

Properties

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
{{ '[ColumnSpan](http://help.syncfusion.com/ug/windows%20forms/documents/column2.htm)' | markdownify }}</td><td>
Gets or set the column span.</td><td>
Integer</td></tr>
<tr>
<td>
Height</td><td>
Gets the height.</td><td>
Float</td></tr>
<tr>
<td>
ImagePosition</td><td>
Gets or sets the image alignment type of the background image.</td><td>
PdfGridImagePosition</td></tr>
<tr>
<td>
{{ '[RowSpan](http://help.syncfusion.com/ug/windows%20forms/documents/row2.htm)' | markdownify }}</td><td>
Gets or sets the row span</td><td>
Integer</td></tr>
<tr>
<td>
{{ '[StringFormat](http://help.syncfusion.com/ug/windows%20forms/documents/drawingtext.htm)' | markdownify }}</td><td>
Gets or sets the string format.</td><td>
PdfStringFormat</td></tr>
<tr>
<td>
Style</td><td>
Gets or sets the cell style.</td><td>
PdfGridCellStyle</td></tr>
<tr>
<td>
Value</td><td>
Gets or sets the value.</td><td>
Object</td></tr>
<tr>
<td>
Width</td><td>
Gets the width.</td><td>
float</td></tr>
</table>

Cell Size

The width and height cannot be modified for a single cell, but for the entire column or row. Please check PdfGridColumn and PdfGridRow for more details.

Value

You can specify the value for an individual cell using the Value property. Also, you can specify another PdfGrid as the cell value to make a nested table. The following code sample illustrates this.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

PdfPage pdfPage = pdfDocument.Pages.Add();



PdfGrid parentPdfGrid = new PdfGrid();



PdfGridRow row1 = parentPdfGrid.Rows.Add();

PdfGridRow row2 = parentPdfGrid.Rows.Add();



row2.Height = 58;



parentPdfGrid.Columns.Add(3);



//Set the value to the specific cell.

parentPdfGrid.Rows[0].Cells[0].Value = "Nested Table";

parentPdfGrid.Rows[0].Cells[1].RowSpan = 2;

parentPdfGrid.Rows[0].Cells[1].ColumnSpan = 2;



PdfGrid childPdfGrid = new PdfGrid();

childPdfGrid.Columns.Add(5);

for (int i = 0; i < 5; i++)

{

    PdfGridRow row = childPdfGrid.Rows.Add();

    for (int j = 0; j < 5; j++)

    {

         row.Cells[j].Value = String.Format("Cell [{0} {1}]", j, i);

    }

}



//Set the value as another PdfGrid in a cell.

parentPdfGrid.Rows[0].Cells[1].Value = childPdfGrid;



//Draws the PdfGrid.

parentPdfGrid.Draw(pdfPage, PointF.Empty);



//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);
{% endhighlight %}


{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()



Dim parentPdfGrid As New PdfGrid()



Dim row1 As PdfGridRow = parentPdfGrid.Rows.Add()

Dim row2 As PdfGridRow = parentPdfGrid.Rows.Add()



row2.Height = 58



parentPdfGrid.Columns.Add(3)



'Set the value to the specific cell.

parentPdfGrid.Rows(0).Cells(0).Value = "Nested Table"

parentPdfGrid.Rows(0).Cells(1).RowSpan = 2

parentPdfGrid.Rows(0).Cells(1).ColumnSpan = 2



Dim childPdfGrid As New PdfGrid()

childPdfGrid.Columns.Add(5)

For i As Integer = 0 To 4

     Dim row As PdfGridRow = childPdfGrid.Rows.Add()

     For j As Integer = 0 To 4

           row.Cells(j).Value = [String].Format("Cell [{0} {1}]", j, i)

     Next

Next



'Set the value as another PdfGrid in a cell.

parentPdfGrid.Rows(0).Cells(1).Value = childPdfGrid



'Draws the PdfGrid.

parentPdfGrid.Draw(pdfPage, PointF.Empty)



'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)
{% endhighlight %}

Style

PdfGrid provides various options to customize the cell content, text color, background color, and so on. The following properties can be used for this purpose.

Properties

Property Table

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
BackgroundBrush</td><td>
Gets or sets background brush for the cell.</td><td>
PdfBrush</td></tr>
<tr>
<td>
BackgroundImage</td><td>
Gets or sets background image for the cell.</td><td>
PdfImage</td></tr>
<tr>
<td>
Borders</td><td>
Gets or sets the borders</td><td>
PdfBorders</td></tr>
<tr>
<td>
Font</td><td>
Gets or sets the font.</td><td>
PdfFont</td></tr>
<tr>
<td>
StringFormat</td><td>
Gets or sets the string format</td><td>
PdfStringFormat</td></tr>
<tr>
<td>
TextBrush</td><td>
Gets or sets the text brush.</td><td>
PdfBrush</td></tr>
<tr>
<td>
TextPen</td><td>
Gets or sets the text pen.</td><td>
PdfPen</td></tr>
</table>


The following code example illustrates you on how to customize the cell content.

{% highlight c# %}

//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page.

PdfPage page = doc.Pages.Add();

//Creates a PdfGrid.

PdfGrid pdfGrid = new PdfGrid();

//Creates a DataTable.

DataTable dataTable = new DataTable();

//Adds columns to the DataTable.

dataTable.Columns.Add("ID");

dataTable.Columns.Add("Name");

//Adds rows to the DataTable.

dataTable.Rows.Add(new object[] { "E01", "Clay" });

dataTable.Rows.Add(new object[] { "E02", "Thomas" });

//Assigns data source.

pdfGrid.DataSource = dataTable;



//Specify the style for the PdfGridCell.

PdfGridCellStyle pdfGridCellStyle = new PdfGridCellStyle();

pdfGridCellStyle.BackgroundImage = new PdfBitmap("pdf_button.png");

pdfGridCellStyle.TextPen = PdfPens.Red;

pdfGridCellStyle.Borders.All = PdfPens.Red;



PdfGridCell pdfGridCell = pdfGrid.Rows[0].Cells[0];



//Apply style

pdfGridCell.Style = pdfGridCellStyle;



//Set image position for the background image in the style.

pdfGridCell.ImagePosition = PdfGridImagePosition.Fit;



//Draws grid to the page of PDF document.

pdfGrid.Draw(page, new PointF(10, 10));

//Saves the document.

doc.Save("Output.pdf");

doc.Close(true);

{% endhighlight %}

{% highlight vbnet %}

'Creates a new PDF document.

Dim doc As New PdfDocument()

'Adds a page.

Dim page As PdfPage = doc.Pages.Add()

'Creates a PdfGrid.

Dim pdfGrid As New PdfGrid()

'Creates a DataTable.

Dim dataTable As New DataTable()

'Adds columns to the DataTable.

dataTable.Columns.Add("ID")

dataTable.Columns.Add("Name")

'Adds rows to the DataTable.

dataTable.Rows.Add(New Object() {"E01", "Clay"})

dataTable.Rows.Add(New Object() {"E02", "Thomas"})

'Assigns data source.

pdfGrid.DataSource = dataTable



'Specify the style for the PdfGridCell.

Dim pdfGridCellStyle As New PdfGridCellStyle()

pdfGridCellStyle.BackgroundImage = New PdfBitmap("pdf_button.png")

pdfGridCellStyle.TextPen = PdfPens.Red

pdfGridCellStyle.Borders.All = PdfPens.Red



Dim pdfGridCell As PdfGridCell = pdfGrid.Rows(0).Cells(0)



'Apply style

pdfGridCell.Style = pdfGridCellStyle



'Set image position for the background image in the style.

pdfGridCell.ImagePosition = PdfGridImagePosition.Fit



'Draws grid to the page of PDF document.

pdfGrid.Draw(page, New PointF(10, 10))

'Saves the document.

doc.Save("Output.pdf")

doc.Close(True
{% endhighlight %}

## Light Table vs Grid

Difference between PdfLightTable and PdfGrid

<table>
<tr>
<th>
Platforms</th><th>
PdfLightTable</th><th>
PdfGrid</th></tr>
<tr>
<td>
Windows Forms</td><td>
Yes</td><td>
Yes</td></tr>
<tr>
<td>
WPF</td><td>
Yes</td><td>
Yes</td></tr>
<tr>
<td>
ASP.NET</td><td>
Yes</td><td>
Yes</td></tr>
<tr>
<td>
ASP.NET MVC</td><td>
Yes</td><td>
Yes</td></tr>
<tr>
<td>
Silverlight</td><td>
Yes</td><td>
Yes</td></tr>
<tr>
<td>
WinRT</td><td>
Yes</td><td>
Yes</td></tr>
<tr>
<td>
Windows Phone</td><td>
Yes</td><td>
Yes</td></tr>
</table>
_
Difference between PdfLightTable and PdfGrid

<table>
<tr>
<th>
Features</th><th>
PdfLightTable</th><th>
PdfGrid</th></tr>
<tr>
<td colspan = "3">
Formatting</td></tr>
<tr>
<td>
Row</td><td>
No direct API, possible through events.</td><td>
Yes</td></tr>
<tr>
<td>
Column</td><td>
Yes (StringFormat)</td><td>
Yes (StringFormat)</td></tr>
<tr>
<td>
Cell</td><td>
No direct API for single cell formatting, possible through events.</td><td>
Yes</td></tr>
<tr>
<td colspan = "3">
Others</td></tr>
<tr>
<td>
Row span</td><td>
No</td><td>
Yes</td></tr>
<tr>
<td>
Column span</td><td>
No direct API, possible through events.</td><td>
Yes</td></tr>
<tr>
<td>
Nested Grid</td><td>
Possible through events</td><td>
Yes</td></tr>
<tr>
<td>
Layout Events</td><td>
BeginCellLayout, BeginPageLayout, BeginRowLayout, EndCellLayout, EndPageLayout, EndRowLayout</td><td>
BeginPageLayout, EndPageLayout</td></tr>
</table>


