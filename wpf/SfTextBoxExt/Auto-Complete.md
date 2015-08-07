---
layout: post
title: Auto-Complete
description: auto complete
platform: wpf
control: TextBoxExt
documentation: ug
---

# Auto Complete

Auto Complete functionality provides suggestions to the user while typing. There are several modes of suggestions. The suggested text can be appended to the original text or it can be displayed in a drop-down list so that user can choose from different options.

## Auto Complete Source

The TextBoxExt control can be populated with a predefined list of items, which will assist the user while typing. Users can choose one item from the filtered list.

For illustration, let us create a textbox, which will populate a list of employees.

The Employee model looks as shown below:


{% highlight  %}
[C#] 



   public class Employee

    {

        public string Name { get; set; }



        public string Email { get; set; }

    }
{% endhighlight %}


Create a collection attribute,


{% highlight  %}
[C#]



     private List<Employee> employees;



     public List<Employee> Employees

     {

         get { return employees; }

         set { employees = value; }

     }

{% endhighlight %}

Populate the collection with items,


{% highlight  %}
[C#]



Employees = new List<Employee>();

Employees.Add(new Employee{Name = "Lucas", Email = "lucas@syncfusion.com"});

Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });

Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });
{% endhighlight %}


Bind the Employees collection to the AutoCompleteSource property of TextBoxExt.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

AutoCompleteSource="{Binding Employees}" />
{% endhighlight %}


At this point, the control is populated with the list of employees. But the Employee model contains two properties Name and Email so we should tell the control, by which property, it has to provide suggestions. In this case, let us make the control to provide suggestions based on Name.

SearchItemPath property specifies the property path by which the filtering has to be done.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}" />
{% endhighlight %}
							
![C:/Users/ApoorvahR/Desktop/4.png](Auto-Complete_images/Auto-Complete_img1.png)



> _Note: Default value of AutoCompleteMode property is None. So running the control without specifying this property will not show any suggestions. Detailed information about Auto Complete modes will be provided in next section._

## Auto Complete Mode

The suggestions can be displayed in several ways. TextBoxExt supports the following modes of auto complete,

1. None
2. Suggest
3. Append
4. SuggestAppend






The default value of AutoCompleteMode is None.

### Suggest

The filtered suggestions are displayed in a drop-down list.  Users can pick an item from the list.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/5.png](Auto-Complete_images/Auto-Complete_img2.png)



_Filtered suggestions displayed in drop-down list_



### Append

The text will be appended to the first matched item in the suggestions collection without opening the drop-down list.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

AutoCompleteMode="Append"

                            AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/6.png](Auto-Complete_images/Auto-Complete_img3.png)



_Append mode_

_Note: By default the text will be appended to first matched item. But still user can browse to other items through up and down keys from keyboard._

### SuggestAppend

The text will be appended to the first matched item in the suggestions collection, in addition to opening the drop-down list.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="SuggestAppend"

                            AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/7.png](Auto-Complete_images/Auto-Complete_img4.png)



_SuggestAppend mode_



### None

This option neither appends text nor opens the drop-down list of suggestions. 

## AutoComplete Item Template

The AutoCompleteItemTemplate helps to decorate the suggested item with visual elements. The following code block explains how to add an image to the drop-down list item.


{% highlight xml %}
[XAML]



  <editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            AutoCompleteMode="SuggestAppend"

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

![C:/Users/ApoorvahR/Desktop/8.png](Auto-Complete_images/Auto-Complete_img5.png)



_Drop down list with image_



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


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="None"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

 ![C:/Users/ApoorvahR/Desktop/9.png](Auto-Complete_images/Auto-Complete_img6.png)



_None case_

### StartsWith

The control returns all possible matches which start with the text typed by the user.

{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="StartsWith"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/10.png](Auto-Complete_images/Auto-Complete_img7.png)



_StartsWith case_



### StartsWithCaseSensitive

The control returns all possible matches which start with the text typed by the user which is culture and case sensitive.

{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="StartsWithCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>
{% endhighlight %}
![C:/Users/ApoorvahR/Desktop/11.png](Auto-Complete_images/Auto-Complete_img8.png)



_StartsWithCaseSensitive case_



### StartsWithOrdinal

The control returns all possible matches which start with the text typed by the user based on OrdinalIgnoreCase.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="StartsWithOrdinal"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>


{% endhighlight %}
![C:/Users/ApoorvahR/Desktop/12.png](Auto-Complete_images/Auto-Complete_img9.png)


_StartsWithOrdinal case_



### StartsWithOrdinalCaseSensitive

The control returns all possible matches which start with the text typed by the user by Ordinal which is case sensitive.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionMode="StartsWithOrdinalCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/13.png](Auto-Complete_images/Auto-Complete_img10.png)



_StartsWithOrdinalCaseSensitive case_




### Contains

The control return all possible matches which contains the text typed by the user.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="Contains"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>


{% endhighlight %}
![C:/Users/ApoorvahR/Desktop/14.png](Auto-Complete_images/Auto-Complete_img11.png)



_Contains case_



### ContainsCaseSensitive

The control return all possible matches which contains the text typed by the user which is culture and case sensitive.

{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="ContainsCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/15.png](Auto-Complete_images/Auto-Complete_img12.png)


_ContainsCaseSensitive case_



### ContainsOrdinal

The control return all possible matches which contains the text typed by the user based on OrdinalIgnoreCase.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="ContainsOrdinal"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/16.png](Auto-Complete_images/Auto-Complete_img13.png)



_ContainsOrdinal case_



### ContainsOrdinalCaseSensitive

The control return all possible matches which contains the text typed by the user based on Ordinal which is case sensitive.
{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="ContainsOrdinalCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/17.png](Auto-Complete_images/Auto-Complete_img14.png)



_ContainsOrdinalCaseSensitive_



### Equals

The control return all possible matches which equals the text typed by the user.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="Equals"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/18.png](Auto-Complete_images/Auto-Complete_img15.png)



_Equals case_

### EqualsCaseSensitive

The control return all possible matches which equals the text typed by the user which is culture and case sensitive.
{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="EqualsCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>


{% endhighlight %}
![C:/Users/ApoorvahR/Desktop/19.png](Auto-Complete_images/Auto-Complete_img16.png)



_EqualsCaseSensitive case_

### EqualsOrdinal

The control return all possible matches which equals the text typed by the user based on OrdinalIgnoreCase.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="EqualsOrdinal"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/20.png](Auto-Complete_images/Auto-Complete_img17.png)


_EqualsOrdinal case_

### EqualsOrdinalCaseSensitive

The control return all possible matches which equals the text typed by the user based on Ordinal which is case sensitive.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="EqualsOrdinalCaseSensitive"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/21.png](Auto-Complete_images/Auto-Complete_img18.png)



_EqualsOrdinalCaseSensitive case_



### Custom

The control return all possible matches based on the Filter property. Filter is of type SuggestionPredicate. In the MyFilter method, filtration is done by checking whether the collection contains the typed text


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt x:Name="autoComplete" HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionMode="Custom"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}


{% highlight  %}
[C#]    



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

{% endhighlight %}

{% highlight  %}
[C#]

autoComplete.Filter = MyFilter;
{% endhighlight %}


![C:/Users/ApoorvahR/Desktop/22.png](Auto-Complete_images/Auto-Complete_img19.png)



_Custom case_

_Note: Append mode always works only with StartsWith behavior. If the typed text is not the same as the start text of any items, it will not append anything even when the auto complete mode is set to Append or SuggestAppend._



### Ignore Case

This option allows the control to filter suggestions by ignoring the case. The default value is false.


{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            IgnoreCase="True"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/23.png](Auto-Complete_images/Auto-Complete_img20.png)



_Ignore Case_



### Minimum Prefix Length

The MinimumPrefixCharacters property allows the control to filter the typed text based on the number of characters.

{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

MinimumPrefixCharacters="2"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>
{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/24.png](Auto-Complete_images/Auto-Complete_img21.png)


_Minimum Prefix Length case_

### Popup Delay

PopupDelay specifies the delay after which the suggestion popup should open. 


{% highlight xml %}
[XAML]



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

{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionBoxPlacement="Top"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/25.png](Auto-Complete_images/Auto-Complete_img22.png)



_Drop down list opening at the top_



#### Bottom

The drop-down list will open at bottom of the control.
{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

                            SuggestionBoxPlacement="Bottom"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/26.png](Auto-Complete_images/Auto-Complete_img23.png)


_Drop down list opening at the bottom_



#### None

The drop-down list will not open.
{% highlight xml %}
[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            SearchItemPath="Name"

SuggestionBoxPlacement="None"

                            AutoCompleteMode="Suggest"

                            AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}
![C:/Users/ApoorvahR/Desktop/27.png](Auto-Complete_images/Auto-Complete_img24.png)


_No drop down list_



