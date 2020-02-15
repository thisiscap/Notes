# Snippets related to MacOS

**Add spaces to the Dock**

- Open `Terminal`
- Write
  ```
  defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'
  ```
- Relaunch the Dock with `killall Dock`

**Turn off, or on, the start-up chime**

- Open `Terminal`
- Write
  ```
  sudo nvram SystemAudioVolume=%80
  ```
- Restart Mac
- To restore it, repeat process but with this in `Terminal`
  ```
  sudo nvram -d SystemAudioVolume
  ```

  **Show, and hide, hidden files**

  - Open `Finder`
  - Press
    ```
    cmd shift .
    ```
