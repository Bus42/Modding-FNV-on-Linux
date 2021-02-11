# Modding Fallout: New Vegas on Linux

*This guide was written running Ubuntu Budgie 20.04.2 on a HP Elitebook 8740w (a laptop as old as FNV) with a 2.67ghz i7 processor, a 4GB NVIDIA Quadro M3000M mobile graphics card, 8ghz DDR3 RAM, and a RAID 0 setup utilizing two 7200 rpm HDD.*

I can run FNV at a consistent 50-60 fps. I do experience some frame drop in combat, down to 20-30 frames. If I can do that with this old machine, this should be a breeze for anyone running a more modern setup.

## Install and setup Fallout: New Vegas through Steam.
+ After installation, restart steam in offline mode.
+ Navigate to the library in Steam after installation, right-click on **Fallout: New Vegas**, and select *Properties*.
+ In the **General** section, disable *Enable the Steam Overlay while in-game*.
+ In the **Compatibility** section, check *force the use of a specific Steam Play compatibility tool* and select **Proton 5.0-10** from the drop-down menu.
+ Launch FNV via Steam to perform first time setup
## Lay the groundwork with Protontricks, NVSE, and 4gb Patch
+ Install ProtonTricks from github `--->` [here](https://github.com/Matoking/protontricks) `<---` and follow directions for installation.
+ Once installed, open the game folder in your terminal application, type ```protontricks --gui```, choose *select the default prefix*, and click *ok*