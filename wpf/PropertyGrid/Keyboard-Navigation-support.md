---
layout: post
title: Keyboard Navigation in WPF PropertyGrid control | Syncfusion
description: This section explains about how the keyboard navigation works between the property items of PropertyGrid
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Keyboard Navigation between property items

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
