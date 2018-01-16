---
title: Action Step – Google Drive
---
# Action Step: Google Drive

Create, append or prepend to files in [Google Drive](http://drive.google.com).

## Examples


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
