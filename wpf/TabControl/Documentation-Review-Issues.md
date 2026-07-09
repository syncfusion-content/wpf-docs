# TabControl Documentation Review Issues

This file consolidates the issues identified during a quality and completeness review of the TabControl developer documentation. Each issue is filed as a separate report grouped by category, ready to be migrated to individual GitHub issues.

---

## 1. MISSING STEPS

### Issue TC-MS-01: C# assembly list is incomplete
- **File:** `Getting-Started.md`
- **Section:** Adding WPF TabControl via C#
- **Description:** Step 2 only lists `Syncfusion.Shared.WPF`, but the rest of the file and the XAML section also require `Syncfusion.Tools.WPF`.
- **Suggested Fix:** Add `Syncfusion.Tools.WPF` to the C# assembly list.

### Issue TC-MS-02: Redundant meta-step in C# instructions
- **File:** `Getting-Started.md`
- **Section:** Adding WPF TabControl via C#
- **Description:** Step 4 ("Declare the `TabControl` control using C#") is a meta-step that the developer cannot act on; the code is actually inside the `MainWindow` constructor from step 3.
- **Suggested Fix:** Remove step 4 or merge it into step 3.

### Issue TC-MS-03: No link to standard WPF SelectionChanged
- **File:** `Selecting-tabitem.md`
- **Section:** Tab selection changed notification
- **Description:** No link or reference to the standard `SelectionChanged` event on `TabControl`, which many developers will look for first.
- **Suggested Fix:** Add a note that `SelectedItemChangedEvent` is the Syncfusion equivalent of WPF `SelectionChanged`.

### Issue TC-MS-04: Drag-and-drop prerequisite not stated
- **File:** `Pin-Unpin-tabs.md`
- **Section:** Re-order pinned tabs
- **Description:** The section mentions "drag and drop" but doesn't document the prerequisite `AllowDragDrop="True"` on the `TabControl`.
- **Suggested Fix:** Add a link to the drag-and-drop section or state the prerequisite explicitly.

---

## 2. MISSING INFORMATION

### Issue TC-MI-01: CloseButtonState enum table incomplete
- **File:** `Closable-tabs.md`
- **Section:** Show or hide close button → Show or hide close button for specific tab item
- **Description:** The `CloseButtonState` table lists only `Visible` and `Collapsed`.
- **Suggested Fix:** Add `VisibleOnMouseOver` and any other valid enum values.

### Issue TC-MI-02: CloseButtonType "Common" position not explained
- **File:** `Closable-tabs.md`
- **Section:** Show or hide close button
- **Description:** Does not document that `CloseButtonType="Common"` shows a single close button at the tab-strip level (not per tab).
- **Suggested Fix:** Add a sentence explaining the position of the common close button.

### Issue TC-MI-03: Empty placeholders for default value
- **File:** `NewButton-Feature.md`
- **Section:** Change background and border thickness of new button
- **Description:** Sentence reads "and `` property is ``" with empty backticks where the property name and default value should appear.
- **Suggested Fix:** Fill in the default value of `NewButtonBorderThickness` and remove the stray backticks.

### Issue TC-MI-04: Inconsistent property name (URL vs text)
- **File:** `NewButton-Feature.md`
- **Section:** Select a new tab item while creating it by new button
- **Description:** The URL uses `SelectOnCreatingNewItemProperty` while the text uses `SelectOnCreatingNewItem`.
- **Suggested Fix:** Verify the actual property name and align URL and text.

### Issue TC-MI-05: Mismatched XAML and C# values
- **File:** `TabItem-Header.md`
- **Section:** Setting size and alignment of tab header
- **Description:** XAML uses `tabItemExt1 Height="30"` but the C# sets `tabItemExt1.Height = 300`. The values do not match.
- **Suggested Fix:** Pick one value and align both samples.

### Issue TC-MI-06: Wrong variable name in C# sample
- **File:** `TabItem-Header.md`
- **Section:** Setting size and alignment of tab header
- **Description:** C# uses `tabItemExt1.Width = 100` for the second item, but the variable name suggests `tabItemExt2`.
- **Suggested Fix:** Use `tabItemExt2` for the second item's size as the variable name implies.

### Issue TC-MI-07: No commit/cancel key documentation
- **File:** `TabItem-Header.md`
- **Section:** Edit tab item header at runtime
- **Description:** Mentions `Ctrl + F2` to start editing but doesn't document how to commit/cancel (Enter/Esc).
- **Suggested Fix:** Add a sentence on commit/cancel behavior.

### Issue TC-MI-08: Undefined `NotificationObject` base class
- **File:** `DataBinding.md`
- **Section:** Adding tab items using data binding
- **Description:** `ViewModel : NotificationObject` is used without a definition or import.
- **Suggested Fix:** Add a `using Syncfusion.Windows.Shared;` line or note that `INotifyPropertyChanged` can be used instead.

### Issue TC-MI-09: No version/compatibility notes
- **Files:** All `.md` files in `TabControl/`
- **Description:** No documentation of minimum Essential Studio version, target .NET version, or required NuGet packages.
- **Suggested Fix:** Add a version-prerequisites section to `Getting-Started.md`.

### Issue TC-MI-10: No error-handling or troubleshooting guidance
- **Files:** All `.md` files in `TabControl/`
- **Description:** Common runtime issues (XAML parse errors, missing `Tools.WPF` assembly, binding failures) are not addressed.
- **Suggested Fix:** Add a Troubleshooting section to `Getting-Started.md`.

---

## 3. TECHNICAL ACCURACY

### Issue TC-TA-01: TabOrderChanged link points to DockingManager
- **File:** `Arrange-tabs.md`
- **Section:** Tab item order changed notification
- **Description:** The `TabOrderChanged` link points to `Syncfusion.Windows.Tools.Controls.DockingManager` instead of `TabControlExt`.
- **Suggested Fix:** Update the URL to point to the `TabControlExt` API page.

### Issue TC-TA-02: TabOrderChanging link points to DockingManager
- **File:** `Arrange-tabs.md`
- **Section:** Restrict tab item reordering
- **Description:** The `TabOrderChanging` link also points to `DockingManager`.
- **Suggested Fix:** Update the URL to point to the `TabControlExt` API page.

### Issue TC-TA-03: Wrong EventArgs type
- **File:** `Arrange-tabs.md`
- **Section:** Restrict tab item reordering
- **Description:** C# handler signature uses `TabOrderChangedEventArgs` for the `TabOrderChanging` event.
- **Suggested Fix:** Verify the actual args type (likely `TabOrderChangingEventArgs`).

### Issue TC-TA-04: Duplicate Header value in ViewModel
- **File:** `DataBinding.md`
- **Section:** Adding tab items using data binding
- **Description:** `Model2.Header = "tab1"` is a copy-paste of `model1`'s value; should be `"tab2"`.
- **Suggested Fix:** Fix to `Header = "tab2"`.

### Issue TC-TA-05: Incorrect focus condition
- **File:** `Getting-Started.md`
- **Section:** Selecting TabItem
- **Description:** Says "use the `Ctrl + Tab` key to select a tab item when control not in focused state" but `Ctrl+Tab` typically requires the control to be focused.
- **Suggested Fix:** Reverse the condition or document the correct modifier.

### Issue TC-TA-06: Duplicate image filename
- **File:** `TabItem-Header.md`
- **Section:** Custom UI for the edit tab item header
- **Description:** The image filename `Header_runtime.png` is reused for two different sections (Edit tab item header at runtime and Restrict header editing).
- **Suggested Fix:** Use distinct image filenames.

### Issue TC-TA-07: Typo "th"
- **File:** `Pin-Unpin-tabs.md`
- **Section:** Re-order pinned tabs
- **Description:** "by using th `AllowDragDrop` property" — typo `th` → `the`.
- **Suggested Fix:** Fix typo to "the".

### Issue TC-TA-08: Wrong handler wired in XAML
- **File:** `ContextMenu.md`
- **Section:** Tab item context menu events
- **Description:** XAML wires `OnCloseOtherTabs="TabControlExt_OnCloseAllTabs"`, reusing the `OnCloseAllTabs` handler.
- **Suggested Fix:** Wire `OnCloseOtherTabs` to its own handler `TabControlExt_OnCloseOtherTabs`.

### Issue TC-TA-09: Non-standard event name
- **File:** `Selecting-tabitem.md`
- **Section:** Tab selection changed notification
- **Description:** Event name `SelectedItemChangedEvent` (ending in `Event`) is non-standard for a CLR event.
- **Suggested Fix:** Verify; Syncfusion's event is typically named `SelectedItemChanged`.

---

## 4. GRAMMATICAL / LANGUAGE ISSUES

### Issue TC-GL-01: "how to closing"
- **File:** `Closable-tabs.md`
- **Section:** Close tabs in WPF TabControl
- **Description:** "explains how to closing the tab item".
- **Suggested Fix:** Change to "explains how to close the tab item".

### Issue TC-GL-02: Subject-verb agreement
- **File:** `Closable-tabs.md`
- **Section:** Show or hide close button
- **Description:** "All close buttons is hidden".
- **Suggested Fix:** Change to "All close buttons are hidden".

### Issue TC-GL-03: Typo "individul"
- **File:** `Closable-tabs.md`
- **Section:** Show or hide close button
- **Description:** "individul close buttons".
- **Suggested Fix:** Fix typo to "individual".

### Issue TC-GL-04: Article "a" before vowel
- **File:** `Closable-tabs.md`
- **Section:** Hide or delete item when closing a tab
- **Description:** "when closing a item".
- **Suggested Fix:** Change to "when closing an item".

### Issue TC-GL-05: Awkward phrasing
- **File:** `Arrange-tabs.md`
- **Section:** Rearrange position of tab items
- **Description:** "drag that item and drop to anywhere".
- **Suggested Fix:** Change to "drag the item and drop it anywhere".

### Issue TC-GL-06: Inconsistent heading case
- **File:** `Arrange-tabs.md`
- **Section:** change drag marker color
- **Description:** Heading uses lowercase "change" while all sibling headings use title case.
- **Suggested Fix:** Change to "Change Drag Marker Color".

### Issue TC-GL-07: Extra article
- **File:** `ContextMenu.md`
- **Section:** Default tab item context menu
- **Description:** "You can close the one or more tab items".
- **Suggested Fix:** Change to "You can close one or more tab items".

### Issue TC-GL-08: Pronoun agreement
- **File:** `ContextMenu.md`
- **Section:** Tab item context menu events
- **Description:** "You can handle this events as follows".
- **Suggested Fix:** Change to "You can handle these events as follows".

### Issue TC-GL-09: Tense/agreement
- **File:** `Pin-Unpin-tabs.md`
- **Section:** Functionality of PinButton
- **Description:** "if its not have any pinned tab".
- **Suggested Fix:** Change to "if it does not have any pinned tab".

### Issue TC-GL-10: Awkward phrasing
- **File:** `Pin-Unpin-tabs.md`
- **Section:** Functionality of PinButton
- **Description:** "placed after to the pinned tab items".
- **Suggested Fix:** Change to "placed after the pinned tab items".

### Issue TC-GL-11: Missing articles
- **File:** `Selecting-tabitem.md`
- **Section:** Select tab item using mouse or keyboard
- **Description:** "when control not in focused state".
- **Suggested Fix:** Change to "when the control is not in a focused state".

### Issue TC-GL-12: Long awkward sentence
- **File:** `Selecting-tabitem.md`
- **Section:** Select tab item using mouse or keyboard
- **Description:** "to select the previous tab item or next tab item of current selected tab item when control in focused".
- **Suggested Fix:** Change to "to select the previous or next tab item relative to the currently selected tab item when the control is focused".

### Issue TC-GL-13: Awkward phrasing
- **File:** `TabItem-Header.md`
- **Section:** Setting tab item header
- **Description:** "add a text for the each tab headers".
- **Suggested Fix:** Change to "add text to each tab header".

### Issue TC-GL-14: Awkward phrasing
- **File:** `TabItem-Header.md`
- **Section:** Custom UI for the edit tab item header
- **Description:** "for the each tab items".
- **Suggested Fix:** Change to "for each tab item".

### Issue TC-GL-15: Awkward phrasing
- **File:** `TabItem-Header.md`
- **Section:** Setting tooltip
- **Description:** "for the each tab items".
- **Suggested Fix:** Change to "for each tab item".

### Issue TC-GL-16: Awkward phrasing
- **File:** `TabItem-Header.md`
- **Section:** Setting size and alignment of tab header
- **Description:** "size of the each tabs".
- **Suggested Fix:** Change to "size of each tab".

### Issue TC-GL-17: "can bound to"
- **File:** `DataBinding.md`
- **Section:** Adding tab items using data binding
- **Description:** "The `TabControl` can bound to an external source to auto create tabs".
- **Suggested Fix:** Change to "The `TabControl` can be bound to an external source to automatically create tabs".

### Issue TC-GL-18: "for display"
- **File:** `DataBinding.md`
- **Section:** TabItem content
- **Description:** "for display the content of the tab item".
- **Suggested Fix:** Change to "to display the content of the tab item".

### Issue TC-GL-19: Missing article
- **File:** `Arrange-tabs.md`
- **Section:** Tab items alignment
- **Description:** "Tab items alignment" heading is missing an article.
- **Suggested Fix:** Change to "Align tab items".

### Issue TC-GL-20: Number agreement
- **File:** `NewButton-Feature.md`
- **Section:** Adding New tab button and new tab item
- **Description:** "adding new tab items to `TabControl`" (singular vs. plural confusion: "a new tab items").
- **Suggested Fix:** Change to "adding a new tab item to the `TabControl`".

### Issue TC-GL-21: Redundant "on" and missing verb
- **File:** `NewButton-Feature.md`
- **Section:** Auto hide new button when no child tab item
- **Description:** "The `TabControl` automatically hides the new button on when no child tab item present".
- **Suggested Fix:** Change to "The `TabControl` automatically hides the new button when no child tab item is present".

### Issue TC-GL-22: Lowercase "f" in platform
- **File:** `Getting-Started.md`
- **Section:** Front matter
- **Description:** `platform: WPf` (lowercase `f`).
- **Suggested Fix:** Fix to `platform: WPF`.

### Issue TC-GL-23: Inconsistent layout mode name
- **File:** `Overview.md`
- **Section:** Key features
- **Description:** "Layout" entry says "MultiLineWithFillWidth" but other files use `MultiLineWithFullWidth`.
- **Suggested Fix:** Standardize on `MultiLineWithFullWidth`.

---

## 5. STRUCTURE / CLARITY

### Issue TC-SC-01: Redundant meta-step
- **File:** `Getting-Started.md`
- **Section:** Adding WPF TabControl via C#
- **Description:** Step 4 is a meta-step that the developer can't act on.
- **Suggested Fix:** Remove or rephrase as "Add the code below to your `MainWindow` constructor".

### Issue TC-SC-02: Heading article error
- **File:** `Closable-tabs.md`
- **Section:** Hide or delete item when closing a tab
- **Description:** "a item" should be "an item".
- **Suggested Fix:** Change to "Hide or delete an item when closing a tab".

### Issue TC-SC-03: Wrong heading level
- **File:** `TabItem-Header.md`
- **Section:** Customize tab item header → Change tab item background
- **Description:** "Change tab item background" is an H2 instead of H3, breaking the hierarchy.
- **Suggested Fix:** Make "Change tab item background" an H3.

### Issue TC-SC-04: Wrong heading level
- **File:** `TabItem-Header.md`
- **Section:** Change tab item foreground
- **Description:** "Change tab item foreground" is an H2 instead of H3.
- **Suggested Fix:** Make it an H3.

### Issue TC-SC-05: Inconsistent heading case
- **File:** `Arrange-tabs.md`
- **Section:** change drag marker color
- **Description:** Heading case inconsistent with all sibling H2s.
- **Suggested Fix:** Use title case "Change Drag Marker Color".

### Issue TC-SC-06: Incomplete default-value phrase
- **File:** `NewButton-Feature.md`
- **Section:** Change background and border thickness of new button
- **Description:** Sentence ends mid-thought with empty backticks `and `` property is ```.
- **Suggested Fix:** Remove the incomplete default-value phrase or fill it in.

### Issue TC-SC-07: Incomplete layout list
- **File:** `Overview.md`
- **Section:** Key features
- **Description:** "Layout" entry lists three modes but the full set has five (`SingleLine`, `SingleLineStar`, `MultiLine`, `MultiLineWithFullWidth`, `MultiLineStar`).
- **Suggested Fix:** List all five or remove the list.

### Issue TC-SC-08: No intro for grouped binding sections
- **File:** `DataBinding.md`
- **Section:** TabItem Header / TabItem content / Editing tab header
- **Description:** These three sections appear under one binding topic but aren't introduced as a group.
- **Suggested Fix:** Add a short intro sentence linking the three.
