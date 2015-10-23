---
layout: Post
title: List
description: list
platform: wpf
control: RichTextBoxAdv
documentation: ug
---
#### ListAdv

The **ListAdv** class represents a list that adds or edits in the document by using the **Lists** property of the **DocumentAdv** class. Each **ListAdv** instance contains reference to any one of the abstract lists in the document and optionally contains the definition of the list level overrides.

<table>
<tr>
<td>
**Properties**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Class**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
AbstractList<br/><br/></td><td>
AbstractListAdv<br/><br/></td><td>
ListAdv<br/><br/></td><td>
Gets or sets the abstract list referred to the list.<br/><br/></td></tr>
<tr>
<td>
AbstractListId<br/><br/></td><td>
int<br/><br/></td><td>
ListAdv<br/><br/></td><td>
Gets or sets the id of the abstract list referred to the list.<br/><br/></td></tr>
<tr>
<td>
LevelOverrides<br/><br/></td><td>
LevelOverrideCollectionAdv<br/><br/></td><td>
ListAdv<br/><br/></td><td>
Gets the list level overrides collection of the list.<br/><br/></td></tr>
<tr>
<td>
ListId<br/><br/></td><td>
int<br/><br/></td><td>
ListAdv<br/><br/></td><td>
Gets or sets the id for the list.<br/><br/></td></tr>
</table>
<table>
<tr>
<td>
**Method**<br/><br/></td><td>
**Return** **Type**<br/><br/></td><td>
**Parameters**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
Dispose<br/><br/></td><td>
void<br/><br/></td><td>
<br/><br/></td><td>
Releases all the resources used by the list.<br/><br/></td></tr>
</table>
**LevelOverrideAdvCollection******

The **LevelOverrideAdvCollection** class contains a collection of list level overrides. You can get the **LevelOverrideAdv** instance of the specified level by using the **indexer** property.

<table>
<tr>
<td>
**Property**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Class**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
Count<br/><br/></td><td>
int<br/><br/></td><td>
LevelOverrideCollectionAdv<br/><br/></td><td>
Returns the number of level overrides present in the collection.<br/><br/></td></tr>
</table>
<table>
<tr>
<td>
**Methods**<br/><br/></td><td>
**Return** **Type**<br/><br/></td><td>
**Parameters**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
Add<br/><br/></td><td>
void<br/><br/></td><td>
int levelNumber, LevelOverrideAdv levelOverride<br/><br/></td><td>
Adds the list level override for the specified level number.<br/><br/></td></tr>
<tr>
<td>
Clear<br/><br/></td><td>
void<br/><br/></td><td>
<br/><br/></td><td>
Clears the list level overrides in the collection.<br/><br/></td></tr>
<tr>
<td>
Dispose<br/><br/></td><td>
void<br/><br/></td><td>
<br/><br/></td><td>
Releases all the resources used by the level override collection.<br/><br/></td></tr>
</table>
**LevelOverrideAdv******

The **LevelOverrideAdv** class represents a list level override that has the definition for start at value and list level properties to override the abstract list. You can define level overrides for any existing level of the list.

<table>
<tr>
<td>
**Properties**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Class**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
OwnerList<br/><br/></td><td>
ListAdv<br/><br/></td><td>
LevelOverrideAdv<br/><br/></td><td>
Gets the owner list.<br/><br/></td></tr>
<tr>
<td>
StartAt<br/><br/></td><td>
int<br/><br/></td><td>
LevelOverrideAdv<br/><br/></td><td>
Gets or sets the start at value to override the start at value of the abstract list.<br/><br/></td></tr>
<tr>
<td>
OverrideListLevel<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
LevelOverrideAdv<br/><br/></td><td>
Gets or sets the list level to override the list level of abstract list.<br/><br/></td></tr>
<tr>
<td>
LevelNumber<br/><br/></td><td>
int<br/><br/></td><td>
LevelOverrideAdv<br/><br/></td><td>
Gets or sets the level number to override.<br/><br/></td></tr>
</table>
<table>
<tr>
<td>
**Method**<br/><br/></td><td>
**Return** **Type**<br/><br/></td><td>
**Parameters**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
Dispose<br/><br/></td><td>
void<br/><br/></td><td>
<br/><br/></td><td>
Releases all the resources used by the level override.<br/><br/></td></tr>
</table>
#### AbstractListAdv

The **AbstractListAdv** class represents the abstract list that has the definition for the abstract list levels. An abstract list can be referred to one or more lists in the document.

<table>
<tr>
<td>
**Property**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Class**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
AbstractListId<br/><br/></td><td>
int<br/><br/></td><td>
AbstractListAdv<br/><br/></td><td>
Gets or sets the id for the abstract list.<br/><br/></td></tr>
<tr>
<td>
Levels<br/><br/></td><td>
ListLevelCollectionAdv<br/><br/></td><td>
AbstractListAdv<br/><br/></td><td>
Gets the list level collection of abstract list.<br/><br/></td></tr>
</table>
**ListLevelAdvCollection******

The **ListLevelAdvCollection** class contains a collection of list levels. You can get the **ListLevelAdv** instance of the specified level by using the **indexer** property. A single level list has only one list level, whereas a multi-level list has nine list levels.

<table>
<tr>
<td>
**Property**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Class**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
Count<br/><br/></td><td>
int<br/><br/></td><td>
ListLevelCollectionAdv<br/><br/></td><td>
Returns the number of list levels present in the collection.<br/><br/></td></tr>
</table>
<table>
<tr>
<td>
**Methods**<br/><br/></td><td>
**Return** **Type**<br/><br/></td><td>
**Parameters**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
Add<br/><br/></td><td>
void<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Adds the list level to the collection.<br/><br/></td></tr>
<tr>
<td>
Clear<br/><br/></td><td>
void<br/><br/></td><td>
<br/><br/></td><td>
Clears the list levels in the collection.<br/><br/></td></tr>
<tr>
<td>
Dispose<br/><br/></td><td>
void<br/><br/></td><td>
<br/><br/></td><td>
Releases all the resources used by the list level collection.<br/><br/></td></tr>
</table>
#### ListLevelAdv

The **ListLevelAdv** class represents a list level that has the definition for properties of a list level. You can define the list level properties for the abstract list and level overrides of the list.

<table>
<tr>
<td>
**Properties**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Class**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
ListLevelPattern<br/><br/></td><td>
ListLevelPattern<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets or sets the list pattern of the list level. Bullet, number, letter, etc.<br/><br/></td></tr>
<tr>
<td>
FollowCharacter<br/><br/></td><td>
FollowCharacterType<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets or sets the follow character type of the list level. Tab, space, etc.<br/><br/></td></tr>
<tr>
<td>
NumberFormat<br/><br/></td><td>
string<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets or sets the number format for the numbered list or bullet character for the bulleted list.<br/><br/></td></tr>
<tr>
<td>
StartAt<br/><br/></td><td>
int<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets or sets the start at value of the list level.<br/><br/></td></tr>
<tr>
<td>
RestartLevel<br/><br/></td><td>
int<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets or sets the list level that appears before the current list level restarts numbering. This is lesser than the level number.<br/><br/></td></tr>
<tr>
<td>
LevelNumber<br/><br/></td><td>
int<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets the level number of the current list level.<br/><br/></td></tr>
<tr>
<td>
ParagraphFormat<br/><br/></td><td>
ParagraphFormat<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets or sets the paragraph format of the list level.<br/><br/></td></tr>
<tr>
<td>
CharacterFormat<br/><br/></td><td>
CharacterFormat<br/><br/></td><td>
ListLevelAdv<br/><br/></td><td>
Gets or sets the character format of the list level<br/><br/></td></tr>
</table>
<table>
<tr>
<td>
**Method**<br/><br/></td><td>
**Return** **Type**<br/><br/></td><td>
**Parameters**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
<tr>
<td>
Dispose<br/><br/></td><td>
void<br/><br/></td><td>
<br/><br/></td><td>
Releases all the resources used by the current list level.<br/><br/></td></tr>
</table>
#### Add or Edit List

The **RichTextBoxAdv** supports both simple or single list (list with one level) and multilevel list (list with nine levels). It allows you to perform various list manipulations similar to the Microsoft Word. 

* Define a new list and add it to the document.
* Apply list to a paragraph.
* Retrieve list from the selected contents. 
* Apply list to the selected contents.
* Edit existing list.
* Define level overrides to the list.

The following code example demonstrates how to define a simple list for a document in the **RichTextBoxAdv** control.

{% highlight c# %}
// Initializes a new abstract list instance.

AbstractListAdv abstractListAdv = new AbstractListAdv(null);

abstractListAdv.AbstractListId = 1;

// Defines new ListLevel instance.

ListLevelAdv listLevel = new ListLevelAdv(abstractListAdv);

listLevel.ParagraphFormat.LeftIndent = 48d;

listLevel.ParagraphFormat.FirstLineIndent = 24d;

listLevel.FollowCharacter = FollowCharacterType.Tab;

listLevel.ListLevelPattern = ListLevelPattern.LowLetter;

listLevel.NumberFormat = "(%1.)";

listLevel.RestartLevel = 0;

listLevel.StartAt = 1;

// Adds list level to abstract list.

abstractListAdv.Levels.Add(listLevel);

// Creates a new list instance.

ListAdv listAdv = new ListAdv(null);

listAdv.AbstractList = abstractListAdv;

listAdv.AbstractListId = abstractListAdv.AbstractListId;

listAdv.ListId = 1;



{% endhighlight %}

The following code example demonstrates how to add a new list to the document in the **RichTextBoxAdv** control.

{% highlight c# %}
// Adds abstract list to the document.

richTextBoxAdv.Document.AbstractLists.Add(listAdv.AbstractList);

// Adds list to the document.

richTextBoxAdv.Document.Lists.Add(listAdv);



{% endhighlight %}

The following code example demonstrates how to apply the list to a paragraph in the **RichTextBoxAdv** control.

{% highlight c# %}
// Defines list format for a paragraph.

paragraph.ParagraphFormat.ListFormat.ListId = listAdv.ListId;

paragraph.ParagraphFormat.ListFormat.List = listAdv;

paragraph.ParagraphFormat.ListFormat.ListLevelNumber = 0;



{% endhighlight %}

The following code sample demonstrates how to apply the list to the selected content in the **RichTextBoxAdv** control.

{% highlight c# %}
// Gets the current list for the selected content.

ListAdv listAdv = richTextBoxAdv.Selection.ParagraphFormat.GetList();



{% endhighlight %}

The following code example demonstrates how to apply a list for the selected content in the **RichTextBoxAdv** control. When the selection content has a list, then it gets modified with that list. Otherwise that list is added to the document and applied to the selection content.

{% highlight c# %}
// Applies list for the Selected content.

richTextBoxAdv.Selection.ParagraphFormat.SetList(listAdv);

richTextBoxAdv.Selection.ParagraphFormat.ListLevelNumber = 0;



{% endhighlight %}

The following code example demonstrates how to define a bulleted list in the **RichTextBoxAdv** control.

{% highlight c# %}
// Defines the Bulleted List.

listLevel.ListLevelPattern = ListLevelPattern.Bullet;



{% endhighlight %}

The following code sample demonstrates how to define Dot bullet in the **RichTextBoxAdv** control.

{% highlight c# %}
// Defining a Dot Bullet

listLevel.NumberFormat = "\uf0b7";

listLevel.CharacterFormat.FontFamily = new Windows.UI.Xaml.Media.FontFamily("Symbol");



{% endhighlight %}

The following code example demonstrates how to define Square bullet in the **RichTextBoxAdv** control.

{% highlight c# %}
// Defines a Square bullet.

listLevel.NumberFormat = "\uf0a7";

listLevel.CharacterFormat.FontFamily = new Windows.UI.Xaml.Media.FontFamily("Wingdings");



{% endhighlight %}

The following code example demonstrates how to define Arrow bullet in the **RichTextBoxAdv** control.

{% highlight c# %}
// Defines a Arrow Bullet.

listLevel.NumberFormat = "\u27a4";

listLevel.CharacterFormat.FontFamily = new Windows.UI.Xaml.Media.FontFamily("Symbol");



{% endhighlight %}

The following code example demonstrates how to define number format for numbered list in the **RichTextBoxAdv** control.

{% highlight c# %}
// Defines the number format for the list level.

/* Note

* The percent sign (%) followed by any number from 1 to 9 represents the number style from the respective list level. 

* For example, when you want the format for the first level to be "Article I." "Article II," and so on, the string for the NumberFormat property would be "Article %1." and the ListLevelPattern property would be set to ListLevelPattern.UpRoman.

*/

listLevel.NumberFormat = "Article %1.";

listLevel.ListLevelPattern = ListLevelPattern.UpRoman;



{% endhighlight %}

The following code example demonstrates how to override the **StartAt** value for an existing list level in the **RichTextBoxAdv** control.

{% highlight c# %}
// Adds StartAtOverride for the list at LevelNumber = 1.

// LevelNumber ranges from 0 to 8.

LevelOverrideAdv levelOverride = new LevelOverrideAdv(listAdv);

levelOverride.StartAt = 2;

levelOverride.LevelNumber = 1;

listAdv.LevelOverrides.Add(levelOverride);



{% endhighlight %}

The following code example demonstrates how to add level override for any existing list level in the **RichTextBoxAdv** control.

{% highlight c# %}
// Adds ListLevel override for the list at LevelNumber = 4.

// LevelNumber ranges from 0 to 8.

LevelOverrideAdv levelOverride = new LevelOverrideAdv(listAdv);

levelOverride.OverrideListLevel = new ListLevelAdv(levelOverride);

levelOverride.OverrideListLevel.ListLevelPattern = ListLevelPattern.LowRoman;

levelOverride.OverrideListLevel.NumberFormat = "%1)";

levelOverride.OverrideListLevel.StartAt = 3;

levelOverride.LevelNumber = 4;

listAdv.LevelOverrides.Add(levelOverride);



{% endhighlight %}

