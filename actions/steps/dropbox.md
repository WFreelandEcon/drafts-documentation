---
title: Action Step – Dropbox
---
# Action Step: Dropbox

Create, append or prepend to files in [Dropbox](http://dropbox.com).

## Examples


## Options

- **Name**: Template for file name, including extension.
- **Path**: Path of folder, relative to Dropbox root, to place file. Default "/" is the root of your Dropbox folder.
- **Template**: Template for the content of the file.
- **Write Type**:
  - **create**: Create a new file. If an existing file already exists at the location, create as new file with a number suffix added.
  - **replace**: Create new file, overwriting an existing if it exists.
  - **prepend**: Prepend template content at the beginning of the file. Create the file if it does not already exist.
  - **append**: Append template content at the end of the file. Create the file if it does not already exist.
- **Identifier**: A string identifier for the Dropbox account to use. This value is only needed if you wish to use more than one Dropbox account with Drafts. If used, all actions with the same identifier will use the same alternate login for Dropbox.
