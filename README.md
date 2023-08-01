| Languages |
| --- |
| **en**, [ru](./lang/ru/), [pt-br](./lang/pt-br/), [fr](./lang/fr/)|

# How to use Hammer++ with Garry's Mod

## Why did I create this?
The answer is pretty simple... I hate myself. No, but really I saw a lot of people struggling to install Hammer++ itself but they had more problems with installing it for Garry's Mod, so this is a way I found to make it work.

## Requirements:
- A computer running Windows
- [7-Zip](https://www.7-zip.org/)
- [Garry's Mod](https://store.steampowered.com/app/4000)
- Source Games
	- [Counter-Strike: Source](https://store.steampowered.com/app/240)
	- [Half-Life 2](https://store.steampowered.com/app/220)
	- [Half-Life 2: Deathmatch](https://store.steampowered.com/app/320)
	- [Half-Life 2: Episode One](https://store.steampowered.com/app/380)
	- [Half-Life 2: Episode Two](https://store.steampowered.com/app/420)
	- [Half-Life 2: Lost Coast](https://store.steampowered.com/app/340)
	- (Optional) [INFRA](https://store.steampowered.com/app/251110)
	- (Optional) [Black Mesa](https://store.steampowered.com/app/362890)
- Source SDK 2013 Multiplayer
- (Optional) [Slammin' Tools](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ)
- [Hammer++](https://ficool2.github.io/HammerPlusPlus-Website/index.html)

**About Windows versions compatibility**  
Hammer++ requires the Windows operating system to function properly, as Valve's support for other operating systems is limited, making Hammer++ unavailable for platforms other than Windows. Although no specific versions are officially designated, I have personally tested Hammer++ on Windows 10 Pro versions 20H2 build 19042.928 up to the latest available version at the time of writing, Windows 10 Pro version 21H2 build 19044.1526.
Since publishing this guide nearly a year ago, other users have reported successful installations of Hammer++ on various Windows versions, including Windows 11.

## How do I install the requirements?
In this tutorial, it is assumed that you already have Garry's Mod and all the mentioned source games installed on your system. Additionally, make sure you have 7-Zip or any other file archiver of your choice installed for extracting the necessary files.

### How to install Source SDK 2013 Multiplayer
1. Go to your Steam library and make sure the "Tools" option is checked in your search filters.
2. Look for `Source SDK 2013 Multiplayer` in the `UNCATEGORIZED` category, or simply search for it.
3. Click on the `INSTALL` button, then click `NEXT`, and wait for the download to complete.
![Image 1](./images/1.png)
4. **IMPORTANT: RUN HAMMER FROM SOURCE SDK 2013 MULTIPLAYER NOW BEFORE CONTINUING** (Follow the steps below to do this)
5. Right-click on `Source SDK 2013 Multiplayer`, hover over `Manage`, and select `Browse local files`.
![Image 2](./images/2.png)
6. Go to the `bin` folder and double-click on `hammer.exe`. A small window should appear, where you need to choose `Half-Life 2`.
7. Once Hammer opens and fully initializes, close it.
![Image 3](./images/3.png)

### (Optional) How to install Slammin' Tools?
**While not necessary, Slammin' Tools can be beneficial to have, particularly when compiling Statua's maps.**

1. Navigate to this [link](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ) and download the file ending with `.7z`
![Image 4](./images/4.png)
2. After the download is complete, open the archive and drag and drop the files into the `bin` folder of `Source SDK 2013 Multiplayer` (When prompted, choose to override the files by clicking "Yes.")
![Image 5](./images/5.png)
![Image 6](./images/6.png)
3. Now repeat steps `6` and `7` of installing `Source SDK 2013 Multiplayer`

## Installing and configuring Hammer++
Finally, we reach the grand finale, which involves installing and configuring Hammer++.

### Installing
1. Go to this [link](https://ficool2.github.io/HammerPlusPlus-Website/pages/download.html) and download the version of Hammer++ made for `Source SDK 2013 Multiplayer`.
![Image 7](./images/7.png)
2. After the download is complete, open the downloaded archive. Inside the folder you see, go into the `bin` folder, and then drag and drop the files from there into the `bin` folder of `Source SDK 2013 Multiplayer`.
![Image 8](./images/8.png)
![Image 9](./images/9.png)
3. Now repeat step `6` and `7` of installing `Source SDK 2013 Multiplayer`

### Configuring
This part of the tutorial will be text only, so read it very carefully as every step written here is very important.

1. Navigate into the root folder of `Source SDK 2013 Multiplayer` and open the folder named `hl2`.
2. Open `gameinfo.txt` with a text editor of your choice.
3. You're gonna need to add these lines into your `gameinfo.txt`. **Don't forget to change "<Steam's common folder>" to the proper path!**
Example: [link](https://github.com/RealParSec/realparsec.github.io/blob/master/README.md#example-gameinfotxt)

```
// Source games content
game				"<Steam's common folder>/GarrysMod/garrysmod/garrysmod.vpk"
game				"<Steam's common folder>/Half-Life 2/episodic/ep1_pak.vpk"
game				"<Steam's common folder>/Half-Life 2/ep2/ep2_pak.vpk"
game				"<Steam's common folder>/Half-Life 2/lostcoast/lostcoast_pak.vpk"
game				"<Steam's common folder>/Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
game				"<Steam's common folder>/Counter-Strike Source/cstrike/cstrike_pak.vpk"
game				"<Steam's common folder>/infra/infra/pak01.vpk"

// Black Mesa content - the last time I checked it was a bit buggy in hammer++ and caused it to crash
game				"<Steam's common folder>/Black Mesa/bms/bms_materials.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_models.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_sound_vo_english.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_sounds_misc.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_textures.vpk"
```

You add them after those lines:

```
// Where the game's binaries are
gamebin				hl2/bin
platform			|all_source_engine_paths|platform
```

These lines mount contents from source games, list goes as follows:
- Garry's Mod
- Counter-Strike: Source
- Half-Life 2: Episode One
- Half-Life 2: Episode Two
- Half-Life 2: Lost Coast
- Half-Life 2: Deathmatch
- Infra
- Black Mesa

4. Navigate to the root folder of `Source SDK 2013 Multiplayer` and then into the `bin` folder.
5. Double-click on `hammerplusplus.exe`, and a small window will appear. Choose `Half-Life 2` from the options list. Note that you won't be adding `Garry's Mod` to the list.
6. Once Hammer++ is open, go to the `Tools` dropdown and select `Options...`
7. In the new window that appears, click on `Game Configurations`, and you'll see a small button labeled `Add`. Click it.
8. Navigate to your `Garry's Mod` root folder, then go into the `bin` folder, and locate the file named garrysmod.fgd. Load this file.
9. Click on the `2D Views` tab, and in the `Options` section, check all the options in the right column.
10. In the `Build Programs` tab, update the path of `Game executable` to `<Garry's Mod root folder>/hl2.exe`.
11. In the `Build Programs` tab, change the path of `Place compiled maps in this directory before running the game` to `<Garry's Mod root folder>/garrysmod/maps`.
12. In `Hammer++`, disable Anisotropic Filtering.

## Example `gameinfo.txt`

```
"GameInfo"
{
	game 		"HALF-LIFE 2"
	title 		"HALF-LIFE'"
	type		singleplayer_only
	supportsvr	1

	FileSystem
	{
		SteamAppId				220		// This will mount all the GCFs we need (240=CS:S, 220=HL2).
		
		//
		// The code that loads this file automatically does a few things here:
		//
		// 1. For each "Game" search path, it adds a "GameBin" path, in <dir>\bin
		// 2. For each "Game" search path, it adds another "Game" path in front of it with _<langage> at the end.
		//    For example: c:\hl2\cstrike on a french machine would get a c:\hl2\cstrike_french path added to it.
		// 3. For the first "Game" search path, it adds a search path called "MOD".
		// 4. For the first "Game" search path, it adds a search path called "DEFAULT_WRITE_PATH".
		//

		//
		// Search paths are relative to the base directory, which is where hl2.exe is found.
		//
		// |gameinfo_path| points at the directory where gameinfo.txt is.
		// We always want to mount that directory relative to gameinfo.txt, so
		// people can mount stuff in c:\mymod, and the main game resources are in
		// someplace like c:\program files\valve\steam\steamapps\half-life 2.
		//
		SearchPaths
		{
			// First, mount all user customizations.  This will search for VPKs and subfolders
			// and mount them in alphabetical order.  The easiest way to distribute a mod is to
			// pack up the custom content into a VPK.  To "install" a mod, just drop it in this
			// folder.
			//
			// Note that this folder is scanned only when the game is booted.
			game+mod			hl2/custom/*

			// We search VPK files before ordinary folders, because most files will be found in
			// VPK and we can avoid making thousands of file system calls to attempt to open files
			// in folders where they don't exist.  (Searching a VPK is much faster than making an operating
			// system call.)
			game_lv				hl2/hl2_lv.vpk
			game+mod			hl2/hl2_sound_vo_english.vpk
			game+mod			hl2/hl2_pak.vpk
			game				|all_source_engine_paths|hl2/hl2_textures.vpk
			game				|all_source_engine_paths|hl2/hl2_sound_misc.vpk
			game				|all_source_engine_paths|hl2/hl2_misc.vpk
			platform			|all_source_engine_paths|platform/platform_misc.vpk

			// Now search loose files.  We'll set the directory containing the gameinfo.txt file
			// as the first "mod" search path (after any user customizations).  This is also the one
			// that's used when writing to the "mod" path.
			mod+mod_write+default_write_path		|gameinfo_path|.

			// Add the HL2 directory as a game search path.  This is also where where writes
			// to the "game" path go.
			game+game_write		hl2

			// Where the game's binaries are
			gamebin				hl2/bin

			// Last, mount in shared HL2 loose files
			game				|all_source_engine_paths|hl2
			platform			|all_source_engine_paths|platform

			// Source games
			game				"|all_source_engine_paths|../GarrysMod/garrysmod/garrysmod.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/episodic/ep1_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/ep2/ep2_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/lostcoast/lostcoast_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
			game				"|all_source_engine_paths|../Counter-Strike Source/cstrike/cstrike_pak.vpk"
			game				"|all_source_engine_paths|../infra/infra/pak01.vpk"

			// Black Mesa content - last time I checked a bit buggy in hammer++ and caused hammer++ to crash
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_materials.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_models.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_sound_vo_english.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_sounds_misc.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_textures.vpk"


			// Other contents
			// game				"E:/gmod/maps/rp_riverden/content/"
		}
	}
}
```
## Fin
Now you are ready to use Hammer++ and it should work as expected. However, there's a slight inconvenience as Hammer++ doesn't support the Garry's Mod mounting method. To address this, you'll need to double mount the content. Since you are likely familiar with the `mount.cfg` of Garry's Mod, you can achieve this by mounting the content directly into the `gameinfo.txt` file you edited earlier. Add the line `game "<path to your content>"` right after the lines you previously added.

If you have any suggestions for improvement or encounter any issues, feel free to reach out to me on GitHub. Alternatively, you can ping me on Discord at ParSec#4563 on the [Statua Mapping](https://discord.gg/3Uq4WKNRuF) server. I highly recommend you drop by and say hello; there are many helpful people there who can assist you with various problems.
