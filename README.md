gen-keys
========

Node utility to scan all Atom editor packages and build key binding DB


**NOTE:** This project was removed because I discovered it was useless without my access token.  Contact me for questions.


## Node utility to scan all Atom editor packages and build key binding DB

gen-keys is a node utility (not an Atom package) that scans all published packages on Atom.io and builds a list of key bindings which is stored in a github gist. The data is retrieved from the first cson file in the keymaps folder.

The data is collected in an array with one `{packageName, downloads, scope, keystroke, command}` object for each binding.  The array is sorted by downloads, converted to json, and stored at https://gist.github.com/mark-hahn/a690a7d5ef746368385f#file-allkeybindings-json.

This gist data is used by the Atom package [search-all-keybindings](https://github.com/mark-hahn/search-all-keybindings).

This is meant to run daily by one user which will be me, Mark Hahn, for the foreseeable future.

## Usage
- clone repo `https://github.com/mark-hahn/gen-keys.git`
- edit first line of gen-keys.coffee file
  - change `corePackagesDir` variable to your core atom packages path
- cd into `gen-keys` directory
- on windows: enter `gen-keys`
- on non-windows: compile coffee file into lib folder and run JS file in node
  - coffee -co lib gen-keys.coffee
  - node lib\gen-keys.js
  

