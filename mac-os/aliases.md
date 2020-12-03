# Useful aliases for zshrc and or bash

Useful aliases to add to `zshrc` or `bash`

- Easier edits/additions in the future
  `alias config-edit="nano ~/.zshrc"` or `nano ~/.bashrc`
- Easily refresh Terminal with new config
  `alias config-refresh="source ~/.zshrc"` or `source ~/.bashrc`
- Keep Mac from going to sleep for an hour, useful for presentations
  `alias presentation="caffeinate -d -t 3600"`
- Find out what your current IP address
  `alias my-ip="curl ipinfo.io/ip"`
- Useful reminder of DNS lookup command
  `alias dns-lookup="echo Use 'host -a [domain]'"`
- Fire up a quick php server from a directory
  `alias sandbox="php -S localhost:2222"`
