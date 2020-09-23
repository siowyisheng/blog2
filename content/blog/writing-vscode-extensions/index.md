---
title: "Writing VSCode Extensions"
date: "2019-12-05"
category: "code"
description: "Sharing and thoughts on writing VSCode extensions."
---

After writing my first chrome extension last week. Today, I explored writing a language support vscode extension for writing TagUI scripts.

#### Interesting capabilities of vscode extensions

1. Access the filesystem.
2. Register commands to the command palette.
3. Register context menu items (when right-clicking).
4. Store data.
5. Display notifications.
6. Get user input through a wizard (called QuickPick).
7. Change colors of code/UI.
8. Change file icons.
9. Show info when hovering some api.
10. Add autocomplete for a language.
11. Show information in the status bar.
12. Show custom content (with WebView API).
13. Highlight syntax for a language.

#### On language extensions

You can write a **Language Server**, which is text-editor-agnostic, or just code directly for vscode.

I'll write more as I discover more.
