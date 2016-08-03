# FUI - Factorio User Interface API

## Project Status

Early design phase

## Overview

FUI makes it significantly easier to implement a GUI (windows, dialogs, etc) for your Factorio mods.

A quick example of a FUI dialog:

```lua
Design
  '@dlgContent' [[
      label #msg 'dialog-label'
  ]]
  
  '@dlgButtons' [[
      button #cancel  'dialog-button-cancel' .btn-cancel
      button #confirm 'dialog-button-ok'     .btn-confirm
  ]]
  
local dlg = Dialog [[
  'Hello World'
  content @dlgContent
  buttons @dlgButtons
]]

dlg.on('close', function(eventName,eventData) {
  game.player.print eventData.button.caption
}

dlg.show()
```
