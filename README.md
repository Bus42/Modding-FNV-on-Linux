# Modding Fallout: New Vegas on Linux

*This guide was written running Ubuntu Budgie 20.04.2 on a HP Elitebook 8740w (a laptop as old as FNV) with a 2.67ghz i7 processor, a 4GB NVIDIA Quadro M3000M mobile graphics card, 8ghz DDR3 RAM, and a RAID 0 setup utilizing two 7200 rpm HDD.*


+ *I recently changed to Kubuntu 20.04 on the same machine, but I changed my drive setup and mounted my secondary HDD to `/home/<user>/Steam_Games/`, so now all of my Steam installs are on a separate drive. This also helps to separate drive read/write tasks so if I'm downloading something to ~/Downloads (on /dev/sda2) in the background, it doesn't affect the read/write speed of my Steam games (on /dev/sdb1)*

I can run FNV at a consistent 50-60 fps. I do experience some frame drop in combat, down to 20-30 frames. If I can do that with this old machine, this should be a breeze for anyone running a more modern setup. I acheived this using NMC's small texture pack, Ojo Bueno's texture pack, and Wasteland Weather

I will make the assumption that you do know enough to at least run the game on your distro. I have played FNV on Manjaro, Ubuntu KDE, GNOME, and Budgie, Mint, AntiX, MX Linux, and probably another I don't recall. Ubuntu Budgie, by far, was the most friendly to my combination of game engine, compatibility tool, and graphics card and ran with the least issues in and out of game.

I suggest keeping all of the files you download during setup in their own dowload folder outside of the wine prefix, such as `~/Downloads/Modding_FNV/` so if you ever need to do a clean install, it will be much easier to repeat this process.

## Install and setup Fallout: New Vegas through Steam.
+ After installing Fallout: New Vegas, restart Steam in offline mode.
+ Navigate to the library, right-click on **Fallout: New Vegas**, and select *Properties*.
+ In the **General** section, disable *Enable the Steam Overlay while in-game*.
+ In the **Compatibility** section, check *force the use of a specific Steam Play compatibility tool* and select **Proton 4.11-13** from the drop-down menu.-
+ Launch FNV via Steam to perform first time setup.
    + In the FNV launcher menu, select **OPTIONS**.
    + Under the **Graphics Adapter and Resolution** section, disable *Anitialiasing* and *Anisotropic Filtering*.
    + Under the **Detail** section, click on **Advanced**.
    + Under the **Water** tab, disable *Water Displacement*.
    + If you're using a glorified toaster, you may want to go to the **Detail** tab and choose *Medium*  or, if you're using an actual potato, *Low*.

## Laying the groundwork for modding
1. Protontricks
3. NVSE
2. FNV 4GB Patcher
4. Vortex
5. FNVEdit/QuickAutoClean

### protontricks
+ Download [protontricks](https://github.com/Matoking/protontricks) and follow directions for installation. Depending on your Linux distro, this may require installation of Winetricks. Winetricks can be installed by typing `sudo apt-get install -y winetricks`.
+ Once installed, open the game folder by navigating to the Steam library, right-clicking on Fallout: New Vegas and selecting **manage -> browse local files**. Right-click in your file manager window and select *open in terminal*. In the terminal, type `protontricks --gui`. Keep the terminal open, you'll use it later.
    + In the **Choose Game** prompt, select **Fallout New Vegas** and click *ok*. Click-through any error messages that come up, they will not affect you.
    + When the Winetricks GUI opens, choose **select the default wineprefix** and click *ok*.
    + Choose **Install a windows DLL or component** and click *ok*.
    + Scroll down, select **dotnet462** and click *ok*. Click-through any error messages that come up, they will not affect you. You will be prompted several times during the installation of dependencies for dotnet462 with EULAs and such. This step will take a while, especially with a slower connection.
    + Once installation has finished, the Winetricks GUI will open again. Select *Cancel*, select *Cancel* again and exit the GUI.

### NVSE
+ Download [New Vegas Script Extender](http://nvse.silverlock.org/), unzip and extract all files into the game folder

### FNV 4GB Patcher
   + Download the [Microsoft Visual C++ Redistributable](https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0) from Microsoft support.
        + In the terminal, which should still be open to the game directory, type `wine vcredist_x86.exe`. The executable will install necesarry .dlls for running FNV 4GB Patcher.
   + Download [FNV 4GB Patcher](https://www.nexusmods.com/newvegas/mods/62552).
        + Copy the downloaded .exe file to your game folder.
        + Unzip and copy `fnv4gb.exe` and `fnv4-gb_helper.dll` file to your game folder.
        + Open a terminal in the game folder and type `wine fnv4gb.exe`, it will patch the executable and launch the game.
        + Once the game has loaded up at the main menu, press the tilde key to open the console, then type `GetNVSEVersion` to verify installation of NVSE.

### FNVEdit
+ Download [FNVEdit](https://www.nexusmods.com/newvegas/mods/34703)
+ Extract and copy everything but the text files into your game folder. We'll get back to this one.

### Wrye Flash
+ Download [Wrye Flash](https://www.nexusmods.com/newvegas/mods/35003)
+ Extract and copy the `data` and `mopy` folders into your game folder. The executable is located in the `mopy` folder. We'll get back to this one as well.

### Vortex
+ Download [Vortex](https://www.nexusmods.com/site/mods/1?tab=description) from Nexus Mods.
+ Place the .exe file in your game folder.
+ Rename `FalloutNVLauncher.exe` to `FalloutNVLauncher.bak`
+ Rename `Vortex*.exe` to `FalloutNVLauncher.exe`
+ Launch Fallout: New Vegas through Steam and Vortex will install itself. Vortex will likely pop up a warning about admin rights, ignore it.
+ Once Vortex launches, click **Log in or Register** and authorize Nexus Mods, create an account if you need to - it will come in handy and really helps to support the mod authors by being able to provide feedback or contribute support.
+ On your Vortex dashboard, click on **Select a game to manage** in the *Let's Get You Set Up* section. Scroll down and you will see Fallout: New Vegas, hover over it and click *Manage*. If prompted for access, give permission.
+ In your notifications, you will see a warning that NVSE is not installed, click on this to automatically dowload and install 
+ Toggle **Archive Invalidation** on by clicking on the corresponding button in the *Let's get you set up" section of the dashboard.
+ You may get prompted for permission to edit Fallout.ini. If so, click *Give Permission*.
+ You will get a warning that "Loose files may not get loaded", click *fix*.
+ Dismiss the notification about download links, they never worked for me.
+ If prompted to restart to update extensions, do so.
+ Launch Fallout: New Vegas, check that your settings are where you want them, then exit.
+ Update the filenames and locations for your tools (FNVEdit and Wrye Flash) by clicking on the dots on the side of the respective buttons. You can find the file path by right-clicking on one of the tools in your game folder and selecting *properties*. From there you can copy and paste the file name and path into Vortex using keyboard shortcuts to paste (no mouse right-click menu). The correct format should be `z:` + `/home/<user>/..path/to/file` + `/` + `tool.exe`