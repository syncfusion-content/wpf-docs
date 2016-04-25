---
title: List
description: list
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: list
---
# List

The SfRichTextBoxAdv supports both the single-level and multilevel lists similar to the Microsoft Word. Lists are used to organize data as step-by-step instructions in documents for easy understanding of key points.
## Single Level List

Single level means that all the items in the list have the same hierarchy and indentation. It can be a numbered or a bulleted list.
The following screenshot shows single level bulleted list.
![](List_images/List_img1.jpeg)

The following screenshot shows single level numbered list.
![](List_images/List_img2.jpeg)

## Multilevel List

Multilevel means defining a list within a list where up to nine levels can be defined similar to the Microsoft Word. A multilevel list can be bulleted or numbered and also mixed with numbers, letters, and bullets. For example, one level can be bulleted and next level can be a numbered list inside it.
The following screenshot shows multilevel list.
![](List_images/List_img3.jpeg)

## Adding List

Each list in the document can contain reference to any one of the abstract lists in the document. Both abstract list and list should be defined a unique Id. List should refer the abstract list with the abstract list’s Id. List format for a paragraph should refer to the list with the list’s Id.
The following code example demonstrates how to define a single level numbered list for a document and how it is applied to a paragraph.
<table>
<tr>
<td colspan=1 rowspan=1>
<RichTextBoxAdv:DocumentAdv><br/><RichTextBoxAdv:DocumentAdv.AbstractLists><br/><RichTextBoxAdv:AbstractListAdv AbstractListId="1"><br/><RichTextBoxAdv:AbstractListAdv.Levels><br/><RichTextBoxAdv:ListLevelAdv ListLevelPattern="LowLetter" NumberFormat="%1." StartAt="1" FollowCharacter="Tab" RestartLevel="0"><br/><RichTextBoxAdv:ListLevelAdv.ParagraphFormat><br/><RichTextBoxAdv:ParagraphFormat LeftIndent="48" FirstLineIndent="24"/><br/></RichTextBoxAdv:ListLevelAdv.ParagraphFormat><br/></RichTextBoxAdv:ListLevelAdv><br/></RichTextBoxAdv:AbstractListAdv.Levels><br/></RichTextBoxAdv:AbstractListAdv><br/></RichTextBoxAdv:DocumentAdv.AbstractLists><br/><RichTextBoxAdv:DocumentAdv.Lists><br/><RichTextBoxAdv:ListAdv AbstractListId="1" ListId="1"><br/></RichTextBoxAdv:ListAdv><br/></RichTextBoxAdv:DocumentAdv.Lists><br/><RichTextBoxAdv:SectionAdv><br/><RichTextBoxAdv:ParagraphAdv><br/><RichTextBoxAdv:ParagraphAdv.ParagraphFormat><br/><RichTextBoxAdv:ParagraphFormat><br/><RichTextBoxAdv:ParagraphFormat.ListFormat><br/><RichTextBoxAdv:ListFormat ListId="1" ListLevelNumber="0"/><br/></RichTextBoxAdv:ParagraphFormat.ListFormat><br/></RichTextBoxAdv:ParagraphFormat><br/></RichTextBoxAdv:ParagraphAdv.ParagraphFormat><br/><RichTextBoxAdv:SpanAdv>List Item 1</RichTextBoxAdv:SpanAdv><br/></RichTextBoxAdv:ParagraphAdv><br/></RichTextBoxAdv:SectionAdv><br/></RichTextBoxAdv:DocumentAdv><br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
// Initializes a new abstract list instance.<br/>AbstractListAdv abstractListAdv = new AbstractListAdv(null);<br/>abstractListAdv.AbstractListId = 1;<br/>// Defines new ListLevel instance.<br/>ListLevelAdv listLevel = new ListLevelAdv(abstractListAdv);<br/>listLevel.ParagraphFormat.LeftIndent = 48d;<br/>listLevel.ParagraphFormat.FirstLineIndent = 24d;<br/>listLevel.FollowCharacter = FollowCharacterType.Tab;<br/>listLevel.ListLevelPattern = ListLevelPattern.LowLetter;<br/>listLevel.NumberFormat = "%1.";<br/>listLevel.RestartLevel = 0;<br/>listLevel.StartAt = 1;<br/>// Adds list level to abstract list.<br/>abstractListAdv.Levels.Add(listLevel);<br/>// Adds abstract list to the document.<br/>richTextBoxAdv.Document.AbstractLists.Add(abstractListAdv);<br/>// Creates a new list instance.<br/>ListAdv listAdv = new ListAdv(null);<br/>listAdv.ListId = 1;<br/>// Sets the abstract list Id for this list.<br/>listAdv.AbstractListId = 1;<br/>// Adds list to the document.<br/>richTextBoxAdv.Document.Lists.Add(listAdv);<br/>// Defines the list format for the paragraph.<br/>paragraphAdv.ParagraphFormat.ListFormat.ListId = 1;<br/>paragraphAdv.ParagraphFormat.ListFormat.ListLevelNumber = 0;<br/></td></tr>
</table>
The following code example demonstrates how to define number format for numbered list in the SfRichTextBoxAdv control.
{% tabs %}
{% highlight c# %}
// Defines the number format for the list level.
/* Note
* The percent sign (%) followed by any number from 1 through 9 represents the number style from the respective list level. 
* For example, if you wanted the format for the first level to be "Article I." "Article II," and so on, the string for the NumberFormat property would be "Article %1." and the ListLevelPattern property would be set to ListLevelPattern.UpRoman.
*/
listLevel.NumberFormat = "Article %1.";
listLevel.ListLevelPattern = ListLevelPattern.UpRoman;


{% endhighlight %}

You can define bulleted list by setting list level pattern as Bullet. You can define various bullets by defining the bullet character. The following code sample demonstrates how to define dot, square and arrow bullets in the SfRichTextBoxAdv control.
{% highlight c# %}
// Defines Bulleted List.
listLevel.ListLevelPattern = ListLevelPattern.Bullet;
// Defining Dot Bullet
listLevel.NumberFormat = "\uf0b7";
listLevel.CharacterFormat.FontFamily = new FontFamily("Symbol");
// Defines Square bullet.
listLevel.NumberFormat = "\uf0a7";
listLevel.CharacterFormat.FontFamily = new FontFamily("Wingdings");
// Defines Arrow Bullet.
listLevel.NumberFormat = "\u27a4";
listLevel.CharacterFormat.FontFamily = new FontFamily("Symbol");


{% endhighlight %}

{% endtabs %}
## Level overrides

The list levels for a list are defined in the abstract list to which it refers to. Additionally you can define level overrides for any list level. The SfRichTextBoxAdv supports two types of level overrides.
1. Start at override – Only start value for the list is overridden and other properties are referred to list level defined in abstract list.

2. Level override – The list level is completely overridden.


The following code example demonstrates how to override the start at value for an existing list level in the SfRichTextBoxAdv control.
<table>
<tr>
<td colspan=1 rowspan=1>
<RichTextBoxAdv:ListAdv AbstractListId="1" ListId="1"><br/><RichTextBoxAdv:ListAdv.LevelOverrides><br/><RichTextBoxAdv:LevelOverrideAdv StartAt="2" LevelNumber="0"/><br/></RichTextBoxAdv:ListAdv.LevelOverrides><br/></RichTextBoxAdv:ListAdv><br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
// Adds StartAtOverride for the list at first level.<br/>// LevelNumber ranges from 0 to 8.<br/>LevelOverrideAdv levelOverride = new LevelOverrideAdv(listAdv);<br/>levelOverride.LevelNumber = 0;<br/>levelOverride.StartAt = 2;<br/>listAdv.LevelOverrides.Add(levelOverride);<br/></td></tr>
</table>
The following code example demonstrates how to add level override for any existing list level in the SfRichTextBoxAdv control.
<table>
<tr>
<td colspan=1 rowspan=1>
<RichTextBoxAdv:ListAdv AbstractListId="1" ListId="1"><br/><RichTextBoxAdv:ListAdv.LevelOverrides><br/><!-- Overrides fourth list level--><br/><RichTextBoxAdv:LevelOverrideAdv LevelNumber="3"><br/><RichTextBoxAdv:LevelOverrideAdv.OverrideListLevel><br/><RichTextBoxAdv:ListLevelAdv ListLevelPattern="UpRoman" StartAt="3" NumberFormat="%1)"/><br/></RichTextBoxAdv:LevelOverrideAdv.OverrideListLevel><br/></RichTextBoxAdv:LevelOverrideAdv><br/></RichTextBoxAdv:ListAdv.LevelOverrides><br/></RichTextBoxAdv:ListAdv><br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
// Adds ListLevel override for the list at fourth level.<br/>// LevelNumber ranges from 0 to 8.<br/>LevelOverrideAdv levelOverride = new LevelOverrideAdv(listAdv);<br/>levelOverride.LevelNumber = 3;<br/>levelOverride.OverrideListLevel = new ListLevelAdv(levelOverride);<br/>levelOverride.OverrideListLevel.ListLevelPattern = ListLevelPattern.UpRoman;<br/>levelOverride.OverrideListLevel.NumberFormat = "%1)";<br/>levelOverride.OverrideListLevel.StartAt = 3;<br/>listAdv.LevelOverrides.Add(levelOverride);<br/></td></tr>
</table>
## Editing list

You can retrieve the list applied for the current selection. By doing so, you can edit the list according to your requirement. After editing the list, you need to set it for the current selection in order to make the changes effective.
The following code sample demonstrates how to apply the list to the selection content in the SfRichTextBoxAdv control.
{% tabs %}
{% highlight c# %}
// Gets the current list for the selection content.
ListAdv listAdv = richTextBoxAdv.Selection.ParagraphFormat.GetList();


{% endhighlight %}

The following code example demonstrates how to apply a list for the selection content in the SfRichTextBoxAdv control. When the selection content has a list, then it gets modified with that list. Otherwise the list is added to the document and applied to the selection content.
{% highlight c# %}
// Applies list for the Selection content.
richTextBoxAdv.Selection.ParagraphFormat.SetList(listAdv);
richTextBoxAdv.Selection.ParagraphFormat.ListLevelNumber = 0;


{% endhighlight %}

{% endtabs %}
