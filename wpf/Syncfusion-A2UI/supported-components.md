---
layout: post
title: Supported Syncfusion® A2UI Components for WPF | Syncfusion®
description: Reference guide to all Syncfusion® A2UI for WPF adapters, grouped by category with A2UI catalog IDs and brief descriptions.
control: A2UI Supported Components
platform: wpf
documentation: ug
---

# Supported Syncfusion® A2UI Components for WPF

The Syncfusion® A2UI for WPF package includes **48 Syncfusion® WPF adapters** and **18 A2UI primitives** in one A2UI v0.9 catalog.

An agent can send these adapters in `createSurface` or `updateComponents` messages. `A2uiSurface` renders them through `SurfaceHost`. Use the exact adapter ID from this page in the payload's `component` property. Supported properties and events vary by adapter.

See [Getting Started](./getting-started) to register the catalog and render a surface. The Composer sample shows how to author and preview A2UI messages.

## Data and collections

| Component ID | Description |
| --- | --- |
| `SyncfusionDataGrid` | Data grid for tabular rows, sorting, filtering, grouping, editing, and selection. |
| `SyncfusionPropertyGrid` | Property grid for inspecting and editing the properties of a selected object. |
| `SyncfusionTreeView` | Hierarchical data with expansion, selection, and drag-and-drop. |
| `SyncfusionAccordion` | Collapsible accordion container for grouped content. |
| `SyncfusionGantt` | Gantt chart for project tasks, dependencies, and timelines. |
| `SyncfusionKanban` | Kanban board for card-based workflow visualization. |

## Charts

| Component ID | Description |
| --- | --- |
| `SyncfusionCartesianChart` | Cartesian chart with line, column, bar, area, scatter, and candlestick series. |
| `SyncfusionChart3D` | 3D chart with column, bar, pie, doughnut, and surface series. |
| `SyncfusionSunburstChart` | Sunburst chart for hierarchical proportional data. |
| `SyncfusionSmithChart` | Smith chart for transmission line impedance visualization. |
| `SyncfusionBulletGraph` | Bullet graph for qualitative range bars and target markers. |
| `SyncfusionHeatMap` | Heatmap for matrix or calendar data visualization. |

## Inputs and editors

| Component ID | Description |
| --- | --- |
| `SyncfusionButton` | Button with styling, icon support, and action dispatch. |
| `SyncfusionTextBoxExt` | Single-line text input with watermark, validation, and formatting. |
| `SyncfusionMaskedEdit` | Input constrained by a mask pattern. |
| `SyncfusionCurrencyTextBox` | Currency-formatted numeric input. |
| `SyncfusionIntegerTextBox` | Integer-formatted numeric input. |
| `SyncfusionDomainUpDown` | Spin-input with a configurable domain of values. |
| `SyncfusionDateTimeEdit` | Date and time editor with calendar drop-down. |
| `SyncfusionComboBox` | Searchable single-selection input with editable text support. |
| `SyncfusionDropDownButtonAdv` | Drop-down button that hosts a popup of actions. |
| `SyncfusionSplitButton` | Button with a secondary drop-down for related actions. |
| `SyncfusionColorPickerPalette` | Color selection control with palette support. |
| `SyncfusionRating` | Symbol or star rating input with read-only support. |
| `SyncfusionRichTextEditor` | Rich text editing surface with formatting toolbar. |
| `SyncfusionSyntaxEditor` | Code editor with syntax highlighting and IntelliSense-style features. |
| `SyncfusionImageEditor` | Image editing surface with crop, rotate, and annotate. |

## Calendar and scheduling

| Component ID | Description |
| --- | --- |
| `SyncfusionCalendar` | Calendar view for date selection. |
| `SyncfusionScheduler` | Day, Week, Month, Timeline, and Agenda views. |

## Layout and navigation

| Component ID | Description |
| --- | --- |
| `SyncfusionCardView` | Card with content and visual styling. |
| `SyncfusionTabControlExt` | Tabbed content layout. |
| `SyncfusionTabNavigation` | Tab navigation control for wizard-style flows. |
| `SyncfusionToolBarAdv` | Toolbar containing configured action items. |
| `SyncfusionMenu` | Menu containing hierarchical menu items. |
| `SyncfusionRibbon` | Ribbon with tabs, groups, and back-stage views. |
| `SyncfusionDocking` | Dock, float, auto-hide, and tab-dock child panels. |
| `SyncfusionNavigationDrawer` | Navigation drawer with content and drawer states. |
| `SyncfusionNavigationPane` | Navigation pane with grouped links. |
| `SyncfusionRadialMenu` | Radial menu with circular item layout. |
| `SyncfusionRadialSlider` | Radial slider with circular track. |
| `SyncfusionTaskBar` | Grouped, expandable task list. |
| `SyncfusionSfTreeNavigator` | Tree-style navigation control. |

## Display and feedback

| Component ID | Description |
| --- | --- |
| `SyncfusionBusyIndicator` | Busy or loading indicator. |
| `SyncfusionAvatarView` | Avatar with initials, image, shape, and size options. |
| `SyncfusionCircularProgressBar` | Circular determinate or indeterminate progress. |
| `SyncfusionStepProgressBar` | Progress across ordered steps. |

## Maps, viewers, and document

| Component ID | Description |
| --- | --- |
| `SyncfusionMap` | Geographic map with shape data, markers, bubbles, labels, and legends. |
| `SyncfusionTreeMap` | Hierarchical treemap for quantitative data. |
| `SyncfusionDiagram` | Diagram surface for nodes, connectors, and layouts. |
| `SyncfusionPdfViewer` | PDF viewing surface with page navigation. |
| `SyncfusionMarkdownViewer` | Markdown rendering surface. |

## AI and shell

| Component ID | Description |
| --- | --- |
| `SyncfusionAiAssistView` | Conversational AI assist view with prompts, responses, and suggestions. |
| `SyncfusionChromelessWindow` | Chromeless window shell for modern-style desktop surfaces. |

## A2UI primitives

The combined catalog also includes these 18 renderer-independent primitives: `Text`, `Image`, `Icon`, `Video`, `AudioPlayer`, `Row`, `Column`, `List`, `Card`, `Tabs`, `Modal`, `Divider`, `Button`, `TextField`, `CheckBox`, `ChoicePicker`, `Slider`, and `DateTimeInput`.

The WPF assembly ships real visuals for `Text`, `Button`, `Row`, and `Column`. Other primitives fall back to typed placeholders that participate in layout and surface their `label`/`value`/`text` props. They can be composed with Syncfusion® adapters in the same surface. Use a unique component `id` for every component instance.

The combined catalog also includes an extras-catalog set of richer primitives (rendered through `ExtrasWpfCatalogBuilder`): `ProgressBar`, `Alert`, `Spinner`, `Avatar`, and `Tooltip`. These are available alongside the 18 basic primitives and the Syncfusion adapters.

## See also

- [Overview](./overview)
- [Getting Started](./getting-started)
- [A2UI v0.9 protocol](https://a2ui.org/specification/v0.9-a2ui/)
