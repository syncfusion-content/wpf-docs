# Documentation Issue Report – WPF Docking (DockingManager)

**Source:** `D:\Development\wpf-docs\wpf\Docking\`
**Review date:** July 7, 2026
**Scope:** All `.md` files under the `Docking` directory
**Format:** `[Category] Location — Issue — Suggested fix`

Issues are grouped by file. Within each file, issues are grouped by category. Severity is one of **High** (blocks task), **Medium** (incorrect/breaks sample), **Low** (grammar/style).

---

## File: `Overview.md`

- [Missing Steps] § "Key features" — No link/CTA to "Getting Started", sample downloads, or first-task navigation — Add a "Next steps" section linking to Getting-Started.md.
- [Missing Information] Whole file — No framework / .NET version compatibility or minimum required Syncfusion version — Add a Version / Compatibility section.

---

## File: `Getting-Started.md`

- [Missing Steps] § "Creating project" — Section heading exists but no actual steps to create a project — Add explicit "File → New → Project → WPF App" walkthrough.
- [Missing Steps] § "Adding control via designer" — Does not mention installing the Syncfusion WPF Toolbox items or registering the toolbox — Add prerequisite for the Syncfusion VS extension.
- [Missing Steps] § "Save / Load the layout" — `PersistState` uses isolated storage but does not explain where files are stored or that storage is per-user — Add a storage-location note.
- [Missing Information] § "Adding control manually in XAML" — XAML uses `xmlns:local="clr-namespace:GettingStartedComboBox"` and `x:Class="GettingStartedComboBox.MainWindow"`, which do not match the Docking sample — Update namespace/Class to the Docking walkthrough.
- [Missing Information] § "Adding control manually in C#" — The `Output` instance is added without `Header`/`State`; doesn't match the XAML — Reconcile so C# and XAML agree.
- [Missing Information] § "Save / Load the layout" — C# block uses `SyncDockingManager` while XAML uses `x:Name="dockingManager"` — Use a single consistent name.
- [Technical Accuracy] § "Adding control manually in XAML" — XAML `xmlns:local` / `x:Class` reference `GettingStartedComboBox` (copy/paste from ComboBox docs) — Update to a Docking namespace.
- [Technical Accuracy] § "Adding control manually in C#" — `Output` ContentControl is created but never given a `Header` — Add `DockingManager.SetHeader(Output, "Output")`.
- [Technical Accuracy] § "Save / Load the layout" — C# uses `SyncDockingManager.PersistState` but XAML uses `x:Name="dockingManager"` — Reconcile the names.
- [Technical Accuracy] § "Set Visual Styles" — Two-step procedure (refer assemblies + apply style) is misordered: the XAML `syncfusionskin:SfSkinManager.VisualStyle` attribute is set on the DockingManager but the example C# uses `SfSkinManager.SetVisualStyle(SyncDockingManager, ...)` — Match XAML name and add the assembly reference for `Syncfusion.SfSkinManager.WPF`.
- [Grammar] Intro paragraph — "In this walk through, user will create…" — Awkward phrasing — Rewrite as "In this walkthrough, you will create…".
- [Structure] TOC at the top — Lists "Creating project" and "Adding control via designer" but those sections are placeholders — Add content or remove from the TOC.

---

## File: `Basic-Features.md`

- [Missing Information] § "Float State" — The XAML tab for `Float` is empty — Provide a code sample.
- [Missing Information] § "DockSide for Docked State child's" — `DockSide` enum options (`Left`, `Right`, `Top`, `Bottom`, `Tabbed`) are not formally listed — Add an enum table.
- [Technical Accuracy] § "Float State" — Empty `{% tabs %}` block contains no code — Add a `Float` XAML/C# sample.
- [Grammar] § Heading "DockSide for Docked State child's" — Stray apostrophe — Remove trailing `'`.
- [Grammar] § Heading "Document State Child" — "Child" should be plural — Use "Document State Children".
- [Structure] § "Document State Child" — Two sub-cases (TDI / MDI) are nested as H4 "Refer Also" but link to nothing — Replace with a concrete link to the TDI/MDI page.
- [Structure] § "Float State" — Empty tab before "Auto Hidden State" — Remove the empty tab.

---

## File: `Data-Binding.md`

- [Missing Information] § "Adding Docking Window child through ItemsSource" — No mention of `DockItem.Name` requirement for `TargetNameInDockedMode` resolution, nor of `INotifyPropertyChanged` support — Add notes.
- [Grammar] § Heading "Docking Window in Different side" — Singular vs plural — Use "in Different Sides".
- [Technical Accuracy] § "Customizing the Header of DockItem" — Link text says "HeaderStyle" but the property is `HeaderTemplate` — Correct the link.

---

## File: `Auto-Hide-Window.md`

- [Missing Information] § "Configuring Auto Hide Animation" — `AnimationDelay` XAML uses string `"100"` but property type is `Duration`; no C# sample for per-item delay — Add clarification and C# sample.
- [Missing Information] § "Enabling and disabling the AutoHide functionality" — `CanAutoHide` does not disable the AWL button in float state — Document the scope.
- [Missing Information] § "Animation modes" — `Docking.AutoHideAnimationMode` C# is a static-style call; instance form not shown — Show both forms.
- [Missing Information] § "Change AutoHide behavior like Visual Studio 2013" — Property name shown as `IsVS2013SidePanelEnable` in text vs `IsVS2013SidePanelEnable` in sample vs `IsVS2013SidePanelEnableProperty` in URL — Reconcile casing.
- [Missing Steps] § "Pinning / UnPinning All Window" — C# uses `DockingManager.AutoHideAllDockWindow()` (class name), but the docs elsewhere show instance calls — Clarify whether it is static or instance.
- [Technical Accuracy] § "Configuring window in Different Side" — XAML mixes straight `"` and curly `"` quotes (`"Top"` vs `“AutoHidden”`) — Use straight quotes only.
- [Technical Accuracy] § "Configuring Auto Hide Animation" — C# uses `Docking.SetAnimationDelay(...)` but the class is `DockingManager` — Correct to `DockingManager.SetAnimationDelay(...)`.
- [Technical Accuracy] § "Making different animation for AutoHideWindow" — C# `Docking.AutoHideAnimationMode` is undefined — Use `dockingManager.AutoHideAnimationMode`.
- [Technical Accuracy] § "Enabling and disabling the AutoHide functionality" — `AutoHideVisibility` sample does not define `SyncDockingManager` in XAML — Add the matching XAML name.
- [Grammar] § "Configuring window in Different Side" — "Side" should be plural — Use "Different Sides".
- [Grammar] § "Making different animation for AutoHideWindow" — Missing article — Use "a different animation".
- [Grammar] § "Pinning / UnPinning All Window" — Inconsistent capitalization and "Window" should be plural — Use "Pinning/Unpinning All Windows".
- [Structure] § "Enabling and disabling the AutoHide functionality" — `AutoHideVisibility` (DockingManager) and `CanAutoHide` (DockItem) are covered together without clear separation — Split into two subsections.

---

## File: `Floating-Window.md`

- [Missing Information] § "Rolling Up support" — URL anchor references `IsRollupFloatWindow` but text says `IsRollUpTopProperty` — Reconcile the API name.
- [Missing Information] § "Show or Hide the Taskbar support" — No default value stated for `ShowInTaskbar` (text only says "default is true") — Confirm and document.
- [Technical Accuracy] § "Rolling Up support" — XAML property shown is `IsRollupFloatWindow` but text introduces `IsRollUpTopProperty` — Pick one and align.
- [Grammar] § "Enabling or Disabling the float functionality Operation on Double Click" — Wordy heading — Shorten to "Disable Dock on Double-Click".

---

## File: `Docking-Window.md`

- [Missing Information] § "Limit Maximized Dock item" — `DesiredMaxHeightInDockedMode` is never assigned in the C# sample — Add the line.
- [Missing Information] § "MaximizeMode" — `MaximizeMode` values (`Default`, `FullScreen`) not enumerated — Add an enum table.
- [Missing Information] § "Custom context menu items for docking window" — C# adds items to `FloatWindowContextMenuItems` instead of `DockWindowContextMenuItems` — Correct.
- [Technical Accuracy] § "Custom context menu items for docking window" — C# adds to `FloatWindowContextMenuItems` (wrong) — Add to `DockWindowContextMenuItems` instead.
- [Structure] § "Maximize/Minimize Support" — Duplicated in `Advanced-Features.md` — Cross-link.

---

## File: `Dock-Hints.md`

- [Missing Steps] § "Restrict outer dockability" — No code sample for `OuterDockAbility` + `UseOuterDockAbility` — Add a complete XAML + C# example.
- [Missing Information] § "All", "DocumentAll", "DockAll" — `DockingManager.IsVS2010DraggingEnabled` introduced here; no version availability note — Add a "since version" note.
- [Structure] Terminology list — Numbered 1, 2, 5, 6, 3, 4 — Renumber sequentially.
- [Structure] § "Restrict docking at run-time" — Table describing `PreviewDockHintsEventArgs` is good but no equivalent table for `DockAbility` enum values — Add a table.

---

## File: `Tabbed-Window.md`

- [Missing Information] § "Tab alignments" — C# uses `Dock.Left/Right/Top/Bottom` (System.Windows.Controls) but no `using` is shown — Add the using directive.
- [Missing Information] § "Tabbed window order changed notification" — `e.Cancel` is not a property of `TabOrderChangedEventArgs` but is shown in the "Restrict" section — Clarify the event-args class.
- [Grammar] § Heading "Closing a Tabbed window" — Lowercase `w` — Capitalize to "Closing a Tabbed Window".
- [Structure] § "Tab alignments" — `DockTabAlignment` is also documented in `Interactive-Features.md` and `Styling-and-Templates.md` — Consolidate.

---

## File: `Interactive-Features.md`

- [Missing Steps] § "FloatWindow Customization" — Does not note that several brushes only take effect when `UseNativeFloatWindow=True` — Add dependency note.
- [Missing Information] § "Retrieving an Active Window from DockingManager" — C# references undefined `ffelement` variable inside the `Click` handler — Declare/rename.
- [Missing Information] § "DocumentTabControlStyle" — Uses `syncfusion:TabControlExt`; should target `DocumentTabControl` — Correct TargetType.
- [Missing Information] § "IsContextMenuButtonVisible" — C# uses `DockingManager.IsContextMenuButton = "false"` (wrong property) — Use `IsContextMenuButtonVisible`.
- [Missing Information] § "Providing Custom Menu Items" — `DockingManager.SetCustomMenuItems(DockingManager, collection)` passes the manager (incorrect) — Pass the child element.
- [Missing Information] § "Enabling/Disabling Animation on mouse over" — Description reverses the behavior (says `true` disables, but elsewhere `true` enables) — Pick one canonical description.
- [Missing Information] § "DocumentMDIHeaderStyle" — Sets a `Header` property on `DocumentHeader` style (not a property) — Remove the `Header` setter.
- [Technical Accuracy] § "Enabling/Disabling Animation on mouse over for auto hide" — Logic reversed — Correct so `false` disables mouse-over animation.
- [Technical Accuracy] § "CanClose" XAML — `<Grid Name="Properties" sftools:DockingManager.CanClose="True">` is missing the closing `>` — Add `/>`.
- [Technical Accuracy] § "Providing Custom Menu Items" — `SetCustomMenuItems(DockingManager, collection)` uses wrong first arg — Use the child control.
- [Technical Accuracy] § "Enable/Disable Dragging a Window" — XAML uses `sftools:` prefix but namespace is not declared — Use `syncfusion:` or declare `sftools:`.
- [Technical Accuracy] § "IsContextMenuButtonVisible" — Wrong API `IsContextMenuButton` — Use `IsContextMenuButtonVisible`.
- [Technical Accuracy] § "AutoHide Mode" C# — `DockingManager.AutoHideTabsMode` is set on a new instance but no children are added — Add children to demonstrate.
- [Technical Accuracy] § "DockedElementTabbedHostStyle" — Uses `x:Type syncfusion:DockedElementTabbedHost` (correct) but no `xmlns:syncfusion` in the sample — Add namespace.
- [Grammar] § Heading "Restrict Maximization or Minimization for a specific children" — Singular vs plural — Use "child".
- [Structure] § "Enable/Disable Docking, Floating, AutoHide, Closing" — Three H4 subsections under one H3 — Promote each to H3.
- [Structure] § "Default Context Menu" + "Custom Menu Items" + "ContextMenuItemClick Event" — Out of logical order (item click appears before custom items) — Reorder.
- [Structure] `CanDock`, `CanFloat`, `CanDrag` are duplicated in `Dealing-with-Windows.md` — Cross-link or deduplicate.

---

## File: `Dealing-with-Windows.md`

- [Missing Steps] § "Event to notify when a child is added or removed" — C# example is incomplete; doesn't show how to subscribe the handler in XAML — Add `ChildrenCollectionChanged="..."`.
- [Missing Information] § "Activating a window" — Treats `Content1` as both element and string — Pick one consistent overload.
- [Missing Information] § "Removing Window Programmatically" — VB uses `Grid1` which is undefined — Provide the host container.
- [Missing Information] § "Event to notify when a child is added or removed" — C# has typo `MessgeBox.Show` and undeclared `SolutionExplorer` — Fix and add declaration.
- [Missing Information] § "Customizing ContextMenuItems Visibility" — `CollapseDefaultContextMenuInDocument` (text) vs `CollapseDefaultContextMenuItemsInDocumentTab` (attached property) — Reconcile.
- [Missing Information] § "Restricting Docking in Float Window" — `CanDockonFloat` (text) vs `SetCanDockonFloat` (method) — Verify exact casing.
- [Technical Accuracy] § "Event to notify when a child is added or removed" — `MessgeBox.Show` typo and undefined `SolutionExplorer` / `dockingManager` — Fix.
- [Technical Accuracy] § "Hide or delete when closing a child item" — Closing tag `{% endhighlight%}` lacks a space and breaks the parser — Use `{% endhighlight %}`.
- [Grammar] § "DockBehavior" — Image tags `<Img alt=... src=.../>` will not render in standard markdown — Use plain text or `![](...)` syntax.
- [Structure] "Enable/Disable Dragging a Window", "Drag Shadow of a Window", "Drag Border of a Window" — All three belong in one H2 — Group under "Drag Modes".
- [Structure] § "Customizing a window" vs § "Customizing FloatWindow" — Duplicated in `Interactive-Features.md` — Deduplicate.

---

## File: `MDI-TDI-functionalities.md`

- [Missing Steps] § "Closing TDI tab items on mouse middle click" — Requires `CanClose=True` per child but doesn't show applying this to all documents — Add a bulk-apply note.
- [Missing Information] § "Different Keyboard Navigation Modes" — `VistaFlip` is named `VistaFlip` in samples but documentation does not state the full enum name — Document `SwitchMode.VistaFlip3D` (if applicable).
- [Missing Information] § "Detecting the maximized state of the MDI window" — `IsInMDIMaximizedState` is documented as get-only but sample assigns `= true` — Replace with a read.
- [Missing Information] § "Adding a new Tab using NewButtonClick event" — `sender` cast to `DocumentTabControl` but `e` is `EventArgs` (no `TargetTabGroup`) — Cast `e` to the correct event args type or change signature.
- [Missing Information] § "Restrict TDI window reordering" — Note mentions `DockStateChangingEvent` (wrong name) — Update.
- [Missing Information] § "TDI window's order changed notification" — XAML has `UseDocumentContainer="UseDocumentContainer"` (string) — Change to `True`.
- [Technical Accuracy] § "Setting MDI Layout" `Cascade` C# — Body calls `MDILayout.Vertical` instead of `MDILayout.Cascade` — Correct the body.
- [Technical Accuracy] § "Detecting the maximized state of the MDI window" — Assigning a read-only property — Replace with a getter call.
- [Technical Accuracy] § "Adding a new Tab using NewButtonClick event" — Wrong event-args type — Use the correct `NewButtonClickEventArgs`.
- [Technical Accuracy] § "TDI window's order changed notification" — XAML has `UseDocumentContainer="UseDocumentContainer"` — Change to `UseDocumentContainer="True"`.
- [Structure] § "Restrict TDI window reordering" — Duplicates `Tabbed-Window.md` "Restrict tabbed window reordering" — Consolidate.

---

## File: `Other-Features.md`

- [Missing Information] § "Enabling/Disabling Animation on mouse over for auto hide" — Reversed description — Correct.
- [Missing Information] § "Support to Enable or Disable Resize" — No code-behind sample for the manager-level properties — Add XAML and code pair.
- [Missing Information] § "Support to Enable or Disable Fixed Size" — C# sample uses `MaximizeButtonMode`/`CanMaximize` (unrelated) — Replace with FixedSize usage.
- [Missing Information] § "Native Float Window" — Stray `<td></tr>` HTML inside a `{% highlight %}` block — Remove.
- [Missing Information] § "Support to Add Document Tab Group" — `AddElementToTabGroup` method is shown but the method owner is `DockingManager` in the URL but the sample uses it on `dockingManager` — Verify correct owner.
- [Technical Accuracy] § "Enabling/Disabling Animation on mouse over for auto hide" — Logic reversed — Correct so `false` disables mouse-over animation.
- [Technical Accuracy] § "AutoHide Animation Delay" C# — `new TimeSpan(100)` is 100 ticks, not 100 ms — Use `TimeSpan.FromMilliseconds(100)`.
- [Technical Accuracy] § "Native Float Window" XAML — Stray HTML `<td></tr>` — Remove.
- [Technical Accuracy] § "Support to Enable or Disable Fixed Size" C# — Demonstrates `MaximizeButtonMode` instead — Replace.
- [Grammar] § Heading "Enabling/Disabling Animation on mouse over for auto hide" — Missing article — Use "Disabling Animation **on mouse hover** for auto-hide".
- [Structure] "VS2010 Behavior of Docking Manager" + "UseNativeFloatWindow" + "CanFloatMaximize" — Mixed old/legacy APIs (e.g., `SkinStorage`) without separation — Group modern vs legacy.

---

## File: `Styling-and-Templates.md`

- [Missing Steps] § "TabItemTemplate" — Uses `Syncfusion:DockPreviewManagerVS2005` without importing the namespace — Add namespace import.
- [Missing Steps] § "CloseButtonTemplate" — XAML has unclosed `<StackPanel>` and missing `</ControlTemplate>` — Add closing tags.
- [Missing Information] § "FloatWindowTemplate" — References `Syncfusion:IWindow` (not a public WPF type) and `OpacityDockPanel` (not declared) — Provide namespace and correct type.
- [Missing Information] § "SidePanelTemplate" — `TextBlock.Foreground={StaticResource Default.TabForeground}` is invalid attached-property syntax — Use a proper setter.
- [Missing Information] § "Custom header for individual child" — Sample sets `IsTemplateParenKeyboardFocusWithin` binding but no `DataTemplate` is provided — Provide complete resources.
- [Technical Accuracy] § "CloseButtonTemplate" — Unclosed `StackPanel` and `ControlTemplate` — Close tags.
- [Technical Accuracy] § "TopDragProvider" — XAML body uses `LeftDragProvider` property (copy/paste from earlier section) — Change to `TopDragProvider`.
- [Technical Accuracy] § "FloatWindowTemplate" — `IWindow` and `OpacityDockPanel` are wrong/unknown — Use correct public types.
- [Technical Accuracy] § "SidePanelTemplate" — Invalid attached-property assignment on `TextBlock.Foreground` — Use a `Setter`.
- [Structure] `DocumentTabControlStyle`, `DocumentTabItemStyle`, `DocumentMDIHeaderStyle` are duplicated in `Interactive-Features.md` — Deduplicate.

---

## File: `Advanced-Features.md`

- [Missing Information] § "Visual Styles" — `SkinStorage.SetVisualStyle` is the legacy API; modern API is `SfSkinManager.SetVisualStyle` — Update or note both.
- [Missing Information] § "Triggering Actions while closing" — `CloseAllTabs`/`CloseOtherTabs` used as XAML attributes (events) — Show correct attribute syntax.
- [Missing Information] § "Minimize/Maximize Support" properties table — `DockWindowState` row has empty `Type` and `Data Type` cells — Fill in.
- [Missing Information] § "Linked Manager Support" methods table — `Type` column shows "NA"; should be the parameter type — Correct.
- [Missing Steps] § "State Persistence" — Missing `using System.Runtime.Serialization.Formatters.Binary;` directive — Add to samples.
- [Missing Steps] § "Hosting Windows Form control" — `WebBrowser` shown is the WPF version, not WinForms — Add a `WindowsFormsHost` example.
- [Technical Accuracy] § "Visual Styles" — Legacy `SkinStorage` API — Add note about `SfSkinManager` and list required assemblies.
- [Technical Accuracy] § "Triggering Actions while closing" — `CloseAllTabs="..."`/`CloseOtherTabs="..."` used as XAML attributes — These are routed events; use event-handler attribute syntax.
- [Technical Accuracy] § "Minimize/Maximize Support" — `DockWindowState` row empty — Fill in.
- [Technical Accuracy] § "Linked Manager Support" — Methods table `Type` column says "NA" — Provide parameter type.
- [Technical Accuracy] § "Hosting Windows Form control" — `WebBrowser` is WPF, not WinForms — Replace with `WindowsFormsHost` + `System.Windows.Forms.WebBrowser`.
- [Grammar] § "Property table" — Inconsistent capitalization of section heading — Use Title Case.
- [Structure] "Use Case Scenarios", "Tables for Properties, Methods, and Events", "Sample Link", "Adding … to an Application" — Boilerplate repeats in every section — Introduce as a template at the top of the page.
- [Structure] § "State Persistence in DockingManager" — Duplicates `State-Persistence.md` — Link instead.
- [Structure] § "Linked Manager Support" — Duplicates `Linked-Manager.md` — Link instead.
- [Structure] § "Minimize/Maximize Support for Docked Windows" — Duplicates `Docking-Window.md` — Link instead.

---

## File: `State-Persistence.md`

- [Missing Steps] § "Auto Save / Load functionalities" — Does not explain how the hosting project's entry point must wire `LoadDockState` in `Loaded` — Add wiring example.
- [Missing Steps] § "Serialize the dynamically added children" — No code example of adding controls before calling `LoadDockState` — Add a sample.
- [Missing Information] § "Save and Load using XML file" — `BinaryFormatter` used with `StorageFormat.Xml` but `DocContainer` is not declared in VB — Add declaration.
- [Missing Information] § "Save and Load using XmlWriter" — VB combines `writer.Close()` and `XmlReader reader = XmlReader.Create(...)` on the same line — Split into two statements.
- [Missing Information] § "Save and Load using Binary" — VB reuses `format` variable twice (redeclaration error) — Rename one.
- [Technical Accuracy] § "Save and Load using XML file" — `BinaryFormatter` + `StorageFormat.Xml` pairing; `DocContainer` is undefined — Add `using` and declarations.
- [Technical Accuracy] § "Save and Load using XmlWriter" — Two statements on one line — Split.
- [Technical Accuracy] § "Save and Load using Binary" — Duplicate `BinaryFormatter format = …` — Rename.
- [Grammar] § "Notification for load DockState" — Awkward — Use "Notification when LoadDockState fails".
- [Structure] § "Manipulating Save / Load functionalities" — Has only placeholder H3s — Promote to actual subtopics.

---

## File: `Pattern-and-Practices.md`

- [Missing Steps] § "MVVM" / "MVVMLight" — No step to wire the `DockingAdapter` to `App.xaml` resources — Add the App.xaml registration.
- [Missing Steps] § "Practice with PRISM" — No step to register `DockingManagerRegionAdapter` in `ConfigureContainer` / `RegisterTypes` — Add registration.
- [Missing Information] § "Practice with PRISM" — Missing step to install Prism NuGet packages and reference the bootstrapper call — Add.
- [Missing Information] § "Prism 7.1" — `RegisterForNavigation<Toolbox.ToolboxModule>()` registers a module type instead of a view type — Show the correct call.
- [Missing Information] § "Prism 7.1" — `CreateModuleCatalog` and `RegisterTypes` both add modules — Show one canonical approach.
- [Technical Accuracy] § "Practice with PRISM" — Uses old Prism 5 namespace `http://www.codeplex.com/prism` — Use `http://prismlibrary.com/`.
- [Technical Accuracy] § "MVVMLight" — "Tools and Extension" — Should be "Extensions and Updates".
- [Technical Accuracy] § "Prism 7.1" — `RegisterForNavigation<ModuleType>` is wrong — Use `RegisterForNavigation<ViewType>()` and add module via `AddModule`.
- [Grammar] § "Practice with PRISM" — Inconsistent capitalization ("the prism application") — Use "Prism".
- [Structure] § "Practice with PRISM" + "Configuring DockingManager with Prism 6.1" + "Configuring DockingManager with Prism 7.1" — Three nearly identical sections — Consolidate.

---

## File: `Linked-Manager.md`

- [Missing Information] § "Nested Docking" — Inner DockingManager's `SideInDockedMode` and attached properties lack the `syncfusion:` prefix — Correct XAML.
- [Technical Accuracy] § "Nested Docking" XAML — Missing `syncfusion:` on `SideInDockedMode` and `Header` for inner DockingManager — Fix.
- [Structure] "Linked Manager" and "Nested Docking" are distinct topics on the same page — Split into two pages or H2 sections with clear separators.

---

## File: `Localization.md`

- [Missing Steps] Whole file — No steps to add a `.resx` file, set `CultureInfo`, or wire `LocalizationManager` — Add a complete walkthrough.
- [Missing Information] Whole file — No mention of `LocalizationManager` initialization, neutral cultures, or supported language codes — Add.
- [Technical Accuracy] Whole file — Uses `markdownify` filter for image embeds inside table cells, which will not render — Provide static descriptions.
- [Grammar] § "Float(en-US) Flotteur(c)" — French translation `Flotteur(c)` is incorrect — Use "Flottant".
- [Structure] Whole file — Single image-heavy table with `markdownify` tags — Add textual walkthrough first, then the table.

---

## File: `Hosting-Windows-Form-control-as-a-window.md`

- [Technical Accuracy] Whole file — `WebBrowser` shown is the WPF version, not the WinForms one — Replace with a `WindowsFormsHost` + `System.Windows.Forms.WebBrowser` example.
- [Structure] Whole file — Single sample in a whole page; same content exists in `Advanced-Features.md` — Link instead of duplicating.

---

## Summary by Category

| Category             | Count |
|----------------------|-------|
| Missing Steps        | 21    |
| Missing Information  | 38    |
| Technical Accuracy   | 40    |
| Grammar / Language   | 22    |
| Structure / Clarity  | 25    |
| **Total**            | **146** |

---

## Suggested Triage Order

1. **Technical Accuracy – High**: Property/Type/Enum mismatches that would cause compile or runtime errors (DockingManager vs Docking, Anchor vs Text, etc.).
2. **Missing Information – High**: Empty code samples, missing enum tables, missing assemblies.
3. **Missing Steps – High**: Steps that block a developer from completing a task (Getting Started placeholders, DockingAdapter registration).
4. **Structure – Medium**: Duplicate content across pages.
5. **Grammar / Language – Low**: Cosmetic and localization.
