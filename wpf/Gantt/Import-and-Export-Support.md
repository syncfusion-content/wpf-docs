---
layout: post
title: Import-and-Export-Support
description: import and export support
platform: wpf
control: Gantt
documentation: ug
---

# Import and Export Support

Essential Gantt allows you to export and import the task details. You can export the task details as XML files and import them again when needed. You can open the exported XML files in MS Project too. The XML file, exported from MS Project can also be opened in Gantt control. You can import and export the details using the provided APIs.

_Properties_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
ImportFromXMLCommand</td><td>
Command binding used to import the XML file generated from MS Project to populate data’s in Gantt control.</td><td>
Command</td><td>
DelegateCommand</td></tr>
<tr>
<td>
ExportToXMLCommand</td><td>
Command binding used to export the XML file generated from Gantt control to populate data’s in MS Project.</td><td>
Command</td><td>
DelegateCommand</td></tr>
</table>


_Methods_

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Type </th><th>
Return Type </th></tr>
<tr>
<th>
ExportToXML()</th><th>
Responsible for exporting the GanttControl to MSProject XML File.</th><th>
-</th><th>
-</th><th>
bool</th></tr>
<tr>
<th>
ImportFromXML()</th><th>
Reponsible for importing the data from MS Project XML file to GanttControl.</th><th>
-</th><th>
-</th><th>
bool</th></tr>
</table>


Import/Export Task Details from/to XML

The following code illustrates how to Import and Export Task Details from or to XML.



[XAML]

<Sync:GanttControl x:Name="Gantt" />


<StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
      <Button Height="25" HorizontalAlignment="Center" VerticalAlignment="Center" 

              Margin="0,10,0,0" Width="200"                    
              Command="{Binding ExportToXMLCommand, ElementName=gantt}"                    Content="Export To XML" />
      <Button Height="25" HorizontalAlignment="Center" VerticalAlignment="Center" 

              Margin="0,10,0,0" Width="200"
              Command="{Binding ImportFromXMLCommand, ElementName=gantt}"
              Content="Import From XML" />
</StackPanel>



[C#]

       private void SaveButton_Click(object sender, System.Windows.RoutedEventArgs e)
        {
            if (this.Gantt.ExportToXML())
            {
                MessageBox.Show("Tasks exported successfully.", 
                                "XML Import/Export", 
                                 MessageBoxButton.OK, 
                                 MessageBoxImage.Information);
            }
        }

        private void Open_Click(object sender, System.Windows.RoutedEventArgs e)
        {
            if (this.Gantt.ImportFromXML())
            {
                MessageBox.Show("Tasks imported successfully.", 
                                "XML Import/Export", 
                                MessageBoxButton.OK, 
                                MessageBoxImage.Information);
            }
        }





The following image shows XML Export Import:



{{ '![](Import-and-Export-Support_images/Import-and-Export-Support_img1.png)' | markdownify }}
{:.image }


_XML Export Import_



The following image shows Importing the exported document in MS Project: 



{{ '![](Import-and-Export-Support_images/Import-and-Export-Support_img2.png)' | markdownify }}
{:.image }


_Exported document opened in MS Project_



Samples Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
1. Click Run Samples for WPF under User Interface Edition panel .
2. Select Gantt.
3. Expand the Import Export Features item in the Sample Browser.
4. Choose the Import Export Demo samples to launch.



