---
title: Scripting
---
# Scripting

Drafts actions may contain Script steps which execute Javascript. The Javascript engine is implemented using the [JavaScriptCore](https://developer.apple.com/documentation/javascriptcore) implementation Apple ships with the host platform, and all standard libraries are available to work with native Javascript data types.  Note that this is not a browser hosted Javascript environment and will not have access to the same extensions to the language provided by browsers, like the Document Object Model and XHTTP objects.

[w3schools.com Javascript reference](https://www.w3schools.com/jsref/default.asp) is an excellent resource on basic language objects and functions.

Drafts extends the Javascript environment with many objects to allow manipulation of drafts, the editor - and to interact with system and online services.

Details on the objects currently available in Drafts scripting environment is maintained at the [project Wiki](https://github.com/agiletortoise/drafts-documentation/wiki) at this time.

Also note that the Drafts scripting environment includes [Date.js](http://datejs.com), a great library which extends Javascript Date and Number objects for easier date manipulation and basic natural language date parsing. All examples and detailed documentation are available on the [Date.js site](http://datejs.com)
