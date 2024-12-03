# thunderbird_userChrome
userChrome.css for changing thread tree colors and some icons in folder pane.
Tested on Betterbird 115.10.0-bb27 on Mac OS Sequoia 15.1.1.

## Changing icons for given folders
To change the icon for a given folder proceed as follows:
  1. open `Developer Tools`
  2. look for your folder name, you should see something like this:
     ```html
     <li xmlns="http://www.w3.org/1999/xhtml" is="folder-tree-row" id="FOLDER_ID" [...] title="00 - EVENTI">
     ```
  3. copy `FOLDER_ID` and add a block which looks like the following:
     ```css
     #folderTree li[id="FOLDER_ID"] > .container > .icon {
        background-image: url("chrome://messenger/skin/icons/new/compact/calendar.svg") !important;
     }
     ```
  4. replace `calendar.svg`with your icon, choosing among one of those listed in `chrome://messenger/skin/icons.css`
