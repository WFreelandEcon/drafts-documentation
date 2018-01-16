---
title: Action Step – Google Drive
---
# Action Step: Google Drive

Create, append or prepend to files in [Google Drive](http://drive.google.com).

## Examples

- [Save to Google Drive](drafts5://action?data=%7B%22uuid%22:%22C5E39021-0F06-4156-8038-635F2C59D191%22,%22steps%22:%5B%7B%22type%22:%22googleDrive%22,%22data%22:%7B%22writeType%22:%22create%22,%22folderTemplate%22:%22%22,%22oauthIdentifier%22:%22%22,%22template%22:%22%5B%5Bdraft%5D%5D%22,%22fileNameTemplate%22:%22%5B%5Btime%5D%5D%22%7D,%22uuid%22:%2282121098-28B4-4786-BDA2-F5C3272FC1C4%22%7D%5D,%22shortName%22:%22%22,%22shouldConfirm%22:false,%22disposition%22:3,%22keyCommand%22:%7B%22optionKey%22:false,%22input%22:%22%22,%22controlKey%22:false,%22commandKey%22:false,%22type%22:%22action%22,%22discoverabilityTitle%22:%22Save%20to%20Google%20Drive%22,%22shiftKey%22:false%7D,%22logLevel%22:2,%22notificationType%22:2,%22tintColor%22:%22red%22,%22actionDescription%22:%22Save%20to%20a%20timestamped%20file%20in%20the%20root%20of%20Google%20Drive.%22,%22keyUseIcon%22:false,%22icon%22:%22action_google_drive%22,%22visibility%22:2,%22supportedPlatform%22:%22any%22,%22groupDisposition%22:0,%22name%22:%22Save%20to%20Google%20Drive%22%7D)
- [Append to Google Drive Journal](drafts5://action?data=%7B%22uuid%22:%22F1A04325-7CCC-4B8E-9AA0-7950D848C602%22,%22steps%22:%5B%7B%22type%22:%22googleDrive%22,%22data%22:%7B%22writeType%22:%22append%22,%22folderTemplate%22:%22%22,%22oauthIdentifier%22:%22%22,%22template%22:%22%23%23%20%5B%5Bcreated%5D%5D%5Cn%5B%5Bdraft%5D%5D%5Cn%22,%22fileNameTemplate%22:%22Journal-%5B%5Bdate%7C%25Y-%25m%5D%5D%22%7D,%22uuid%22:%224ECFBD7E-2619-4EF7-AA7C-00B13B6DD013%22%7D%5D,%22shortName%22:%22%22,%22shouldConfirm%22:false,%22disposition%22:3,%22keyCommand%22:%7B%22optionKey%22:false,%22input%22:%22%22,%22controlKey%22:false,%22commandKey%22:false,%22type%22:%22action%22,%22discoverabilityTitle%22:%22Append%20to%20Google%20Drive%20Journal%22,%22shiftKey%22:false%7D,%22logLevel%22:2,%22notificationType%22:2,%22tintColor%22:%22green%22,%22actionDescription%22:%22Append%20timestamp%20and%20draft%20contents%20to%20rolling%20monthly%20Journal%20file%20in%20the%20root%20of%20Google%20Drive.%22,%22keyUseIcon%22:false,%22icon%22:%22action_google_drive%22,%22visibility%22:2,%22supportedPlatform%22:%22any%22,%22groupDisposition%22:0,%22name%22:%22Append%20to%20Google%20Drive%20Journal%22%7D)

## Options

- **Name**: Template for file name, including extension.
- **Parent**: Leave blank for root level of Google Drive, or include the name of a folder in the root level of Google Drive. The folder will be created when the action is run if it does not already exist.
- **Template**: Template for the content of the file.
- **Write Type**:
  - **create**: Create a new file. If an existing file already exists at the location, create as new file with a number suffix added.
  - **replace**: Create new file, overwriting an existing if it exists.
  - **prepend**: Prepend template content at the beginning of the file. Create the file if it does not already exist.
  - **append**: Append template content at the end of the file. Create the file if it does not already exist.
- **Identifier**: A string identifier for the Google Drive account to use. This value is only needed if you wish to use more than one account with Drafts. If used, all actions with the same identifier will use the same alternate login for Google Drive.
