---
title: Changelog
---
# Changelog

#### v0.1.1.47

- **New:** Watch app. I have some other plans for it, but it is currently a port of the updated D4 watch app. Not super well tested, but I think it mostly works. Going to run it through the paces myself this weekend.  Will circle back on it and add Siri and some other planned features soon.  I made a couple UI flips just to make it distinguishable from the D4 watch app.
- **Change:** Darken blue icon sets slightly.
- **Fix:** Do not ask for Siri access if Siri is disabled.
- **Fix:** Do not start displaying drawers when scrolling a long tag list.
- **Change:** If focus is dismissed from tag entry field without assigning tag, clear the field.
- **Fix:** Do not warn about invalid callback url if the source action step did not have "Wait for response" enabled.
- **Fix:** VO labels for pin button not updated for status.
- **Fix:** A few layout issues on the little phones.

#### v0.1.1.46

- **New:** "Insert Text" action step. [Docs](https://agiletortoise.github.io/drafts-documentation/actions/steps/inserttext)
- **Fix:** Fixes for a few odd configuration bits in the default action set.  These will not re-install automatically.
- **Change:** Capture and warn about invalid links in HTML preview.
- **Change:** Open valid links in HTML Previews using Safari View Controller instead of the preview window itself.

#### v0.1.1.45

- **Change:** Action groups and action export files are now in compressed binary format. This works better for sharing, downloading, etc. - in addition to being a space-saver for backups, etc. - and users don't get confronted with a wall of JSON which scares them. At least that's what I'm hoping.  Still need to test more.
- **Change:** Port D4's RTL language support.
- **New:** Template tag helper keyboard row. Probably not done yet, but it's something.
- **New:** Include Action step type. Works like the D4 version.
- **New:** Draft script object "languageGrammar" property to read/write the preferred syntax for the draft.
- **New:** `editor.focus()` method to return focus to the editor. Useful if an action takes focus to display other UI (like a prompt) and you would like to return to editing mode.
- **Change:** A few tweaks in the default action groups.
- **Fix:** Action group backup was being a bit too agressive about ensuring the safety of your Action Groups.
- **Change:** More tweaks to javascript editing and syntax highlighting.
- **New:** Google Drive action step.  May still be a bit buggy, but should mostly work. [Docs](https://agiletortoise.github.io/drafts-documentation/actions/steps/googledrive)
- **New:** "Edit on draft selection" setting (default: true) in Appearance settings. Controls whether tapping a draft in the draft list immediately focuses the draft for editing.
- **New:** Prompt script object now has `addPasswordField(name, label, initialText)` method.
- **Fix:** Crash calling reminder.addAlarm() without any parameters.
- **New:** Improvements to Javascript grammar, especially handling comments.
- **New:** Some basic indentation support in Javascript editing.
- **Change:** Default light theme was underlining tasks.
- **Change:** Begin edit on cold start of app.
- **Change:** Script editor should respect javascript editing attributes configured in editor.
- **New:** `Drafts.recentTags()` scripting object. Useful for building prompts to select a tag.
- **Fix:** Scrolling jumping around after scripting call that updated text (like setSelectedText()).
- **Fix:** Automatic list completion could cause jumping around in longer drafts.
- **Change:** General improvements to display of prompts and dialogs, but style and animation.
- **Fix:** "Auto-correct" selection was not being saved in Editor settings properly.
- **Fix:** Smart quote and smart dash toggle where not working if you enabled them. They do now. If you like that kind of thing.
- **New:** Launch screen revisions.
- **Fix:** Optional not getting unwrapped flipped to a new dictation session when one expires leaving extraneous characters.
- **New:** Lots of works on IAPs, subs, pitch screens, etc., that you won't actually see yet.
- **New:** Some work on fleshing out Siri vocabularies. "Capture a note using Drafts", "Dictate a note with Drafts" should trigger correct intent now.

#### v0.1.1.42

- **New:** Work on the on-boarding process.  If you delete and reinstall you will get the first launch experience. Design is not done, but it will on-board an initial set of actions and keys now.  The on-boarding sets up a "Basic" actions group with some common actions, and also loops over a set of actions for popular apps (like OmniFocus, Fantastical, Things, Tweetbot, Ulysses, etc.) and sets up actions in the Basic list for those apps *IF* the user has that app installed on the device.  This process updates status in iCloud, so the groups will not be re-created on a new install if the user already has been through it on another device, or in a previous install.
- **New:** Arrange mode is now available from a text selection popover menu to arrange only the current selected lines, instead of the full text of the draft.
- **New:** Scripting changes:
    - app.version: Return current version number of Drafts.
    - `device` object for access to model, os version, battery level. Useful for scripting actions which behave differently on iPad/iPhone, etc. 1[Docs](https://github.com/agiletortoise/drafts-documentation/wiki/Device)
- **Fix:** Dialogs and prompts could clip longer message texts.
- **Fix:** Enabling Reminder import should request Reminder permissions if they have not already been granted.
- **Change:** Add syntax coloring for ES6 Template literals to javascript language grammar.
- **Change:** Updated to blue app icons.
- **Change:** Change default app icon to gradient blue variant.
- **Fix:** "List in Reminders" action could fail to finish properly.

#### v0.1.1.41

- **New:** Dialogs and prompts support keyboard interaction now.  Tab or down arrow, or Shift-tab or up arrow move been selections.  Enter to select the current button.
- **Fix:** Keyboard shortcut (CMD-0) to show actions would hide draft list, but not move main view back if drawer was pinned.
- **Fix:** You should not be able to delete the "no steps" placeholder row in the action editing.
- **New:** Callback URL steps now create template tags for each parameter returned in an x-success callback from the target app, in the format `[[callback_parameter]]`. These values are still available via script as well.
- **New:** Run Workflow steps now create a template tag for the result returned in an x-success callback from the Workflow, with the name `[[workflow_result]]`. These values are still available via script as well.

#### v0.1.1.40

- **New:** Mail action step supports "Send in background".  The "Use Markdown" option has been removed in favor of the more generic "Send as HTML". [Docs](https://agiletortoise.github.io/drafts-documentation/actions/steps/mail)
- **New:** Mail script object has "sendInBackground" property, and, well, can send in background. [Docs](https://github.com/agiletortoise/drafts-documentation/wiki/Mail)
- **New:** /create, /append and /prepend URLs can now take "tag=..." parameters to attach tags to the draft. [Docs](https://agiletortoise.github.io/drafts-documentation/urls/)
- **Change:** Shrink size of icons on keys a little.
- **Change:** Make tag and action group slide-overs a little wider.
- **New:** A few more action icons in the Editor category.
- **Fix:** Notification settings should copy with an action if it's copied/moved.

#### v0.1.1.39

- **Change:** More reworking of keyboard selection.  It's back at the start of the keyboard row, but will scroll with the keys.
- **Fix:** Inability to select a keyboard if one had not already been selected in the installation.
- **Change:** Rewrote url query parameter coding based on AlamoFire implementation, instead of old C one. Hopefully doesn't break anything.
- **Change:** Move arrange mode access to keyboard selection view (with find-replace).
- **Fix:** Clean up more funky behaviors after cancelling a drawer show animation.
- **Fix:** Crash using URL step set to use Safari with non-http(s) URL.
- **Fix:** Drawers should not dismiss when editing started if pinned.
- **Fix:** JavaScript language grammar handles multiline comments properly now.
- **Fix:** JavaScript language grammar handles regex literals.
- **Fix:** Changes to share extension template would only be saved the first time they were edited.
- **Fix:** Navigating action list by using up-down arrows would not properly highlight the selected row.
- **New:** Add "show" option to reveal tag selection if the recent tags list is empty at the bottom of draft list.
- **Fix:** Some fields which show keyboard in Settings were not picking up the dark keyboard for dark themes.

#### v0.1.1.38

- **Change:** Try "Manage keyboards" ... button at the end of the scrolling key row.  Can't promise it will stay there, but worth a try.
- **Fix:** A proper fix (workaround, really) for the double drawer animation weirdness.
- **Change:** Refactored task identifiers and enabling to language grammar definitions. Task marks are now only enabled in Markdown grammar.
- **Fix:** Tags on current draft would not update in editor if changed in script.
- **Change:** Display improvements to recent drafts widget.  Implement pro only mode.

#### v0.1.1.37

- **New:** "Callback URL" action step. Similar to Open URL, but appends x-callback-url parameters and can wait for a response from the target app - with result parameters being available subsequent script steps. [Details in the docs](https://agiletortoise.github.io/drafts-documentation/actions/steps/callbackurl)
- **Change:** "Run Workflow" action steps supports same callback system as new Callback URL step - allowing Drafts to wait for the result of a workflow, to be used in subsequent script steps. [Docs](https://agiletortoise.github.io/drafts-documentation/actions/steps/runworkflow)
- **New:** context script object adds "callbackResponses" object to access parameters returned by x-callback-url call using Callback URL or Run Workflow steps which "Wait for response". [Docs](https://github.com/agiletortoise/drafts-documentation/wiki/Context)
- **Fix:** Probably with animations getting confused by poor gesture timing making both side drawers visible.

#### v0.1.1.36

- **New:** TextExpander support. Basically the same as in D4, with a few notes:
    - TE Settings/refresh are now under a separate screen in Settings.
    - Fill-in snippets are not supported.
    - TE snippets work in the Share extension.
    - Expansion in action templates is supported for shortcuts wrapped in << >> as in D4.
- **New:** Additional and updated App icon options (in Aa view).
- **New:** A couple more categories of action icons from the Symbolicon set.
- **Fix:** "Restore" button in version history works now.
- **Fix:** Drawer interactions will now cancel if directly of swipe is reversed.
- **Fix:** Updated drawer interactions for tags in draft list and groups in action list to match fixes in the other drawer interactions.
- **Fix:** Maybe(?) a fix for case where swiping to left on action in action list could show "Delete" option instead of triggering groups drawer.

#### v0.1.1.35

- **Fix:** Main glitches in Backup features introduced yesterday. Most of the failures were due to file naming conflicts.
- **Change:** Support `application/x-www-form-urlencoded` params in HTTP request with new setting option for encoding - defaults to `application/json`.  [Docs](https://github.com/agiletortoise/drafts-documentation/wiki/HTTP)

#### v0.1.1.34

- **New:** On-demand and automated periodic backups of Drafts and Action Groups to iCloud Drive - configured in Settings > Backup. Currently the periodic interval is set to 7 days when enabled. [Docs](https://agiletortoise.github.io/drafts-documentation/settings/backups)
- **New:** Mostly finished up Share extension. Append/Prepend available now.
- **Fix:** Performance issue with external keyboard.
- **Fix:** Disable iPhone X input accessory resizing with external keyboard, because of text drop issue.
- **Change:** Update Dropbox action icon to their new logo shape.
- **Fix:** URL encode Workflow name in Run Workflow action.
- **Fix:** Crash after using date formatted template tags in a prompt action step.
- **Fix:** When drawer is visible and pinned, do not grab up-down arrow key from editor.
- **Fix:** Share extension template not saving in settings.

#### v0.1.1.32

- **New:** Run Workflow action step.
- **New:** Swipe up or down on extended keyboard row to swap between available keyboards.
- **New:** Sharing action or action group now offers the option to share as URL or File.
- **Change:** Refactored drawer animations and gestures.
- **Fix:** Theme problem on share extension settings page.
- **Fix:** Custom implementations of cut and copy commands to force plain text.
- **Fix:** Case where quick select buttons for action groups could point to invalid groups and not do anything.
- **Fix:** Make sure action group buttons are updated when switching groups.
- **New:** Scripting:
    - Reminder object now has priority property [Docs](https://github.com/agiletortoise/drafts-documentation/wiki/Reminder)
    - app.openURL(url) now can take optional boolean param to open in Safari View Controller. [Docs](https://github.com/agiletortoise/drafts-documentation/wiki/App)
- **Fix:** Allow a little more padding for key if icon and label are shown to avoid clipping.
- **Fix:** /append URL was, actually, prepending.
- **New:** "Play sounds" setting to disable/enable UI and notification sounds.

#### v0.1.1.30

- **Fix:** Workaround for glitching display when pasting text into editor.

#### v0.1.1.29

- **New:** Share extension (no append-prepend yet) and related settings.
- **Fix:** Importing action group should not add "(copy)" in action names.
- **Change:** Better activity indication on tapped actions.
- **New:** Misc. UI tweaks, added haptics, etc.

#### v0.1.1.27

!!! IMPORTANT: Before installing this build, you will have to delete and previous builds on the device, or it will crash on launch due to underlying data changes. Sync should restore your data, if it was enabled prior to the deletion, but not a bad idea to back up.

- **Fix:** Problem in persisting drafts which could generate a duplicate of the draft in the database when certain timing scenarios were hit.
- **New:** Conflict recognition for incoming sync changes when occuring to the same draft loaded in the editor.
- **Fix:** Action groups now refresh (in list and keyboard) when changes are made to the group, either via manage screens or sync.  This means you should not have to reload keyboards and or the action list to pick up changes.
- **Change:** On new installs, if iCloud is available, enable sync by default.

#### v0.1.1.26

- **New:** Actions in the action list are now drop targets for anything that can provide text.  Drag one or more text snippets, text files, drafts to an action and it will be queued and run for each item.
- **Fix:** A variety of storage issues with the new editor settings changes.
- **Fix:** Do not add "(copy)" to action names when importing.
- **New:** Add selectionStart and selectionLength properties to draft script object.
- **New:** Improved editing of action in a group when accessed in Manage screen - including options to duplicate, move actions and drag and drop reordering.
- **Change:** Adjust sidebar pane sizes.

#### v0.1.1.25

- **New:** Refactored editor settings by syntax.  All the text related settings (font, size, autocorrect, etc.) are stored separately by syntax and automatically changed when you change syntax - so you can have different fonts and behaviors for Markdown and Javascript, for example.  These are synced to iCloud, but by device - so they will restore from iCloud if reinstalled, but can be different on iPhone and iPad.
- **Fix:** Misc. fixes/improvements to syntax highlighting, especially in Markdown.
- **Fix:** Crasher passing invalid text ranges to some editor script methods.
- **New:** Mail and Message script steps now have contact selection option to insert recipients.
- **New:** /arrange URL scheme to use arrange mode with external apps/services.
- **New:** `editor.find()` and `editor.arrange()` methods to display arrange and find modes.

#### v0.1.1.24

- **Fix:** [[selection]] tag did not default to full contents if there was no selection.
- **Fix:** Possible threading gap that could allow a duplicate draft to be created if the timing was just right running an action.

#### v0.1.1.23

- **New:** Recent tag quick access list at bottom of draft list.
- **New:** Recent action group quick access list at the bottom action list.
- **New:** Groups now all appear in the action list sidebar.  Individual groups can be configured with "Available as keyboard" option to also make them visible in the keyboard selector.  A variety of related changes around this also.
- **New:** Add sync activity indicator at top of draft list.
- **Change:** A variety of visual fixes and improvements around the app.
- **New:** Actions now have "use icon" option to display the action's icon on keyboard keys.

#### v0.1.1.21

- **New:** "Recent Drafts" today widget.
- **New:** Dropbox scripting object allows read/write of files in Dropbox via script. (see: https://github.com/agiletortoise/drafts-documentation/wiki/Dropbox)
- **New:** Enhancements to Draft scripting object, including... (details: https://github.com/agiletortoise/drafts-documentation/wiki/Draft)
    - isArchived, isFlagged, isTrashed properties.
    - `find(uuid)` to retrieve existing draft by UUID.
    - `query(query, filter, tags)` method to query and return a list of matching drafts.
- **New:** `alert(msg);` script method to show a simple alert dialog.
- **Fix:** Re-enable some of the Script Editor settings which got disabled by accident in last build.
- **Change:** Styling improvement in action step editing.
- **New:** Start to include summarys in action step list for some types of steps.
- **Fix:** Layout glitch editing clipboard action step.
- **Fix:** Recent drafts available via 3D Touch should not include drafts in trash.
- **Fix:** HTML Preview display issue on iOS 11.2 (same issue Script Editor had).
- **Fix:** Tag keyboard helper suggestions getting clipped.

#### v0.1.1.20

- **Fix:** Script editor now displays properly on 11.2 devices.
- **Fix:** undo/redo were not working due to extra call to registerUndo points.
- **Change:** Build with iOS 11.2 b2 SDK on Xcode 9.2b2

#### v0.1.1.19

- Scripting changes (details on Wiki: https://github.com/agiletortoise/drafts-documentation/wiki):
    - **New:** Calendar and Event scripting objects to create calendar events.
    - **New:** "context" object in scripts with cancel and fail calls to stop execution of additional steps.
    - **New:** "action" object in scripts to query current action information and find actions by name.
    - **New:** `app.queueAction(action, draft)` method to queue and action to run after the current action.
    - **Change:** Moved "getClipboard" and "setClipboard" methods from editor to app object. They make more sense there.
    - **New:** `app.htmlToClipboard(html)` method. Takes HTML and converts it to rich-text in the clipboard - compatible with pasting into most rich-text apps (Mail, Pages, etc.).
- **Fix:** Clean up of a few styling issues in settings screens.
- **Change:** Contrast tweaks in dark theme.

#### v0.1.1.18

- **New:** Prompt action step type. Works just like in D4.
- **New:** Clipboard action step now supports append/prepend.
- **New:** Export operation in drafts list to export selected drafts.
- **New:** Export feature in Settings to export json or csv dumps of drafts.
- **Change:** "Operations" in draft list should error if no drafts are selected.
- **Fix:** Fix URL encoding of line feeds.
- **Fix:** Better handling of clearing tags from the list when no remaining drafts are assigned to a tag.
- **Change:** Hide tag shelf if draft list is hidden.
- **Change:** Hide action group shelf if action list hidden.
- **New:** FileManager.createLocal() and FileManager.createCloud() convenience methods.

#### v0.1.1.17

- **Fix:** Sync issues preventing edits of existing drafts from syncing properly.
- **Fix:** A couple of crashing issues in template evaluation, particularly of {{ }} url encoding.  Most recursive URLs should work now, but "AllowEmpty" doesn't do anything as of now, so they might end back in the target app.
- **Fix:** Issue with duplicate insert which could hang sync.
- **Fix:** Dropbox append/prepend would fail if file did not already exist.
- **Fix:** ||clipboard|| tag in incoming URLs should become blank string if nothing is in clipboard.
- **Fix:** Running action from keyboard would not properly save changes to the draft before running.
- **New:** Trash is now swept leaving only the last 7 days of drafts when the app is sent to the background.

#### v0.1.1.16

- **New:** "File" action step type to create/append/prepend to files in either the Local app storage or iCloud Drive.
- **New:** FileManager script object. This allows reading from and writing to files in both the Drafts' local documents directory (visible in Files.app) or iCloud Drive (in "Drafts5" folder).
    - [FileManager docs](https://github.com/agiletortoise/drafts-documentation/wiki/FileManager)
- **Change:** Improve visibility of sidebar pinning buttons when available (mainly on iPad)
- **Fix:** Custom template tags defined in scripts were not being evaluated properly.
- **Fix:** Attempt to create Reminder objects in script should request Reminders access permissions if not already granted.

#### v0.1.1.15

- **New:** Prompt scripting object for creation and display of prompt dialogs with custom text input and buttons (see docs: https://github.com/agiletortoise/drafts-documentation/wiki/Prompt)
- **Fix:** Tapping on the draft in Siri after using "Create note using Drafts..." properly opens the new draft now.
- **Fix:** Crash deleting action step if it was the only action step in the action.
- **Fix:** If draft loaded in editor is moved to the trash, start a new draft.
- **Fix:** Search button from widget now works.
- **Fix:** /search URL scheme now works. Supports query and new "tag" arguments.
- **Fix:** Set the app badge to 0 using the old API because Apple's new API doesn't work for 0 because ??
- **New:** Custom template tags defined by "draft.setTemplateTag(name, value)" javascript calls are not evaluated in templates properly.
- Laying some groundwork for the watchOS app in the underlying frameworks.

#### v0.1.1.14

- **New:** Work on URL schemes.  Most of the same URLs supported by D4 should work now, just with the drafts5: scheme.
- **Change:** Tweaks to Find and Replace view.
- **Change:** Theme preview improvements.
- **New:** "Copy to Drafts" file imports work now.
- **Change:** Switch to sharing and import of Action Groups and Actions using URL (in leiu of files) for better compatibility.
- **New:** Fill in a few more missing action icons.

#### v0.1.1.13

- **New:** List auto-completion for Markdown and TaskPaper language grammars.
- **New:** Alternate app icons available in Appearance settings.  Preliminary set, options may change.
- **New:** Reminders import functionality. Can be configured in Settings.
- **Fix:** Actions with "use default" dispositions did not always properly inherit the disposition setting of their action group.
- **Change:** Some Script Editor changes for better flow.  Syntax checker warning symbol added.

#### v0.1.1.12

- **New:** Reminder action step.
- **New:** List in Reminders action step.
- **New:** Reminder and Reminder list scripting interfaces, including alarms. Details in wiki...
    - [Reminder](https://github.com/agiletortoise/drafts-documentation/wiki/Reminder)
    - [ReminderList](https://github.com/agiletortoise/drafts-documentation/wiki/ReminderList)
    - [Alarm](https://github.com/agiletortoise/drafts-documentation/wiki/Alarm)
- **Change:** Disable landscape support on iPhone, at least for now.
- **Change:** Fix up some visual inconsistencies across views.
- **Change:** Insert custom popover view background class for better styling.
- **New:** Expand theming to buttons and action tint colors.
- **Fix:** Modifications to the draft currently in editor from the draft list (archiving, etc.) could get lost when editor re-saved draft.

#### v0.1.1.11

- **Fix:** Deleting action steps did not work properly.
- **New:** Added template tag and processTemplate methods to draft object in scripting (Details: https://github.com/agiletortoise/drafts-documentation/wiki/Draft)
- **Fix:** Script methods on editor object which change text should register undo points so the change can be reverted with undo.
- **Fix:** Change to draft content in action script might not be loaded in the editor.
- **Fix:** Extended keyboard should reload action group after changes are made in the "Manage" screen.
- **Fix:** List indentations for ordered lists in Markdown language grammar did not indent wrapped lines properly.
- **Fix:** Deleting actions in manage groups views did not work properly.
- **Fix:** Some encoding issues for certain characters posting to twitter.

#### v0.1.1.10

- **Change:** Sync can now be enabled in Settings - can't promise I won't clear data, however.
- **Change:** Tweak momentum for drawer gestures a little.
- **Change:** Make "Get info" keyboard shortcut opt-cmd-I to avoid conflict with italics.
- **Change:** Default draft list sort order to "modified" on new install.
- **New:** HTML Preview action step type.
- **Fix:** Add title to step editing views.
- **New:** Tweaks to recent tag suggestions, including way to clear recent list.
- **Fix:** Prevent keyboard shortcuts from interferring with other views (like Script Editor)
- **Change:** Keyboard shortcut for "Enter" in draft list should hide draft list.
- **New:** Incorporate Date.js library into Scripting context for easy date parsing/manipulation (http://www.datejs.com)
- **Change:** Improve display of table view separators.
- **New:** "Remove tag" operation in draft list.
- **Change:** Build with Xcode 9.1 against 11.1 SDK.
