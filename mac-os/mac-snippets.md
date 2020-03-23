# Snippets related to MacOS

## Add spaces to the Dock

- Open `Terminal`
- Write `defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'`
- Relaunch the Dock with `killall Dock`

## Turn off, or on, the start-up chime

- Open `Terminal`
- Write `sudo nvram SystemAudioVolume=%80`
- Restart Mac
- To restore it, use `sudo nvram -d SystemAudioVolume`

## Show, and hide, hidden files (as of MacOS Sierra)

- Open `Finder`
- Press `cmd shift .`
  
## Prevent Mac from going to sleep, during presentations for example

- Open `Terminal`
- Type `caffeinate`
    
## Disable drop shadows on window screenshots
    
- Open `Terminal`
- Write `defaults write com.apple.screencapture disable-shadow -bool TRUE`
- Then `killall SystemUIServer`

[Source](https://matthewpalmer.net/blog/2018/04/14/ultimate-pro-guide-best-secret-mac-features/index.html#match-the-desktop-background-colour-to-the-dark-menu-bar)
