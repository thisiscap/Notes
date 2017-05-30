# Snippets related to MacOS

**Add spaces to the Dock**

- Open `Terminal`
- Write
  ```
  defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'
  ```
- Relaunch the Dock with `killall Dock`
