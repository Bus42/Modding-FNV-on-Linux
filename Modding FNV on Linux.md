# Modding Fallout: New Vegas on Linux

*This guide was written running Ubuntu Budgie 20.04.2 on a HP Elitebook 8740w (a laptop as old as FNV) with a 2.67ghz i7 processor, a 4GB NVIDIA Quadro M3000M mobile graphics card, 8ghz DDR3 RAM, and a RAID 0 setup utilizing two 7200 rpm HDD.*

I can run FNV at a consistent 50-60 fps. I do experience some frame drop in combat, down to 20-30 frames. If I can do that with this old machine, this should be a breeze for anyone running a more modern setup.

I will make the assumption that you do know enough to at least run the game on your distro. I have played FNV on Manjaro, Ubuntu KDE, GNOME, and Budgie, Mint, AntiX, MX Linux, and probably another I don't recall. Ubuntu Budgie, by far, was the most friendly to my combination of game engine, compatibility tool, and graphics card and ran with the least issues in and out of game.

I suggest keeping all of the files you download during setup in their own dowload folder outside of the wine prefix, such as `~/Downloads/Modding_FNV/` so if you ever need to do a clean install, it will be much easier to repeat this process.

## Install and setup Fallout: New Vegas through Steam.
+ After installing Fallout: New Vegas, restart Steam in offline mode.
+ Navigate to the library, right-click on **Fallout: New Vegas**, and select *Properties*.
+ In the **General** section, disable *Enable the Steam Overlay while in-game*.
+ In the **Compatibility** section, check *force the use of a specific Steam Play compatibility tool* and select **Proton 5.0-10** from the drop-down menu.
+ Launch FNV via Steam to perform first time setup.
    + In the FNV launcher menu, select **OPTIONS**.
    + Under the **Graphics Adapter and Resolution** section, disable *Anitialiasing* and *Anisotropic Filtering*.
    + Under the **Detail** section, click on **Advanced**.
    + Under the **Water** tab, disable *Water Displacement*.
    + If you're using a glorified toaster, you may want to go to the **Detail** tab and choose *Medium*  or, if you're using an actual potato, *Low*.

## Laying the groundwork for modding
1. Protontricks
2. FNV 4GB Patcher
3. NVSE
4. Vortex
5. FNVEdit/QuickAutoClean

### protontricks
+ Download [protontricks](https://github.com/Matoking/protontricks) and follow directions for installation.
+ Once installed, open the game folder by navigating to the library, right-clicking on Fallout: New Vegas and selecting **manage -> browse local files**. Right-click in your file manager window and select *open in terminal*. In the terminal, type ```protontricks --gui```. Keep the terminal open, you'll use it later.
    + In the **Choose Game** prompt, select **Fallout New Vegas** and click *ok*. Click-through any error messages that come up, they will not affect you.
    + When the Winetricks GUI opens, choose **select the default wineprefix** and click *ok*.
    + Choose **Install a windows DLL or component** and click *ok*.
    + Scroll down, select **dotnet462** and click *ok*. Click-through any error messages that come up, they will not affect you. You will be prompted several times during the installation of dependencies for dotnet462 with EULAs and such. This step will take a while, especially with a slower connection.
    + Once installation has finished, the Winetricks GUI will open again. Select *Cancel*, select *Cancel* again and exit the GUI.

### Vortex
+ Download [Vortex](https://www.nexusmods.com/site/mods/1?tab=description) from Nexus Mods.
+ Place the .exe file in your game folder.
+ Rename FalloutNVLauncher.exe to FalloutNVLauncher.bak
+ Rename Vortex*.exe to FalloutNVLauncher.exe
+ Launch Fallout: New Vegas through Steam and Vortex will install itself
### NVSE
+ Download [NVSE](http://nvse.silverlock.org/) - you will not run this one just yet.
### FNV 4GB Patcher
   + Download the [Microsoft Visual C++ Redistributable](https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0) from Microsoft support.
   + Copy the downloaded .exe file to your game folder.
   + In the terminal, which should still be open to the game directory, type `wine VC_redist.x86.exe`. The executable will install necesarry .dlls for running FNV 4GB Patcher.
   + Download [FNV 4GB Patcher](https://www.nexusmods.com/newvegas/mods/62552).
   + Copy the downloaded .exe file to your game folder.
   + Unpack the .zip file into a folder in the same directory, ie: `~/Downloads/Modding_FNV/4GBPatch/`.
   + Open **FNV4GB Readme.txt** and follow the directions in the *Running* section, run with wine the same as you did to run the Microsoft Visual C++ Redistributable.