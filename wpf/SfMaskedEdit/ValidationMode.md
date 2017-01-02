---
layout: post
title: ValidationMode| SfMaskedEdit | Wpf | Syncfusion
description: validationmode
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# ValidationMode

Input validation happens based on the value of the ValidationMode property. The enum values of this property are 

      * LostFocus
      * KeyPress

When the ValidationMode is KeyPress, the validation is raised for each key press. For LostFocus, the validation take place when the control get lost its focus. 

## HasError

This read only property is used to check whether the validation succeeds or not. It returns true once validation succeeds or else set to false.  

