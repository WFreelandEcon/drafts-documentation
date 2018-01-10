---
title: Action Step – Callback URL
---
# Action Step: Callback URL

Similar to [Open URL]({{ site.baseurl }}/actions/steps/openurl.md), but for use with other apps with support [x-callback-url](http://x-callback-url.com/) to return to other apps after completing a URL action.

When using this step, create a target URL in the template, but do **not** include x-callback-url return parameters (x-success, x-error, x-cancel) as Drafts will generate and add those parameters.

If the "Wait for response" option is enabled, Drafts will hold processing of the action waiting on a response from the target app. If the target app responds using x-success, the action will continue and any response parameters provided by the target app will be available in the `context.callbackResponses` ([docs](https://github.com/agiletortoise/drafts-documentation/wiki/Context)) object for subsequent script steps in the action. Additionally, new template tags will be defined for each parameter included in the callback response, named "callback_parameterName".  For example, if the callback included `result=Hello`, the template tag `[[callback_result]]` would be available for later action steps in the same action, and it would return `Hello`. If the target app responds with x-cancel callback, the action will be cancelled - x-error will fail the action and log responses.

If "Wait for response" is enabled, Drafts will wait for 120 seconds for a response from the target app, and cancel the remainder of the action if none is received.

## Options

- **Template**: Template for URL.
- **Encode tags**: If enabled, the output of Drafts template tags will automatically be encoded for use in URL query parameters. For example, if the current draft has the text "Hello World" the `[[draft]]` tag would return "Hello%20World" with this option enabled. If you are using tags previous encoded in prior action steps, this can be diabled.
- **Wait for response**: If enabled, Drafts will wait for a callback response from a target app. See details above.
