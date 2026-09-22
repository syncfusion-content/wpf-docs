---
layout: post
title: Syncfusion® AI Coding Assistant Prompt Library | Syncfusion®
description: Explore the AI Coding Assistant Prompt Library to enhance WPF development productivity with code generation, configuration examples, and contextual guidance.
control: Syncfusion® AI Coding Assistant Prompt Library
platform: wpf
documentation: ug
---

# Prompt Library for Syncfusion® AI Coding Assistants Tools

Speed up your WPF projects using these ready-made prompts for popular Syncfusion components. Each prompt is short, easy to understand, and focused on real tasks—like quick setups, tweaks, and fixes.

## How to Use

These prompts can be used with the MCP server or agent skills to streamline your development workflows.

* Choose a prompt that fits your needs.
* Customize the prompt as needed before running it.
* Run the prompt using either of the following AI tools:
    - **Skills:** Skills can also run automatically based on the query, or can be called explicitly using the /syncfusion-wpf-datagrid skill.
    - **MCP Server:** Tool can start automatically based on the query, or can be invoked explicitly using #search_docs.
* Always review and test the generated code before adding it to the project.

## Component-Specific Prompts

### Grid

The Syncfusion WPF DataGrid provides fast, flexible tables for large datasets with rich built-in interactivity.

{% promptcards %}
{% promptcard Paging and Sorting %}
How to enable paging and sorting in the Syncfusion WPF DataGrid?
{% endpromptcard %}
{% promptcard Grouping and Filtering %}
Show me an example of grouping and filtering data in the Syncfusion WPF DataGrid.
{% endpromptcard %}
{% promptcard Editing with Column Types %}
How to configure in-place editing using numeric, text, date, checkbox, image, combo box, picker, and template editors in the DataGrid.
{% endpromptcard %}
{% promptcard Selection and Keyboard Navigation %}
Enable single and multiple row selection with programmatic selection APIs and Windows keyboard navigation.
{% endpromptcard %}
{% promptcard CRUD Operations %}
What’s the code to implement full CRUD operations in the Syncfusion WPF DataGrid?
{% endpromptcard %}
{% promptcard Export to PDF and Excel %}
How to export DataGrid content to PDF and Excel in Syncfusion WPF?
{% endpromptcard %}
{% promptcard Virtual Scrolling %}
How to configure virtual scrolling for large datasets in the DataGrid?
{% endpromptcard %}
{% promptcard Multicolumn Grid Setup %}
Create a multi-column DataGrid to display product details with sorting and filtering.
{% endpromptcard %}
{% promptcard Load control in a cell/column %}
How can I integrate or load a WPF control inside each cell or column of the Syncfusion WPF DataGrid?
{% endpromptcard %}
{% promptcard Advanced Grid Features %}
Show me a DataGrid with paging, sorting, grouping, filtering, and virtual scrolling.
{% endpromptcard %}
{% promptcard Troubleshooting Export %}
Why isn’t my DataGrid exporting to PDF or Excel correctly?
{% endpromptcard %}
{% promptcard Cell Editing %}
How to enable cell editing in the DataGrid?
{% endpromptcard %}
{% promptcard Dynamic Column Configuration %}
How can I add or display the predefined or multi columns in a drop-down in the DataGrid?
{% endpromptcard %}
{% promptcard Drag and Drop Support %}
How to enable row drag-and-drop in the Syncfusion WPF DataGrid?
{% endpromptcard %}
{% promptcard Styling and Conditional Formatting %}
Customize cell and header styles and apply conditional formatting based on data values.
{% endpromptcard %}
{% endpromptcards %}

### Chart

The Syncfusion WPF Chart suite offers versatile visualizations across many series types for insightful data exploration.

{% promptcards %}
{% promptcard Data Binding %}
How to bind data sources to a Syncfusion WPF Chart for real-time updates?
{% endpromptcard %}
{% promptcard Selection and Highlighting %}
How to enable selection and highlighting of data points in WPF Charts?
{% endpromptcard %}
{% promptcard Chart Types Overview %}
What chart types are available in Syncfusion WPF Charts, and how to configure them?
{% endpromptcard %}
{% promptcard Markers and Data Labels %}
How can I display markers and data labels on a line chart in WPF?
{% endpromptcard %}
{% promptcard Zooming and Panning %}
How to enable zooming and panning in WPF Charts for large datasets?
{% endpromptcard %}
{% promptcard Annotations %}
Add image and shape annotations to highlight specific data points in a chart.
{% endpromptcard %}
{% promptcard Export to Image or PDF %}
How to export a Syncfusion WPF Chart to PDF or image formats?
{% endpromptcard %}
{% promptcard Print Support %}
Enable print functionality for a Syncfusion WPF Chart.
{% endpromptcard %}
{% promptcard Tooltips and Trackball %}
Show interactive tooltips and a trackball with formatted labels and multiple series value display.
{% endpromptcard %}
{% promptcard Axes and Multiple Axes %}
Configure CategoryAxis, NumericalAxis, DateTimeAxis, and add a secondary Y-axis with series mapped to it.
{% endpromptcard %}
{% promptcard Legend and Title %}
Add chart title, subtitle, and a responsive legend (positioning, overflow modes) in a WPF chart.
{% endpromptcard %}
{% promptcard Series Types Quick Setup %}
Create a chart with Line, Spline, StepLine, Area, SplineArea, Column, Bar, Scatter, and Bubble series.
{% endpromptcard %}
{% promptcard Segment Color Mapping and Gradients %}
Apply segment color mapping and gradient fills based on Y-value ranges.
{% endpromptcard %}
{% promptcard Axis Customization %}
Configure axis intervals, labels format, inversed axis, axis crossing, and logarithmic axis.
{% endpromptcard %}
{% promptcard Data Labels and Smart Labels %}
Enable data labels with templates, alignment, and smart label collision avoidance for dense data.
{% endpromptcard %}
{% promptcard Gridlines and Chart Area Styling %}
Customize major/minor gridlines, tick lines, chart area background, and border.
{% endpromptcard %}
{% promptcard Animation Support %}
How to enable animations in WPF Charts to make visualization more engaging?
{% endpromptcard %}
{% promptcard Multiple Series Types %}
How to combine bar and line series in a single Syncfusion WPF Chart?
{% endpromptcard %}
{% promptcard Custom Markers and Labels %}
Show me how to customize chart markers and data label styles.
{% endpromptcard %}
{% endpromptcards %}

### Scheduler

The Syncfusion WPF Scheduler helps manage events, resources, and timelines with powerful views and customization.

{% promptcards %}
{% promptcard Views and Quick Switch %}
Configure Day, Week, Month, Timeline Day/Week/WorkWeek/Month views and add quick view switching.
{% endpromptcard %}
{% promptcard Appointment Mapping and Data Binding %}
How to bind custom appointment models using mapping (subject, notes, location, start time, end time) with MVVM.
{% endpromptcard %}
{% promptcard Recurring Events and Series Editing %}
Create recurring appointments (daily/weekly/monthly/yearly) and enable editing a single occurrence or the entire series.
{% endpromptcard %}
{% promptcard Time Zones %}
Show appointments in the WPF Scheduler control for specific time zones.
{% endpromptcard %}
{% promptcard Work Time, Work Days, and First Day of Week %}
How to set working hours, configure work days and customize the first day of week.
{% endpromptcard %}
{% promptcard Min/Max Date Navigation Limits %}
How to restrict navigation with MinimumDateTime and MaximumDateTime to keep users in a valid planning range.
{% endpromptcard %}
{% promptcard Special Time Regions (Blocking Intervals) %}
Define special time regions to block interaction (e.g., holidays/breaks) and highlight them across views.
{% endpromptcard %}
{% promptcard Blackout Dates for MonthView %}
Disable specific dates like weekends or holidays to prevent selection and interaction for month view.
{% endpromptcard %}
{% promptcard Drag-and-Drop %}
Enable drag to reschedule, resize to change duration for quick appointment updates.
{% endpromptcard %}
{% promptcard Resources and Grouping %}
Group by resources (rooms/people/teams) with color-coding and timeline views optimized for many resources.
{% endpromptcard %}
{% promptcard Load on Demand %}
Load appointments on demand with a loading indicator for large schedules.
{% endpromptcard %}
{% promptcard Reminders and Notifications Integration %}
Add reminder metadata to appointments and integrate with app notifications for alerts.
{% endpromptcard %}
{% promptcard Theming and Customization %}
How to style headers, cells, appointments, selection, and special regions; support Light/Dark themes.
{% endpromptcard %}
{% endpromptcards %}

### AI AssistView

The Syncfusion WPF AI AssistView provides a ready-made conversational UI for integrating LLMs with features like message list, input box, suggestions, attachments, and tool/action invocation.

{% promptcards %}
{% promptcard Messages %}
Bind AssistView to a message collection with system, user, and pre load conversation history.
{% endpromptcard %}
{% promptcard Streaming and Typing Indicator %}
Enable token streaming with a typing indicator and incremental message updates.
{% endpromptcard %}
{% promptcard Suggestions (Quick Prompts) %}
How to add clickable suggestion chips that insert predefined prompts into the input box.
{% endpromptcard %}
{% promptcard Markdown and Rich Rendering %}
How to render assistant responses with Markdown (headings, code blocks) and support inline images/emojis.
{% endpromptcard %}
{% promptcard Avatars and Message Templates %}
How to customize assistant avatars and use DataTemplate/DataTemplateSelector for message bubbles.
{% endpromptcard %}
{% promptcard Error Handling and Retries %}
How to handle provider errors with retry/cancel UI and graceful fallback messages.
{% endpromptcard %}
{% promptcard Theming and Styling %}
Apply custom themes for message bubbles, background, input bar, and suggestion chips (Light/Dark support).
{% endpromptcard %}
{% promptcard Command/Enter Behavior %}
Configure Enter to send and Shift+Enter for newline; support multiline input with character counter.
{% endpromptcard %}
{% promptcard Citations and References %}
Display citations/references returned by the model as hyper links under the message.
{% endpromptcard %}
{% endpromptcards %}

### Diagram

The Syncfusion WPF Diagram is a powerful, extensible library for visualizing, creating, and editing interactive diagrams.

{% promptcards %}
{% promptcard Data Source %}
Generate a layout using NodeViewModel as the data source instead of a business object class?
{% endpromptcard %}
{% promptcard Annotations %}
Add labels (annotations) to a node in the Diagram?
{% endpromptcard %}
{% promptcard Ports %}
Add connection points (ports) to Diagram elements?
{% endpromptcard %}
{% promptcard Gridlines %}
How to customize the appearance of gridlines?
{% endpromptcard %}
{% promptcard Snapping %}
Enable snapping in the Syncfusion WPF Diagram?
{% endpromptcard %}
{% promptcard Scrolling %}
How to restrict or enable scrolling only within the Diagram area?
{% endpromptcard %}
{% promptcard Serialization %}
How to serialize the Content and ContentTemplate properties of a node?
{% endpromptcard %}
{% promptcard Virtualization %}
Configure Diagram with UI virtualization for smooth scrolling on large objects.
{% endpromptcard %}
{% promptcard Commands %}
How to add a custom gesture command in the WPF Diagram?
{% endpromptcard %}
{% promptcard Automatic Layout %}
How can I create flowchart and organization layouts with the Diagram?
{% endpromptcard %}
{% promptcard Stencil: Custom Controls %}
How to use different user controls in the Stencil?
{% endpromptcard %}
{% promptcard Stencil: Add Symbols %}
How to add symbols to the Stencil?
{% endpromptcard %}
{% promptcard Print Support %}
How to enable the Print Properties option in the WPF Diagram print dialog?
{% endpromptcard %}
{% promptcard Export to PDF %}
How to export the Diagram as a PDF?
{% endpromptcard %}
{% endpromptcards %}

### Ribbon

The Syncfusion WPF Ribbon is a command bar that organizes an application’s tools into tabs and supports a Backstage view similar to Microsoft Office.

{% promptcards %}
{% promptcard Add Ribbon Items %}
Add RibbonTab, RibbonGroup, RibbonButton, RibbonDropDownButton, and RibbonComboBox in the WPF Ribbon?
{% endpromptcard %}
{% promptcard Application Menu / Backstage %}
How to add and customize the Backstage (application menu) with pages, navigation, and commands in the WPF Ribbon?
{% endpromptcard %}
{% promptcard Quick Access Toolbar (QAT) %}
Add, remove, and persist QAT items and position it above or below the Ribbon?
{% endpromptcard %}
{% promptcard ScreenTips %}
Create ScreenTips with headers, footers, images, and shortcuts for Ribbon items?
{% endpromptcard %}
{% promptcard KeyTips %}
How to enable and customize KeyTips for keyboard navigation in the Ribbon?
{% endpromptcard %}
{% promptcard Serialization %}
How to save and restore Ribbon state (selected tab, QAT items, recent files) to a file or user settings?
{% endpromptcard %}
{% promptcard Simplified Layout %}
Enable simplified layout and configure group resizing behavior in the Ribbon?
{% endpromptcard %}
{% promptcard Ribbon Merging %}
How to merge RibbonTab and RibbonBar from two different Ribbon controls in MDI applications?
{% endpromptcard %}
{% promptcard Contextual Tabs %}
Create contextual RibbonTab groups and show or hide them based on selection or app state?
{% endpromptcard %}
{% promptcard MVVM Commands %}
How to bind Ribbon items to ICommand using MVVM, including CanExecute and routed commands?
{% endpromptcard %}
{% promptcard Galleries %}
How to build Ribbon galleries with item templates, filtering, and selection change handling?
{% endpromptcard %}
{% promptcard Localization and RTL %}
How to localize Ribbon text and tooltips and enable right-to-left (RTL) layout?
{% endpromptcard %}
{% promptcard Theming %}
How to apply Office/Fluent themes and switch themes at runtime for the Ribbon?
{% endpromptcard %}
{% promptcard Group Resizing Policies %}
How to configure Ribbon group size definitions (Large, Medium, Small) and item collapsing for narrow widths?
{% endpromptcard %}
{% endpromptcards %}

### Docking Manager

The Syncfusion WPF Docking Manager provides a Visual Studio–like interface for creating dockable windows in your applications.

{% promptcards %}
{% promptcard Data Binding %}
How to add and manage child dock windows via data binding and MVVM in DockingManager?
{% endpromptcard %}
{% promptcard Dock Support %}
How to enable or disable docking globally or for specific panes in DockingManager?
{% endpromptcard %}
{% promptcard Float and Auto-Hide Programmatically %}
How to float, auto-hide, pin, or restore a docked pane via code?
{% endpromptcard %}
{% promptcard Tabbed Documents %}
How to create tabbed document windows and manage document groups?
{% endpromptcard %}
{% promptcard Prevent Close and Customize Header %}
How to prevent closing certain panes and customize header text, icons, and header buttons?
{% endpromptcard %}
{% promptcard Context Menu Customization %}
How to disable or customize the dock window/tab context menu?
{% endpromptcard %}
{% promptcard Events for State Changes %}
Show events that notify dock state changes (docked, floating, auto-hide, closed) and how to handle them?
{% endpromptcard %}
{% promptcard Serialization / Layout Persistence %}
How to save and restore DockingManager layout to a file/stream and manage versioned changes safely?
{% endpromptcard %}
{% promptcard Runtime Add/Remove Panes %}
How to dynamically add and remove dock panes at runtime and refresh the layout?
{% endpromptcard %}
{% promptcard Restrict Docking Targets %}
How to restrict where a pane can dock (left/right/top/bottom/tabbed) or disallow floating?
{% endpromptcard %}
{% promptcard Per-User Layouts %}
How to maintain separate layouts per user and switch between them at runtime?
{% endpromptcard %}
{% promptcard Performance and Memory %}
What are best practices to improve performance and avoid memory leaks when frequently adding/removing panes?
{% endpromptcard %}
{% promptcard Host Windows Forms Control %}
Host a Windows Forms control inside a dock pane using WindowsFormsHost?
{% endpromptcard %}
{% endpromptcards %}

### Calendar

The Syncfusion WPF Calendar supports flexible date selection, localization, and custom rendering.

{% promptcards %}
{% promptcard Date Range Selection %}
How to enable date range selection in the Syncfusion WPF Calendar?
{% endpromptcard %}
{% promptcard Globalization Support %}
Configure the Calendar to support multiple cultures and languages.
{% endpromptcard %}
{% promptcard Multi-Date Selection %}
Show me how to allow users to select multiple dates in the Calendar.
{% endpromptcard %}
{% promptcard Skip Months Feature %}
Enable skipping months in Calendar navigation for faster browsing.
{% endpromptcard %}
{% promptcard Show Other Month Days %}
How to show days from adjacent months in the current Calendar view?
{% endpromptcard %}
{% promptcard Custom Day Cell Format %}
Customize the day cell format in the Calendar to show short weekday names.
{% endpromptcard %}
{% promptcard Highlight Weekends %}
Highlight weekends in the Calendar with a different background color.
{% endpromptcard %}
{% promptcard Multi-Selection and Range %}
Enable both multi-date selection and range selection in the Calendar.
{% endpromptcard %}
{% promptcard Troubleshooting Date Range %}
Why isn’t my Calendar selecting the correct date range?
{% endpromptcard %}
{% promptcard Advanced Calendar Setup %}
Create a Calendar with date range, multi-selection, globalization, and weekend highlights.
{% endpromptcard %}
{% endpromptcards %}

## See also

* [Skills](https://help.syncfusion.com/wpf/skills)
* [MCP Server](https://help.syncfusion.com/wpf/mcp)