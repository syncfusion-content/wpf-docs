---
layout: post
title: AutoComplete | SfTextBoxExt | wpf | Syncfusion
description: auto complete
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Auto Complete

Auto Complete functionality provides suggestions to the user while typing. There are several modes of suggestions. The suggested text can be appended to the original text or it can be displayed in a drop-down list so that user can choose from different options.

## Auto Complete Source

The TextBoxExt control can be populated with a predefined list of items, which will assist the user while typing. Users can choose one item from the filtered list.

For illustration, let us create a textbox, which will populate a list of employees.

The Employee model looks as shown below:


{% highlight c# %}

public class Employee

{

	public string Name { get; set; }



	public string Email { get; set; }

}
	
{% endhighlight %}


Create a collection attribute,


{% highlight c# %}

private List<Employee> employees;

public List<Employee> Employees

{

 get { return employees; }

 set { employees = value; }

}

{% endhighlight %}

Populate the collection with items,

{% highlight c# %}

Employees = new List<Employee>();

Employees.Add(new Employee{Name = "Lucas", Email = "lucas@syncfusion.com"});

Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });

Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });

{% endhighlight %}


Bind the Employees collection to the AutoCompleteSource property of TextBoxExt.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}


At this point, the control is populated with the list of employees. But the Employee model contains two properties Name and Email so we should tell the control, by which property, it has to provide suggestions. In this case, let us make the control to provide suggestions based on Name.

SearchItemPath property specifies the property path by which the filtering has to be done.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}" />
							
{% endhighlight %}
							
![AutoCompleteSource](Auto-Complete_images/Auto-Complete_img1.png)

N> Default value of AutoCompleteMode property is None. So running the control without specifying this property will not show any suggestions. Detailed information about Auto Complete modes will be provided in next section.

## Auto Complete Mode

The suggestions can be displayed in several ways. TextBoxExt supports the following modes of auto complete,

1. None
2. Suggest
3. Append
4. SuggestAppend


The default value of AutoCompleteMode is None.

### Suggest

The filtered suggestions are displayed in a drop-down list.  Users can pick an item from the list.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}

![Suggest](Auto-Complete_images/Auto-Complete_img2.png)

Filtered suggestions displayed in drop-down list
{:.caption}


### Append

The text will be appended to the first matched item in the suggestions collection without opening the drop-down list.


{% highlight xaml %}



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

AutoCompleteMode="Append"

                            AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}

![Append](Auto-Complete_images/Auto-Complete_img3.png)



#### Append mode

N> By default the text will be appended to first matched item. But still user can browse to other items through up and down keys from keyboard.

### SuggestAppend

The text will be appended to the first matched item in the suggestions collection, in addition to opening the drop-down list.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="SuggestAppend"

                            AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}

![SuggestAppend](Auto-Complete_images/Auto-Complete_img4.png)

SuggestAppend mode
{:.caption}


### None

This option neither appends text nor opens the drop-down list of suggestions. 

## AutoComplete Item Template

The AutoCompleteItemTemplate helps to decorate the suggested item with visual elements. The following code block explains how to add an image to the drop-down list item.


{% highlight xaml %}



  <editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="None"

                            AutoCompleteSource="{Binding Employees}" >

            <editors:SfTextBoxExt.AutoCompleteItemTemplate>

                <DataTemplate>

                    <StackPanel Orientation="Horizontal">

                        <Image Source="User.png" Margin="2" Stretch="Uniform" Width="12"/>

                        <TextBlock Text="{Binding Name}" Margin="5 2"/>

                    </StackPanel>

                </DataTemplate>

            </editors:SfTextBoxExt.AutoCompleteItemTemplate>

        </editors:SfTextBoxExt>

{% endhighlight %}

![None mode](Auto-Complete_images/Auto-Complete_img5.png)

Drop down list with image
{:.caption}


## Filtering Customization

The way that the control filters the suggestions can be customized in several ways.

## Suggestion Mode

The property SuggestionMode helps to specify how to compare the string. It contains two built-in modes. 

1. None
2. StartsWith
3. StartsWithCaseSensitive
4. StartsWithOrdinal
5. StartsWithOrdinalCaseSensitive
6. Contains
7. ContainsCaseSensitive
8. ContainsOrdinal
9. ContainsOrdinalCaseSensitive
10. Equals
11. EqualsCaseSensitive
12. EqualsOrdinal
13. EqualsOrdinalCaseSensitive
14. Custom

The default value is StartsWith.

### None

The controls returns the entire collection without filtering when the user types text.


{% highlight xaml %}



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="None"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

 ![SuggestMode None](Auto-Complete_images/Auto-Complete_img6.png)

None case
{:.caption}


### StartsWith

The control returns all possible matches which start with the text typed by the user.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="StartsWith"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![StartsWith](Auto-Complete_images/Auto-Complete_img7.png)


StartsWith case
{:.caption}


### StartsWithCaseSensitive

The control returns all possible matches which start with the text typed by the user which is culture and case sensitive.

{% highlight xaml %}



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="StartsWithCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>
{% endhighlight %}

![StartsWithCaseSensitive](Auto-Complete_images/Auto-Complete_img8.png)



StartsWithCaseSensitive case
{:.caption}


### StartsWithOrdinal

The control returns all possible matches which start with the text typed by the user based on OrdinalIgnoreCase.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="StartsWithOrdinal"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>


{% endhighlight %}

![StartsWithOrdinal](Auto-Complete_images/Auto-Complete_img9.png)


StartsWithOrdinal case
{:.caption}


### StartsWithOrdinalCaseSensitive

The control returns all possible matches which start with the text typed by the user by Ordinal which is case sensitive.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="StartsWithOrdinalCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![StartsWithOrdinalCaseSensitive](Auto-Complete_images/Auto-Complete_img10.png)

StartsWithOrdinalCaseSensitive case
{:.caption}



### Contains

The control return all possible matches which contains the text typed by the user.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="Contains"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>


{% endhighlight %}

![Contains](Auto-Complete_images/Auto-Complete_img11.png)

Contains case
{:.caption}


### ContainsCaseSensitive

The control return all possible matches which contains the text typed by the user which is culture and case sensitive.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="ContainsCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![ContainsCaseSensitive](Auto-Complete_images/Auto-Complete_img12.png)

ContainsCaseSensitive case
{:.caption}


### ContainsOrdinal

The control return all possible matches which contains the text typed by the user based on OrdinalIgnoreCase.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="ContainsOrdinal"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![ContainsOrdinal](Auto-Complete_images/Auto-Complete_img13.png)

ContainsOrdinal case
{:.caption}


### ContainsOrdinalCaseSensitive

The control return all possible matches which contains the text typed by the user based on Ordinal which is case sensitive.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="ContainsOrdinalCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![ContainsOrdinalCaseSensitive](Auto-Complete_images/Auto-Complete_img14.png)

ContainsOrdinalCaseSensitive
{:.caption}


### Equals

The control return all possible matches which equals the text typed by the user.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="Equals"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![Equals](Auto-Complete_images/Auto-Complete_img15.png)

Equals case
{:.caption}

### EqualsCaseSensitive

The control return all possible matches which equals the text typed by the user which is culture and case sensitive.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="EqualsCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>


{% endhighlight %}

![EqualsCaseSensitive](Auto-Complete_images/Auto-Complete_img16.png)

EqualsCaseSensitive case
{:.caption}

### EqualsOrdinal

The control return all possible matches which equals the text typed by the user based on OrdinalIgnoreCase.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="EqualsOrdinal"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![EqualsOrdinal](Auto-Complete_images/Auto-Complete_img17.png)

EqualsOrdinal case
{:.caption}

### EqualsOrdinalCaseSensitive

The control return all possible matches which equals the text typed by the user based on Ordinal which is case sensitive.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="EqualsOrdinalCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![EqualsOrdinalCaseSensitive](Auto-Complete_images/Auto-Complete_img18.png)

EqualsOrdinalCaseSensitive case
{:.caption}


### Custom

The control return all possible matches based on the Filter property. Filter is of type SuggestionPredicate. In the MyFilter method, filtration is done by checking whether the collection contains the typed text

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt x:Name="autoComplete" HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="Custom"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}


{% highlight c# %}    



     public bool MyFilter(string search, object item)

        {

            Person model = item as Person;

            if (model != null)

            {

                if (model.Name.ToLower().Contains(search))

                {

                    return true;

                }

                else

                    return false;

            }

            else

                return false;

        }

		
[c#]

autoComplete.Filter = MyFilter;

{% endhighlight %}

{% endtabs %}


![Custom](Auto-Complete_images/Auto-Complete_img19.png)

Custom case
{:.caption}

N> Append mode always works only with StartsWith behavior. If the typed text is not the same as the start text of any items, it will not append anything even when the auto complete mode is set to Append or SuggestAppend.



### Ignore Case

This option allows the control to filter suggestions by ignoring the case. The default value is false.


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            IgnoreCase="True"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![Ignore Case](Auto-Complete_images/Auto-Complete_img20.png)

Ignore Case
{:.caption}


### Minimum Prefix Length

The MinimumPrefixCharacters property allows the control to filter the typed text based on the number of characters.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

MinimumPrefixCharacters="2"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>
{% endhighlight %}

![Minimum Prefix Length](Auto-Complete_images/Auto-Complete_img21.png)

Minimum Prefix Length case
{:.caption}

### Popup Delay

PopupDelay specifies the delay after which the suggestion popup should open. 


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            PopupDelay="00:00:02"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

### Positioning the Popup

The SuggestionBoxPlacement property defines the position of Popup relative to the control. It contains three built-in options,

1. Top
2. Bottom
3. None

The default value is bottom.

#### Top

The drop-down list will open at top of the control.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionBoxPlacement="Top"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![Top](Auto-Complete_images/Auto-Complete_img22.png)

Drop down list opening at the top
{:.caption}


#### Bottom

The drop-down list will open at bottom of the control.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionBoxPlacement="Bottom"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![Bottom](Auto-Complete_images/Auto-Complete_img23.png)


Drop down list opening at the bottom
{:.caption}


#### None

The drop-down list will not open.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionBoxPlacement="None"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![None](Auto-Complete_images/Auto-Complete_img24.png)

No drop down list
{:.caption}

