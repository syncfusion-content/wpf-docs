---
layout: post
title: About WPF Currency TextBox control | Syncfusion®
description: Learn here all about introduction of Syncfusion® WPF Currency TextBox control, its elements and more.
platform: wpf
control: CurrencyTextBox
documentation: ug
---

# WPF Currency TextBox Overview
The `CurrencyTextBox` is a specialized input control designed to accept, format, and display numeric values as currency in WPF applications. It enforces numeric input, formats numbers according to currency conventions, and exposes a concise API for common scenarios such as data binding, range validation, culture-aware formatting, and UI-driven value adjustment. The control is intended for forms, financial entry screens, reporting dialogs, dashboards, and any UI that requires reliable currency input and presentation.

## Control structure

The `CurrencyTextBox` combines a text-editing area with a number-formatting layer and optional adorner for visual feedback. Typical visual elements include a watermark (placeholder text) when the control is empty, the formatted currency text, and an optional range adorner that can act like a progress indicator based on `MinValue`/`MaxValue`.

![WPF Currency TextBox](getting-started_images/wpf-currency-textbox-control-structure.png)

![WPF Currency TextBox with Watermark Text](getting-started_images/wpf-currency-textbox-watermark.png)

## Typical usage scenarios

- Data-entry forms where users input monetary values (invoices, purchase orders, budgets).
- Financial dashboards that present editable currency fields with immediate formatting.
- Localized applications that must display currency values according to the user's culture and regional settings.
- UI components that need numeric constraints, e.g., limits, step increments, or visual progress indication for values within a range.

## Key capabilities

- Value enforcement and parsing: accepts only decimal-compatible characters and exposes the current numeric value through the `Value` property.
- Formatting and culture support: formats the displayed value as currency using either a `NumberFormatInfo` instance or the `Culture` property; supports dedicated formatting properties such as `CurrencySymbol`, `CurrencyDecimalDigits`, and `CurrencyGroupSeparator`. See details in [Culture and Formatting](Culture-and-Number-Formats.md).
- Range and validation: allows `MinValue` and `MaxValue` limits and configurable validation timing (`OnKeyPress` or `OnLostFocus`). Advanced options control behavior when entered digits exceed the allowed limits. See [Restriction or Validation](Restriction-or-Validation.md) for full guidance.
- Range adorner: optionally renders a colored fill inside the control to indicate a value proportion within the configured range. This is useful for quick visual feedback and is documented in [Range Adorner](Range-Adorner.md).
- Incrementing/scrolling: supports keyboard arrow keys and mouse wheel increments with a configurable `ScrollInterval` and circular scrolling options.
- Data binding and notifications: supports two‑way binding on the `Value` property and exposes value-change notifications so view models can react immediately to user edits.
- Accessibility and read-only mode: supports `IsReadOnly` and related caret behavior to present values without allowing edits while keeping selection and focusable behavior as needed.

## Integration and quick start

To add a `CurrencyTextBox` to your view and get started quickly, see the step-by-step instructions in [Getting Started](Getting-Started.md). That page shows the required assembly reference, XAML and C# examples, and the preferred `Value`-based approach for setting and binding currency data.

## Behavior and developer notes

- Prefer the `Value` property rather than `Text` when reading or setting the control programmatically; `Value` always represents the parsed numeric value.
- When both `NumberFormat` and `Culture` are specified, `NumberFormat` takes precedence for display formatting.
- `CurrencyDecimalDigits`, `MinimumCurrencyDecimalDigits`, and `MaximumCurrencyDecimalDigits` control decimal precision and interact according to explicit precedence rules documented in the formatting guide.

## Theming, styling and extensibility

The `CurrencyTextBox` supports built-in visual themes and can be styled using standard WPF templates and brushes. Visual states for positive, negative and zero values can be customized to make value meaning immediately perceptible. For examples and theming notes see the related Getting Started and Culture/Formatting documentation.
