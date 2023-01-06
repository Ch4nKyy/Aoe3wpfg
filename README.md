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

## How to develop

Visual Studios XAML designer can help you, but it also requires some trial and error ingame.

### Setup

* Clone project
* Use ResourceManager (0.5.0) to extract all .bars inside Age3/Game/UI and put the output into
aoe3wpfg/resources.
* Build the solution with Visual Studio (requires WPF Desktop Development)
* Ingame use the Definitive UI!

### Routine

* Open xaml in designer view
* Do some changes
* Copy uimainnew.xaml to
  ```C:\Users\user\Games\Age of Empires 3 DE\playerID\mods\local\SC2UI\data\wpfg\uimainnew.xaml```
* The game reloads the UI, when you restart the match.

### When Age3 gets an update

Age3 DE might get updates that add UI features that will be missing in the UI mod.

* Extract the current xamls from Game/UI/UI.bar
* Compare the diff between the extracted uimainnew.xaml and aoe3wpfg/uimainnew_orig.xaml
  * (Formatting both files to match indents can help minimizing the diff)
* Add new features to aoe3wpfg/uimainnew.xaml
* Copy xaml like usual to mod folder

## Troubleshooting

* Designer says "BitmapImage initialization is not complete. Call the EndInit method to complete
the initialization."  
-> Files in /resources are missing.

* Some exceptions and "Invalid markup" is caused by URI sources starting with
"pack://siteoforigin:,,,/resources/" or "resources/". It should always be "/resources/..."!
