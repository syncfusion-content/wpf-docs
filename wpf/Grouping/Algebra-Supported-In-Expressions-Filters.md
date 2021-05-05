---
layout: post
title: Algebra Supported In Expressions Filters in WPF Grouping control | Syncfusion
description: Learn about Algebra Supported In Expressions Filters support in Syncfusion WPF Grouping control and more.
platform: WindowsForms
control: Grouping
documentation: ug
---

# Algebra Supported In Expressions Filters in WPF Grouping

Expressions can be any well-formed algebraic combination of the following: 

* Property (column) names enclosed with square brackets `[]` 
* Numerical constants and literals 
* Algebraic and logical operators

The computations are performed as listed below, with level one operations done first. 

* *, /: multiplication, division 
* +, -: addition, subtraction 
* <, >, =, <=, >=, <>: less than, greater than, equal, less than or equal, greater than or equal, not equal
* match, like, in, between 
* or, and, or

N>
N> 1. Alpha constants used with match and like should be enclosed in apostrophes (').
N> 2. Logical operators return "1", if the logical expression is True and return "0", if the logical expression is False.



Given below is some more information on special logical operators:

* Match-Returns 1 if there is any occurrence of the right-hand argument in the left-hand argument. 



### Example

[CompanyName] match 'RTR' returns 0 for any record whose CompanyName field does not contain RTR anywhere in the string. 

* Like-Checks if the field starts exactly as specified in the right-hand argument. 



### Example 

[CompanyName] like 'RTR' returns 1 for any record whose CompanyName field is exactly 'RTR'. You can use an asterisk as a wildcard. [CompanyName] like 'RTR*' returns 1 for any record whose CompanyName field starts with 'RTR'. [CompanyName] like '*RTR' returns 1 for any record whose CompanyName field ends with 'RTR'. 

* In-Checks if the field value is any of the values listed in the right-hand operand. The collection of items used as the right-hand should be separated by commas and enclosed within braces({ }). 



### Example 

[code] in {1,10,21}, returns 1 for any record whose code field contains 1 or 10 or 21. [CompanyName] in {RTR,MAS} returns 1 for any record whose CompanyName field is RTR or MAS. 



 Note that spaces that are significant in the list, i.e. {RTR,MAS} is not the same as {RTR, MAS}. 



* Between-Checks if a date field value between the two values is listed in the right-hand operand. 



### Example

[date] between {2/25/2004, 3/2/2004} returns 1 for any record whose date field is greater than or equal to 2/25/2004 and less than 3/2/2004. To represent the current date, use the token TODAY. To represent DateTime.MinValue, leave the first argument empty. To represent DateTime.MaxValue, leave the second argument empty. 



## Custom Functions

Essential Grouping lets you add custom functions to your code that can then be used in expressions. 

Following are the limitations on the use of custom functions: 

* You cannot use custom functions in algebraic expressions. 
* They must be used stand-alone in a simple expression that consists of only the function name and its argument list. 
* The argument list can be any number of arguments separated by a delimiter. 
