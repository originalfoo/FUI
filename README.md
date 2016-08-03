# FUI - Factorio User Interface API

## Project Status

Early design phase

## Overview

FUI makes it significantly easier to implement a GUI (windows, dialogs, etc) for your Factorio mods.

A quick example of a FUI dialog:

```lua
Design
  '@dlgContent' [[
      label #msg 'dlg-label'
  ]]
  
  '@dlgButtons' [[
      button #cancel  'dlg-button-cancel' .btn-cancel
      button #confirm 'dlg-button-ok'     .btn-confirm
  ]]
  
local dlg = Dialog [[
  'Hello World'
  content @dlgContent
  buttons @dlgButtons
]]

dlg.on('close', function(eventName,eventData) {
  game.player.print eventData.button.caption -- localised caption of button clicked
}

dlg.show() -- defaults to local player (player 1)
```
