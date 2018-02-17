# Snippets related to Firefox on Mac OS (and Windows)

**Disable zoom when scrolling with meta/config**

- Open new tab with `about:config` in the url
- Search for
  ```
  mousewheel.with_meta.action
  or
  mousewheel.with_control.action
  ```
- Double click and change value to `1`

**Disable zoom when pinching**

- Open new tab with `about:config` in the url
- Search for
  ```
  browser.gesture.pinch.in
  and
  browser.gesture.pinch.out
  ```
- Double click and change value to `null`

**Keep tab bar open when in Fullscreen mode**
- Open new tab with `about:config` in the url
- Search for
  ```
  browser.fullscreen.autohide
  ```
- Set to `false`
