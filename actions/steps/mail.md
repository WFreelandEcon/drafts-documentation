---
title: Action Step – Mail
---
# Action Step: Mail

Send pre-configured email messages either using Mail.app or web services in the background.

## Examples

*(Open links on device with Drafts to install)*

- [Mail](drafts5://action?data=%7B%22uuid%22:%2297572F43-B478-4734-9ECC-32EB6B396C96%22,%22steps%22:%5B%7B%22type%22:%22mail%22,%22data%22:%7B%22sendInBackground%22:%22false%22,%22ccRecipients%22:%22%22,%22toRecipients%22:%22%22,%22bccRecipients%22:%22%22,%22sendAsHTML%22:%22false%22,%22subjectTemplate%22:%22%5B%5Btitle%5D%5D%22,%22bodyTemplate%22:%22%5B%5Bbody%5D%5D%22%7D,%22uuid%22:%227FD9F5F9-505F-415C-89FE-DDF6FFD6A84D%22%7D%5D,%22shortName%22:%22%22,%22shouldConfirm%22:false,%22disposition%22:3,%22keyCommand%22:%7B%22optionKey%22:false,%22input%22:%22%22,%22controlKey%22:false,%22commandKey%22:false,%22type%22:%22action%22,%22discoverabilityTitle%22:%22Mail%22,%22shiftKey%22:false%7D,%22logLevel%22:2,%22notificationType%22:2,%22tintColor%22:%22indigo%22,%22actionDescription%22:%22%22,%22keyUseIcon%22:false,%22icon%22:%22action_email_filled%22,%22visibility%22:2,%22supportedPlatform%22:%22any%22,%22groupDisposition%22:0,%22name%22:%22Mail%22%7D)
- [Markdown Mail](drafts5://action?data=%7B%22uuid%22:%22B1EE61CE-AA84-415B-A5F9-C66CCEB0600F%22,%22steps%22:%5B%7B%22type%22:%22mail%22,%22data%22:%7B%22sendInBackground%22:%22false%22,%22ccRecipients%22:%22%22,%22toRecipients%22:%22%22,%22bccRecipients%22:%22%22,%22sendAsHTML%22:%22true%22,%22subjectTemplate%22:%22%5B%5Btitle%5D%5D%22,%22bodyTemplate%22:%22%25%25%5B%5Bbody%5D%5D%25%25%22%7D,%22uuid%22:%2288EF3DF8-129F-4DD0-BA64-CE9FEF82503F%22%7D%5D,%22shortName%22:%22%22,%22shouldConfirm%22:false,%22disposition%22:3,%22keyCommand%22:%7B%22optionKey%22:false,%22input%22:%22%22,%22controlKey%22:false,%22commandKey%22:false,%22type%22:%22action%22,%22discoverabilityTitle%22:%22Markdown%20Mail%22,%22shiftKey%22:false%7D,%22logLevel%22:2,%22notificationType%22:2,%22tintColor%22:%22gray%22,%22actionDescription%22:%22%22,%22keyUseIcon%22:false,%22icon%22:%22action_email_filled%22,%22visibility%22:2,%22supportedPlatform%22:%22any%22,%22groupDisposition%22:0,%22name%22:%22Markdown%20Mail%22%7D)

## Options

- **Recipients**: Comma separated list of recipient emails for each of the recipient types. These can be just email address, or "Name <email>" formatted - like "Joe Smith <joe@smith.com>, Jane Doe <jane@doe.com>".
  - **To**
  - **CC**
  - **BCC**
- **Subject**: Template for the subject line.
- **Body**: Template for content of the message. If "Send as HTML" is enabled, this template is expected to output valid HTML, otherwise plain text.
- **Send as HTML**: If enabled, the mail is sent as formatted HTML email and the body template should output fully formed HTML. The most common use of this option is to run Markdown to HTML conversion to get rich-text mail.  In this case the simple template "%%[[body]]%%" can be used.
- **Send in background**: If enabled, the mail will be sent using a web service instead of Mail.app. This does not require user interaction, but recipients must be pre-configured and the email will come addressed "From: drafts5@drafts5.agiletortoise.com". This is best suited for "Email to myself", or to send to services which provide a dedicated unique incoming email address as a dropbox.
