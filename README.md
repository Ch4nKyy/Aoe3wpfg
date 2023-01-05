# AOE3wpfg

Changes the Age3 DE HUD so that the layout matches SC2/WC3.  
* Minimap bottom left
* Timer bottom left
* Idle bottom left
* Command bar bottom right
* Resources bar top right

The project includes all kinds of xaml, but I only edit uimainnew.xaml to change the ingame HUD.  
The HUD is based on the Classic HUD (uimainnew_legacy.xaml) with some elements from the Definitive
HUD (uimainnew.xaml). However, for the mod, uimainnew.xaml MUST be used, because otherwise some
UI images are not loaded by the game!

## How to setup

* Clone project
* Use ResourceManager (0.5.0) to extract all bars inside Age3/Game/UI and put the output into
aoe3wpfg/resources.
* Build the solution with Visual Studio
* Open xaml in designer view

## How to update

Age3 DE might get updates that add UI features that will be missing in the UI mod.

* First, compare the new official UI and the modded UI by:
  * Extracting the new xamls from Game/UI/UI.bar
  * Formating both files to match indents, so the diff is minimal
  * Compare diff
  * Please note that even when nothing was added, there will be a diff, because of the UI elements
    I moved around
* Add missing stuff
* Overwrite
C:\Users\user\Games\Age of Empires 3 DE\playerID\mods\local\SC2UI\data\wpfg\uimainnew.xaml

## Troubleshooting

* Designer says "BitmapImage initialization is not complete. Call the EndInit method to complete
the initialization."  
-> Files in /resources are missing.

* Some exceptions and "Invalid markup" is caused by URI sources starting with
"pack://siteoforigin:,,,/resources/" or "resources/". It should always be "/resources/..."!
