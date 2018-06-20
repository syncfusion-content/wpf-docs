---
layout: post
title: MaskType| SfMaskedEdit | Wpf | Syncfusion
description: masktype
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# MaskType

Each MaskType has different set of mask elements that are combined to form a mask expression. Based on the complexity and usage, mask types are classified as,

1. Simple
2. Regular
3. Reg-Ex

## Simple

Expressions that are generated with very simple mask elements come under this group. This is mainly used for fixed length inputs. For example: Phone number.

Mask elements in this mask type are as follows:

### Simple mask elements

<table>
<tr>
<th>
Elements</th><th>
Description</th></tr>
<tr>
<td>
0</td><td>
Digit, required. This element accepts any single digit between 0 and 9.</td></tr>
<tr>
<td>
9</td><td>
Digit or space, optional.</td></tr>
<tr>
<td>
#</td><td>
Digit or space, optional. Plus (+) and minus (-) signs are allowed.</td></tr>
<tr>
<td>
L</td><td>
Letter, required. Restricts input to the ASCII letters a-z and A-Z. This mask element is equivalent to [a-z A-Z] in regular expressions.</td></tr>
<tr>
<td>
?</td><td>
Letter, optional. Restricts input to the ASCII letters a-z and A-Z. This mask element is equivalent to [a-z A-Z]? in regular expressions.</td></tr>
<tr>
<td>
C</td><td>
Character, optional. </td></tr>
<tr>
<td>
A</td><td>
Alphanumeric, required.</td></tr>
<tr>
<td>
<</td><td>
Shift down. Converts all the characters that follow to lowercase.</td></tr>
<tr>
<td> > </td><td>
Shift up. Converts all the characters that follow to uppercase.</td></tr>
</table>

## Regular

Expressions that are generated with slightly complex mask elements are under this group, preferable for variable length inputs and input in range. For example: Hexadecimal values [0-9A-C].

### Regular mask elements

<table>
<tr>
<th>
Elements</th><th>
Description</th></tr>
<tr>
<td>
\w</td><td>
Accepts any alphabet.</td></tr>
<tr>
<td>
\d</td><td>
Accepts any digit.</td></tr>
<tr>
<td>
[0-9A-Z]</td><td>
Accepts any digit between 0-9 and character between A-Z.</td></tr>
<tr>
<td>
{n}</td><td>
Accepts the input for n number of times.</td></tr>
<tr>
<td>
{n,m}</td><td>
Accepts the input for n minimum number of times and m maximum number of times.</td></tr>
<tr>
<td>
?</td><td>
Optional input.</td></tr>
<tr>
<td>
+</td><td>
Accepts the input for one or more times.</td></tr>
<tr>
<td>
*</td><td>
Accepts the input for zero or more times.</td></tr>
</table>


## RegEx

Very complex regular expressions come under this category. It accepts input of variable length and allows to use OR expressions.  

### RegEx mask elements

<table>
<tr>
<th>
Elements</th><th>
Description</th></tr>
<tr>
<td>
abc|def</td><td>
Accepts any one input that matches.</td></tr>
<tr>
<td>
(a|b)+</td><td>
Accepts the matching input one or more times.</td></tr>
</table>

For example: The following code example shows the validation for E-mail using Regex Elements.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit x:Name="sfMaskedEdit" MaskType="RegEx" Mask="[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}" Value="someone@example.com" />

{% endhighlight %}

{% endtabs %}


