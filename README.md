# My Shared Compendia

A Foundry VTT module to share Data between worlds via compendia.

This is a forked version for my personal use

## Installation

1. Go to the Add-on Modules tab within the FoundryVTT Configuration and Setup page.
2. Click the `Install Module` button.
3. Paste the Module's [Manifest URL](https://github.com/stschoelzel/My-Shared-Compendia/releases/download/v1.2.0/module.json)
   into the `Manifest URL` field.
4. Click the `Install` button.

| WARNING: If you update this module, FoundryVTT will erase your compendia. |
| ------------------------------------------------------------------------- |

### Preventing Module Update

- Option 1 (easier): Locking your module:
  1. Go to the Add-on Modules tab within the FoundryVTT Configuration and Setup page.
  2. Find this module (My Shared Compendia) in the list, and click the padlock icon.
     - Unlocked:  
       ![unlocked-module](resources/images/unlocked-module.webp)
     - Locked:  
       ![locked-module](resources/images/locked-module.webp)
- Option 2: Updating your `module.json` file:
  1. Go to the Module's installation folder within foundry (`~/Data/modules/My Shared Compendia`) and update the `module.json` file.
  2. Remove lines 68-69 (`download` and `manifest`) and save the file.
  3. Restart Foundry to reload the module.

### Unlock your Compendia!

_Remember_ that you need to unlock your compendia to be able to add things to them.

## Default Setup

This module comes with 13 Default compendia:

- `Actors (shared)` ([Actor](https://foundryvtt.com/article/actors/))
- `Items (shared)` ([Item](https://foundryvtt.com/article/items/))
- `Journal Entries (shared)` ([JournalEntry](https://foundryvtt.com/article/journal/))
- `Macros (shared)` ([Macro](https://foundryvtt.com/article/macros/))
- `Playlists (shared)` ([Playlist](https://foundryvtt.com/article/playlists/))
- `Roll Tables (shared)` ([RollTable](https://foundryvtt.com/article/roll-tables/))
- `Scenes (shared)` ([Scene](https://foundryvtt.com/article/scenes/))

## Adding a new system

To change the default setup, edit the `module.json` file. All compendia are defined within the "packs" attribute beginning with line 18. You'll need to add a new one for each 

For example (you should replace <insert system id> with the id of the system you want to add):

```json
  {
      "name": "actors<insert system id>",
      "label": "Actors (shared)",
      "system": "<insert system id>",
      "path": "./packs/actors<insert system id>.db",
      "module": "my-shared-compendia",
      "type": "Actor"
    },
    {
      "name": "items<insert system id>",
      "system": "<insert system id>",
      "label": "Items (shared)",
      "path": "./packs/items<insert system id>.db",
      "module": "my-shared-compendia",
      "type": "Item"
    },
```

## Dependencies
- Using [Compendium Folders](https://github.com/earlSt1/vtt-compendium-folders) is highly recommended.
- Actors and Items will only work for systems which have been added.

## When uploading module
1) Download code as zip (name module)
2) Extract zip
3) Move files from module/My-Shared-Compendia to module
4) delete resources folder
5) delete original zip
6) compress module folder to zip
7) upload the new module.zip (from step 6) and the module.json when creating the release (drag and drop to attach binaries... section)
