---
layout: post
title: Keyboard Navigation in WPF PropertyGrid control | Syncfusion
description: This section explains about how the keyboard navigation works between the property items of PropertyGrid
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Keyboard Navigation

## Keyboard Navigation between property items

The following table explains how the navigation performed between properties,

<table>
<th> S.No </th>
<th> Key </th>
<th> Description </th>
<tr>
<td>1</td>
<td>Up</td>
<td>Selection will be moved from current property to previous property.</td>
</tr>
<tr>
<td>2</td>
<td>Down</td>
<td>Selection will be moved from current property to next property.</td>
</tr>
<tr>
<td>3</td>
<td>Home</td>
<td>Selection will be moved from current property to first property of the PropertyGrid.</td>
</tr>
<tr>
<td>4</td>
<td>End</td>
<td>Selection will be moved from current property to last property of the PropertyGrid.</td>
</tr>
<tr>
<td>5</td>
<td>Left</td>
<td>Selection will be moved from current property to previous property. When the property {{'**EnableGrouping**'| markdownify }} is 'true' and the Header of the Category group is selected, and the group is expanded, then the Category group will be collapsed, and collapsed category group header remains selected.</td>
</tr>
<tr>
<td>6</td>
<td>Right</td>
<td>Selection will be moved from current property to next property. When the property {{'**EnableGrouping**'| markdownify }} is true and the Header of the Category group is selected and the group is not expanded, then the Category group will be expanded, and expanded category group header remains selected.</td>
</tr>
<tr>
<td>7</td>
<td>Tab</td>
<td>When the PropertyName field is focused then the focus will be moved to value field and for next {{'**Tab**'| markdownify }} key press, focus will move to next property Name field from current property Value field.
<br/> 
<br/>
<img src="KeyNavigation-Images/Tab-Key-Navigation.png" alt="Explaining Name and Value field"/>
<br/>
<br/>
</td>
</tr>
<tr>
<td>8</td>
<td>Esc</td>
<td>If the property’s value field is focused, then the focus has been moved to property’s name field.</td>
</tr>
<table>


## Handling focus of the editors

By default property grid will handle the keyboard navigation, so pressing keydown(Up and Down) will move the focus to next/previous editor from current editor. For all built-in editors, moving focus to next editor will be handled by PropertyGrid. To achieve this focus handling behavior in custom editors, that editors need to be overrides the `ShouldPropertyGridTryToHandleKeyDown` method which the editors has inherited from `BaseTypeEditor` instead of `ITypeEditor`.

If the method `ShouldPropertyGridTryToHandleKeyDown` returns true, the proeprty grid control should be allowed to handle the key down events based on the key, and the editor will handles the key down event for `false` value.

{% tabs %}
{% highlight C# %}

public class PasswordEditor : IBaseTypeEditor
    {
        public override void Attach(PropertyViewItem property, PropertyItem info)
        {
            if(info.CanWrite)
            {
                passwordBox.IsEnabled = true;
            }
            else
            {
                passwordBox.IsEnabled = false;
            }
            passwordBox.Password = info.Value.ToString();
        }

        PasswordBox passwordBox;
        public override object Create(PropertyInfo propertyInfo)
        {
            passwordBox = new PasswordBox(); 
            return passwordBox;
        }

        public override void Detach(PropertyViewItem property)
        {
            passwordBox = null;
        }

        /// <summary>
        /// Here, the property grid should not handle the focus of the editor which means, while doing key navigation the next focuable editor will not be focused. And the PasswordEditor will have the focus and handles the key down event.
        /// </summary>
        public override bool ShouldPropertyGridTryToHandleKeyDown(Key key)
        {
            return false;
        }
    }

{% endhighlight %}
{% endtabs %} 


