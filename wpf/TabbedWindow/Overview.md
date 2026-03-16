---
layout: post
title: TabbedWindow — Overview | Syncfusion®
description: Learn here all about introduction of Syncfusion® WPF TabbedWindow control, its elements and more.
platform: WPF
control: TabbedWindow
documentation: ug
---

# WPF TabbedWindow Overview

The `TabbedWindow` provides a multi‑document (MDI‑style) experience inside a single WPF window. It combines a chromeless window shell (`SfChromelessWindow`) with a tab host (`SfTabControl`) so applications can open, switch and manage multiple documents or views in a single container.

## Key features

**Tabbed window shell** — Integrates `SfTabControl` into a chromeless window (`WindowType = Tabbed`) so the tab strip is visually part of the window chrome.

**Tab management** — Open, close and switch tabs quickly. Tabs are represented by `SfTabItem` and host arbitrary content (views, documents, dashboards).

**Drag & drop** — Reorder tabs within a tab strip by dragging headers.

**Tear‑off / detach** — Drag a tab off the strip to float it into a standalone `SfChromelessWindow`.

**Merge support** — Drop tabs onto another `SfTabControl` to merge; use the `PreviewMerge` event to accept or reject cross‑window merges.

**New‑tab flow** — Built‑in new‑tab button and `AddingNewTab` event to create tabs with default content or view models.

**Templating & styling** — Customize header templates, content templates, new‑tab button templates and tab item styles to match application design and Syncfusion themes.

**Accessibility & RTL** — Respect `FlowDirection` for RTL languages and expose automation properties for screen readers and keyboard navigation.
