---
title: Credentials
---
# Credentials

Some services accessed via Drafts actions require authentication. In these cases, the first time the action is used Drafts will trigger then necessary authentication process and when successfully completed, store the credentials for reuse.

In most cases, these services use [OAuth](https://en.wikipedia.org/wiki/OAuth) and you will be redirected to the website for the service to provide your login and authorize Drafts. Drafts will store the token provided in these cases, and you will not need to enter your username and password directly in Drafts.

To log out of a service, visit *Settings > Credentials* in Drafts, and "Forget" the account you wish to remove.  If you use an action requiring this service again, you will be prompted to re-authenticate.

### Multiple Accounts

Action which use credentials have an optional "Identifier" field in their advanced options. If you are only using one account for a service, such as Dropbox or Twitter, this field can remain blank.  To have one or more actions target a second account, place a value in the "Identifier" field and any actions with the same identifier will use the same account.

The first time an action for that service, with a specific identifier, a new authentication process will be started - be sure to login to the proper account you wish to target in that process.

A common example use case for identifiers is to setup actions to target more than one Twitter account.
