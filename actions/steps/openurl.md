---
title: Action Step – Open URL
---
# Action Step: Open URL

Construct and open an URL. Can be used to open web URLs, but also other apps utilizing non-http URL schemes.

## Options

- **Template**: Template for URL.
- **Encode tags**: If enabled, the output of Drafts template tags will automatically be encoded for use in URL query parameters. For example, if the current draft has the text "Hello World" the `[[draft]]` tag would return "Hello%20World" with this option enabled. If you are using tags previous encoded in prior action steps, this can be diabled.
- **Use Safari**: If enabled, Drafts will open the URL in-app using Safari View Controller, rather than passing the URL to iOS to open.
