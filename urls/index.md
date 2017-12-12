---
title: URLs
---
# URL Actions

Drafts implement URL actions based on [the x-callback-url specification](http://x-callback-url.com/), and registers the **drafts5:** URL scheme.  All actions below should be formatted as follows:

- `drafts5://x-callback-url/[actionName]?[queryParameters]`

All URLs should be proper valid URLs with URL encoded values in query arguments. With a few exceptions, all actions support x-callback-url x-success, x-error and x-cancel arguments where appropriate.

## Supported Actions

### /create

Create a new draft with the content passed in the "text" argument.

- **Arguments**
  - **text** *[string, required]* : Text to be used at the content of the new draft.
  - **action** *[string, optional]* : Name of an action in the action list. If provided, this action will be run on the specified draft.
- **Examples**
  - `drafts5://x-callback-url/create?text=Hello%20World`
    - Create new draft with the content "Hello World"

### /open

Open an existing draft based on the UUID argument.

- **Arguments**
  - **uuid** *[string, required]* : The UUID identifier for a draft.
  - **action** *[string, optional]* : Name of an action in the action list. If provided, this action will be run on the specified draft.
- **Examples**
  - `drafts5://x-callback-url/open?uuid=UUID-TO-VALID-DRAFT`
    - Open the draft in the editor with the UUID provided.

### /get

Return the current content of the draft specified by the UUID argument as an argument to the x-success URL provided.

- **Arguments**
  - **uuid** *[string, required]* : The UUID identifier for a draft.
  - **retParam** *[string, optional]* : The name of the argument to use to pass the draft content back to the x-success URL.  Defaults to "text", but if the requesting app expects another value (like Workflow's "input") use this argument to override.
- **Examples**
  - `drafts5://x-callback-url/get?uuid=UUID-TO-VALID-DRAFT&x-success=APP-URL`
    - Retrieves the content of the identified draft, and calls the x-success URL with the argument `text=DRAFT-CONTENT` added.

### /prepend

Prepend the passed text to the beginning of a draft identified by the UUID argument.

- **Arguments**
  - **uuid** *[string, required]* : The UUID identifier for a draft.
  - **text** *[string, required]* : Text to add.
  - **action** *[string, optional]* : Name of an action in the action list. If provided, this action will be run on the specified draft.
- **Examples**
  - `drafts5://x-callback-url/prepend?uuid=UUID-TO-VALID-DRAFT&text=TEXT-TO-ADD`
    - Adds "TEXT-TO-ADD" to the beginning of the draft.

### /append

Append the passed text to the end of a draft identified by the UUID argument.

- **Arguments**
  - **uuid** *[string, required]* : The UUID identifier for a draft.
  - **text** *[string, required]* : Text to add.
  - **action** *[string, optional]* : Name of an action in the action list. If provided, this action will be run on the specified draft.
- **Examples**
  - `drafts5://x-callback-url/append?uuid=UUID-TO-VALID-DRAFT&text=TEXT-TO-ADD`
    - Adds "TEXT-TO-ADD" to the end of the draft.

### /search

Open drafts directly to the draft search field.

- **Arguments**
  - **query** *[string, optional]* : Initial text to use in the search.
  - **tag** *[string, optional]* : Tag to use to filter the query.
- **Examples**
  - `drafts5://x-callback-url/search?query=QUERY-TEXT`

### /runAction

Run a drafts action on the passed text without saving that text to a draft.

- **Arguments**
  - **text** *[string, required]* : Text to add.
  - **action** *[string, optional]* : Name of an action in the action list. If provided, this action will be run on the specified draft.
- **Examples**
  - `drafts5://x-callback-url/prepend?uuid=UUID-TO-VALID-DRAFT&text=TEXT-TO-ADD`
    - Adds "TEXT-TO-ADD" to the beginning of the draft.
  - `drafts5://x-callback-url/runAction?text=TEXT&action=VALID-ACTION-NAME`
    - If found, runs the VALID-ACTION-NAME action on an unsaved draft containing "TEXT".

### /dictate

Open Drafts dictation interface. Pass the resulting dictated text to the x-success URL instead of saving it in Drafts.

- **Arguments**
  - **retParam** *[string, optional]* : The name of the argument to use to pass the draft content back to the x-success URL.  Defaults to "text", but if the requesting app expects another value (like Workflow's "input") use this argument to override.
- **Examples**
  - `drafts5://x-callback-url/dictate?x-success=APP-URL`
    - Retrieves the content of the identified draft, and calls the x-success URL with the argument `text=DICTATED-TEXT` added.

### /arrange

Open Drafts arrange interface. Pass the resulting arranged text to the x-success URL instead of saving it in Drafts.

- **Arguments**
  - **text** *[string, required]* : Text to arrange.
  - **retParam** *[string, optional]* : The name of the argument to use to pass the draft content back to the x-success URL.  Defaults to "text", but if the requesting app expects another value (like Workflow's "input") use this argument to override.
- **Examples**
  - `drafts5://x-callback-url/arrange?x-success=APP-URL`
    - Retrieves the content of the identified draft, and calls the x-success URL with the argument `text=ARRANGED-TEXT` added.
