---
title: Action Step  – Run Workflow
---
# Action Step: Run Workflow

Run a named workflow in the [Workflow app](https://workflow.is).

If the "Wait for response" option is enabled, Drafts will hold processing of the action waiting on a response from Workflow. If the Workflow responds using x-success, the action will continue and any response parameters provided by the target app will be available in the `context.callbackResponses` ([docs](https://github.com/agiletortoise/drafts-documentation/wiki/Context)) object for subsequent script steps in the action. Additionally, a new template tag will be defined for the result parameter included in the callback response, named "workflow_result".  For example, if the workflow returned "Hello", the template tag `[[workflow_result]]` would be available for later action steps in the same action, and it would return `Hello`. If the target app responds with x-cancel callback, the action will be cancelled - x-error will fail the action and log responses.

If "Wait for response" is enabled, Drafts will wait for 120 seconds for a response from the target app, and cancel the remainder of the action if none is received.

## Options

- **Workflow name**: Name of a valid Workflow in the Workflow app. Must match exactly.
- **Template**: Template for content to send to Workflow as an "input" parameter.
- **Wait for response**: If enabled, Drafts will wait for a callback response from a target app. See details above.
