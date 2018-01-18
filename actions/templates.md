---
title: Templates
---
# Templates

Drafts actions support a number of tags for dynamically inserting text when an action is performed. These can be used in most fields that accept text in actions, including not only fields for content, but for naming, creating subject lines, etc.

### Content Tags

- `[[draft]]` The full text of the draft.
- `[[title]]` The first line of the draft only.
- `[[safe_title]]` File name safe version of the first line with white-space and punctuation characters removed.
- `[[body]]` The remainder of the draft text after the first line is removed.
- `[[selection]]` If text was selected within the draft before selecting an action, this tag will return only that selected text. If no text was selected, it will return the full text of the draft.
- `[[line|n]]` The text of a specific line number in the draft, where “n” is the line number. i.e. `[[line|1]]`, `[[line|2]]`.
- `[[line|n..n]]` In addition to specific lines, the lines tag (above) can accept ranges of lines, such as `[[line|2..5]]` for lines 2 through 5. This initial or trailing number in the range can be omitted to indicate the beginning or end, i.e. `[[line|2..]]` is line 2 through the end of the draft, `[[line|..4]]` is the first for lines of the draft.
- `[[selection_start]]` The integer index of the start location of the last text selection in the draft.
- `[[selection_length]]` The number of characters in the last text selection in the draft.

### Identifier Tags

- `[[uuid]]` A unique identifier for the current draft.
- `[[draft_open_url]]` A URL which can be used as a bookmark to open Drafts and select the current draft.

### Dates and Locations

- `[[date]]` Timestamp in the format YYYY-MM-DD.
- `[[date|format]]` Timestamp, formatted based on a custom strfime format string. For example `[[date|%m-%d-%Y]]` becomes “01–02–2013”.
- `[[created|format]]` Same as “date”, but returns the timestamp for the creation of the draft, rather than the current time.
- `[[modified|format]]` Same as “date”, but returns the timestamp for the last modification date of the draft content, rather than the current time.
- `[[longitude]]` The current device location longitude.
- `[[latitude]]` The current device location latitude.
- `[[created_longitude]]` The location longitude where the draft was created.
- `[[created_latitude ]]` The location latitude where the draft was created.
- `[[modified_longitude]]` The location longitude where the content of the draft was last modified.
- `[[modified_latitude]]` The location latitude where the content of the draft was last modified.
- `[[time]]` Timestamp in the format YYYY-MM-DD-HH-MM-SS.

### Utility Tags

- `[[clipboard]]` The current contents of the iOS clipboard.

## Other Special markup

- `{% raw %}{{ }}{% endraw %}` Wrap text in double-curly brackets to have the text URL encoded.
- `{% raw %}%% %%{% endraw %}` Wrap text in double percent signs to run the enclosed text through the Markdown engine and convert it to HTML.  This is useful to export Markdown to HTML, use in HTML Preview steps or other purposes.  By default, HTML5 compliant HTML is generated, but if you include the xhtml parameter, like `%%xhtml|...%%`, XHTML will be output.  This is needed to generate HTML compatible with Evernote's ENML markup.
- `<<snippet-abbreviation>>` A valid [TextExpander](https://textexpander.com) abbreviation wrapped in double brackets will be expanded at runtime.
