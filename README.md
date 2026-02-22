# NotepadXT: Find and Replace Utility

NotepadXT is a simple yet powerful find and replace utility for text manipulation. It provides a user-friendly interface to search for specific strings or patterns within a text area and replace them with new content.  This tool supports various search modes and options to give you fine-grained control over the find and replace process.

**Launch the app:**

https://html-preview.github.io/?url=https://raw.githubusercontent.com/pbelyasnik/NotepadXT/master/src/app.html

## Purpose

The primary purpose of NotepadXT is to streamline the process of modifying text. Whether you need to make bulk changes, correct errors, or reformat content, this utility can save you time and effort. It's particularly useful for developers, writers, and anyone who frequently works with text data.

## Features

NotepadXT offers the following features:

### Find and Replace Functionality

*   **Find What:** Specify the string or pattern you want to search for.
*   **Replace With:** Enter the text you want to replace the found content with.
*   **Find Next:** Locates the next occurrence of the search term.
*   **Count All:** Counts the total number of occurrences of the search term.
*   **Replace:** Replaces the current highlighted instance of the search term.
*   **Replace All:** Replaces all occurrences of the search term with the replacement text.

### Matching Options

*   **Match Whole Word Only:** Ensures that only whole words matching the search term are found (e.g., searching for "cat" won't find "scat").
*   **Match Case:** Makes the search case-sensitive (e.g., "Cat" will not match "cat").
*   **Wrap Around:** When reaching the end of the text, the search will wrap around to the beginning to continue searching.

### Search Modes

*   **Normal:** Performs a simple string search.
*   **Extended:** Interprets escape sequences like `\n` (newline), `\r` (carriage return), `\t` (tab), `\0` (null), and `\x...` (hexadecimal character).
*   **Regular Expression:** Enables powerful pattern matching using regular expressions.  This mode offers the greatest flexibility for complex searches.  **Crucially, in regex mode, the replace field supports backreferences (e.g., `$1`, `$2`, etc.) to insert captured groups from the matched pattern into the replacement text.  This allows for powerful transformations of the matched content.** For example, if you search for `(.)(.)(.)` and replace with `$3$2$1`, you will reverse the order of the first three characters of each match.  You can also use named capture groups like `(?<first>.)(?<second>.)` and refer to them as `$<first>`, `$<second>`. You can specify regex flags in the `regex flags` input box.
*   **Regex Flags**: Add flags to your regular expression. For example, `i` for case-insensitive matching.

### Direction

*   **Up:** Searches for matches from the current cursor position upwards.
*   **Down:** Searches for matches from the current cursor position downwards (default).

### View

*   **Word Wrap:** Enables or disables word wrapping in the text area.
*   **Dark Theme:** Toggles between light and dark color schemes.
*   **Font:** Choose the font used in the text area.
*   **Size:** Adjust the font size in the text area.

### Editor Shortcuts

Keyboard shortcuts available while editing text in the text area:

| Shortcut | Action |
|---|---|
| `Tab` | Indent selected line(s) |
| `Shift+Tab` | Unindent selected line(s) |
| `Ctrl+D` | Duplicate current line (or all selected lines) below; cursor stays on the original line |
| `Ctrl+Shift+Up` | Move current line (or selected lines) up |
| `Ctrl+Shift+Down` | Move current line (or selected lines) down |
| `Ctrl+U` | Lowercase selected text |
| `Ctrl+Shift+U` | Uppercase selected text |
| `Ctrl+S` | Download textarea content as a UTF-8 text file |
| `Ctrl+Z` / `Cmd+Z` | Undo |
| `Ctrl+Y` / `Cmd+Y` / `Ctrl+Shift+Z` / `Cmd+Shift+Z` | Redo |

All shortcuts preserve the selection range after the operation and save undo state before modifying.

### Configuration Persistence

The app's configuration (search options, view settings, etc.) is saved in the URL hash and automatically restored on reload.

## How to Use

1.  Enter the text you want to search for in the "Find what" field.
2.  Enter the text you want to replace it with in the "Replace with" field.
3.  Choose the desired matching options and search mode.
4.  Select the search direction (up or down).
5.  Use the "Find Next," "Count All," "Replace," and "Replace All" buttons to perform the desired actions.
6.  The message box will display feedback on the operations.

## Example (Regular Expression with Backreferences)

Let's say you have the following text:

```
John Doe
Jane Smith
Peter Jones
```

And you want to swap the first and last names. You can use the following:

*   **Find what:** `(.*) (.*)`
*   **Replace with:** `$2 $1`
*   **Search Mode:** Regular expression

After clicking "Replace All," the text will become:

```
Doe John
Smith Jane
Jones Peter
```

This demonstrates the power of regular expressions and backreferences for text manipulation.
