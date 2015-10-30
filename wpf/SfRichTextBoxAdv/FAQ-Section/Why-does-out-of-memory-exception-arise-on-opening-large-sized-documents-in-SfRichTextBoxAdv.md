---
layout: post
title: Why-does-out-of-memory-exception-arise-on-opening-large-sized-documents-in-SfRichTextBoxAdv
description: why does out of memory exception arise on opening large-sized documents in sfrichtextboxadv
platform: winrt
control: RichTextBoxAdv
documentation: ug
---

### Why does out of memory exception arise on opening large-sized documents in SfRichTextBoxAdv

The SfRichTextBoxAdv control keeps the entire rich text content (text, images, tables, and all the other supported elements along with its formatting) of the document and its corresponding information needed for rendering in main memory. In case of opening a Docx file, you may think that the file size is small and SfRichTextBoxAdv utilizes a very large memory; whereas it is a zip archive file with extension “docx” and SfRichTextBoxAdv control internally decompresses it and populates the content in the document object model by utilizing remarkable amount of main memory.

The SfRichTextBoxAdv control supports UI Virtualization. UI elements are created only for the contents that are visible in the viewer. The UI elements are created for the contents that become visible while scrolling the viewer. This reduces the main memory utilization and also improves UI performance. Even though UI Virtualization is handled, the main memory utilization increases with respect to the increase of content and its complexity. The main memory utilized by an instance will not be released until the instance is removed from the document. So, there is a chance for out of memory exception when the memory utilization exceeds the maximum level as the content of the document increases. In that case, split the contents to several documents or use high configuration machines with extended RAM so as to create or open large sized documents comfortably.







