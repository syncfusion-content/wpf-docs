---
layout: post
title: Section 508 Compliance for Syncfusion Essential Studio WPF products
description: Learn here about Section 508 Compliance for Syncfusion Essential Studio WPF products, its elements and more.
platform: WPF
control: Section 508 Compliance
 documentation: ug
---

# Section 508 Compliance - Voluntary Product Accessibility Template

The following Voluntary Product Accessibility information refers to Syncfusion Essential Studio for WPF.

<table>
<tr>
<th>
CRITERIA<br/><br/></th><th>
SUPPORTING FEATURES<br/><br/></th></tr>
<tr>
<td>
Section 1194.21 Software applications and operating systems.<br/><br/></td><td>
Please refer to the Subpart B.<br/><br/></td></tr>
<tr>
<td>
Section 1194.22 Web-based Intranet and Internet information and applications.<br/><br/></td><td>
Not Applicable.<br/><br/></td></tr>
<tr>
<td>
Section 1194.23 Telecommunications products.<br/><br/></td><td>
Not Applicable.<br/><br/></td></tr>
<tr>
<td>
Section 1194.24 Video and multimedia products.<br/><br/></td><td>
Not Applicable.<br/><br/></td></tr>
<tr>
<td>
Section 1194.25 Self-contained closed products.<br/><br/></td><td>
Not Applicable.<br/><br/></td></tr>
<tr>
<td>
Section 1194.26 Desktop and portable computers.<br/><br/></td><td>
Not Applicable.<br/><br/></td></tr>
<tr>
<td>
Section 1194.31 Functional performance criteria.<br/><br/></td><td>
Please refer to the Subpart C.<br/><br/></td></tr>
<tr>
<td>
Section 1194.41 Information, documentation, and support.<br/><br/></td><td>
Please refer to the Subpart D.<br/><br/></td></tr>
</table>

## Subpart B – Technical Standards Section 1194.21 

Section 1194.21 Software Applications and Operating Systems - Detail Voluntary Product Accessibility Template


<table>
<tr>
<th style="width:50%">
CRITERIA<br/><br/></th><th style="width:10%">
SUPPORTING FEATURES<br/><br/></th><th style="width:40%">
EXPLANATIONS<br/><br/></th></tr>
<tr>
<td>
(a) When software is designed to run on a system that has a keyboard, product functions shall be executable from a keyboard, where the function itself or the result of performing a function can be discerned textually.<br/><br/></td><td>
Supported with minor exceptions.<br/><br/></td><td>
Essential Diagram WPF provides keyboard support for most of the functions. <br/><br/>All other products controls that accept focus provide keyboard support. <br/><br/></td></tr>
<tr>
<td>
(b) Applications shall not disrupt or disable activated features of other products identified as accessibility features, where those features are developed and documented according to industry standards. Applications also shall not disrupt or disable activated features of any operating system that is identified as accessibility feature where the application programming interface for those accessibility features has been documented by the manufacturer of the operating system and is available to the product developer.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
All Essential Studio for WPF controls do not disable any accessibility features of other products.<br/><br/>Application developers using the controls should take care to preserve this.<br/><br/></td></tr>
<tr>
<td>
(c) A well-defined on-screen indication of the current focus shall be provided to move among interactive interface elements as the input focus changes. The focus shall be programmatically exposed so that Assistive Technology can track focus and focus changes.<br/><br/></td><td>
Supported with minor exceptions<br/><br/></td><td>
Essential Tools: Supported with minor exceptions. Controls provide a well-defined live indication of the current focus that moves among interactive interface elements as the input focus changes with minor exceptions such as Docking Manager, Ribbon.<br/><br/>Essential Chart: Fully Supported.<br/><br/>Essential Diagram: Fully Supported. Also provides hover styles and selection styles that highlight the position of the focus.<br/><br/>Essential Schedule: Fully Supported.<br/><br/>Essential Edit: Fully Supported.<br/><br/></td></tr>
<tr>
<td>
(d) Sufficient information about user interface element including identity, operation and state of the element shall be available to Assistive Technology. When an image represents a program element, the information conveyed by the image must also be available in text.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
Essential Tools: Fully supported. Controls provide enough information regarding the user interface elements and program elements, which can be used in Assistive technologies.<br/><br/>Essential Chart: Not Applicable. <br/><br/>Essential Diagram: Fully supported. Control provides sufficient information available in text about user interface elements and program elements represented by images, in virtually all cases. <br/><br/>Essential Gauge: Fully supported. Control provides enough information regarding the user interface elements and program elements, which can be used in Assistive technologies.<br/><br/>Essential Edit: Not Applicable.<br/><br/></td></tr>
<tr>
<td>
(e) When bitmap images are used to identify controls, status indicators, or other programmatic elements, the meaning assigned to those images shall be consistent throughout an application's performance.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
Essential Tools: Not applicable.<br/><br/>Essential Chart: Not applicable.<br/><br/>Essential Diagram: Fully supported. Control provides functionality that complies with these criteria. The cursor changes according to the operation being performed and it is consistent throughout the program.<br/><br/>Essential Gauge: Not applicable.<br/><br/>Essential Edit: Not applicable.<br/><br/></td></tr>
<tr>
<td>
(f) Textual information shall be provided through operating system functions for displaying text. The minimum information that shall be made available is text content, text input caret location and text attributes.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
Essential Diagram: Fully Supported. Control provides functionality that complies with these criteria. Text information is usually provided using the operating system only.<br/><br/>Essential Tools: Not applicable.<br/><br/>Essential Chart: Not applicable.<br/><br/>Essential Schedule: Not applicable.<br/><br/>Essential Edit: Not applicable.<br/><br/></td></tr>
<tr>
<td>
(g) Applications shall not override user selected contrast, color selections and other individual display attributes.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
All Essential Studio for WPF controls provide functionality that conforms to these criteria.<br/><br/><br/><br/></td></tr>
<tr>
<td>
(h) When animation is displayed, the information shall be displayable in at least one non-animated presentation mode at the option of the user.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
All Essential Studio for WPF controls provide functionality that conforms to these criteria.<br/><br/>Essential Diagram: The nodes can contain animations if desired and also any other content can be used.<br/><br/></td></tr>
<tr>
<td>
(i) Color coding shall not be used as the only means of conveying information, indicating an action, prompting a response or distinguishing visual element.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
All Essential Studio for WPF controls provide functionality that conforms to these criteria.<br/><br/></td></tr>
<tr>
<td>
(j) When a product permits a user to adjust color and contrast settings, a variety of color selections capable of producing a range of contrast levels shall be provided.<br/><br/></td><td>
Supported with minor exceptions<br/><br/></td><td>
Essential Diagram: Supported with minor exceptions. Control provides functionality that allows setting colors for almost all the elements by providing a large range of colors to choose from.<br/><br/>Other products: Fully supported.<br/><br/></td></tr>
<tr>
<td>
(k) Software shall not use flashing or blinking text, objects, or other elements having a flash or blink frequency greater than 2 Hz and lower than 55 Hz.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
All Essential Studio for WPF controls provide functionality that conforms to these criteria.<br/><br/></td></tr>
<tr>
<td>
(l) When electronic forms are used, the form shall allow people using Assistive Technology to access the information, field elements, and functionality required for completion and submission of the form, including all directions and cues.<br/><br/></td><td>
Not Applicable<br/><br/></td><td>
This criterion does not apply to Essential Studio for WPF controls.<br/><br/></td></tr>
</table>

## Subpart C - Section 1194.31 Functional Performance Criteria

<table>
<tr>
<th style="width:50%">
CRITERIA<br/><br/></th><th style="width:10%">
SUPPORTING FEATURES<br/><br/></th><th style="width:40%">
REMARKS AND EXPLANATIONS<br/><br/></th></tr>
<tr>
<td>
(a) At least one mode of operation and information retrieval that does not require user vision shall be provided or support for Assistive Technology used by people who are blind or visually impaired shall be provided.<br/><br/></td><td>
Partially Supported.<br/><br/></td><td>
Essential Tools: Supported in the following WPF Controls - Supported for TabControlExt, Docking Manager related controls. Not supported in the other Essential Studio for WPF controls.<br/><br/></td></tr>
<tr>
<td>
(b) At least one mode of operation and information retrieval that does not require visual acuity greater than 20/70 shall be provided in audio and enlarged print output working together or independently, or support for Assistive Technology used by people who are visually impaired shall be provided.<br/><br/></td><td>
Not Applicable<br/><br/></td><td>
This criterion does not apply to Essential Studio for WPF controls.<br/><br/></td></tr>
<tr>
<td>
(c) At least one mode of operation and information retrieval that does not require user-hearing shall be provided or support for Assistive Technology used by people who are deaf or hard of hearing shall be provided.<br/><br/></td><td>
Not Applicable.<br/><br/></td><td>
This criterion does not apply to Essential Studio for WPF controls.<br/><br/></td></tr>
<tr>
<td>
(d) Where audio information is important for the use of a product, at least one mode of operation and information retrieval shall be provided in an enhanced auditory fashion or support for assistive hearing devices shall be provided.<br/><br/></td><td>
Not Applicable<br/><br/></td><td>
This criterion does not apply to Essential Studio for WPF controls.<br/><br/></td></tr>
<tr>
<td>
(e) At least one mode of operation and information retrieval that does not require user-speech shall be provided or support for Assistive Technology used by people with disabilities shall be provided.<br/><br/></td><td>
Not Applicable.<br/><br/></td><td>
This criterion does not apply to Essential Studio for WPF controls.<br/><br/></td></tr>
<tr>
<td>
(f) At least one mode of operation and information retrieval that does not require fine motor control or simultaneous actions and that is operable with limited reach and strength shall be provided.<br/><br/></td><td>
Fully Supported<br/><br/></td><td>
Essential Studio for WPF controls provide functionality that conforms to these criteria.<br/><br/><br/><br/></td></tr>
</table>

## Subpart D - Section 1194.41 Information, documentation, and support

<table>
<tr>
<th style="width:50%">
Criteria<br/><br/></th><th style="width:10%">
Supporting Features<br/><br/></th><th style="width:40%">
Remarks and explanations<br/><br/></th></tr>
<tr>
<td>
Section 1194.41 (a) Product Support Documentation provided to end-users shall be made available in alternate formats upon request, at no additional charge.<br/><br/></td><td>
Supported.<br/><br/></td><td>
Online <a href="http://help.syncfusion.com">Documentation</a> is available.<br/><br/></td></tr>
<tr>
<td>
Section 1194.41 (b) Accessibility and Compatibility Features. End-users shall have access to a description of the accessibility and compatibility features of products in alternate formats or alternate methods upon request, at no additional charge.<br/><br/><br/><br/></td><td>
Supported.<br/><br/></td><td>
Essential Studio WPF controls are accessible<br/><br/></td></tr>
<tr>
<td>
1194.41 (c) Support Services for products shall accommodate the communication needs of end-users with disabilities.<br/><br/><br/><br/></td><td>
Supported.<br/><br/></td><td>
Online support <a href="https://www.syncfusion.com/support/directtrac/incidents">Incidents</a> and <a href="https://www.syncfusion.com/support/directtrac/forums">Forums</a> are available.<br/><br/></td></tr>
</table>
Syncfusion does not promise that the information provided in this document will be error-free, or that any errors will be corrected, or that your use of the information will provide specific results. The document and its content are delivered on an “as-is” basis. All information provided is subject to change without notice. Syncfusion disclaims all warranties, express or implied, including any warranties of accuracy, non-infringement, merchantability and fitness for a particular purpose.

