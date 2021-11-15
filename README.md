| Languages |
| --- |
| **en**, [ru](./lang/ru/) |

# How to use Hammer++ with Garry's Mod

## Why did I create this?
The answer is pretty simple... I hate myself. No, but really I saw a lot of people struggling to install Hammer++ itself but they had more problems with installing it for Garry's Mod, so this is a way I found to make it work.

## Requirments
- Computer running Windows 10 (20H2) or newer
- [7-Zip](https://www.7-zip.org/)
- [Garry's Mod](https://store.steampowered.com/app/4000/Garrys_Mod/)
- Source Games
	- [Counter-Strike: Source](https://store.steampowered.com/app/240/CounterStrike_Source/)
	- [Half-Life 2](https://store.steampowered.com/app/220/HalfLife_2/)
	- [Half-Life 2: Deathmatch](https://store.steampowered.com/app/320/HalfLife_2_Deathmatch/)
	- [Half-Life 2: Episode One](https://store.steampowered.com/app/380/HalfLife_2_Episode_One/)
	- [Half-Life 2: Episode Two](https://store.steampowered.com/app/420/HalfLife_2_Episode_Two/)
	- [Half-Life 2: Lost Coast](https://store.steampowered.com/app/340/HalfLife_2_Lost_Coast/)
	- (Optional) [INFRA](https://store.steampowered.com/app/251110/INFRA/)
- Source SDK 2013 Multiplayer
- (Optional) [Slammin' Tools](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ)
- [Hammer++](https://ficool2.github.io/HammerPlusPlus-Website/index.html)

## How to install requirments?
In this tutorial I assume you have Garry's Mod as well as all the source games I have mentioned installed and also 7-Zip installed.

### How to install Source SDK 2013 Multiplayer
1. Navigate to your steam library and make sure you have tools checked in your filters
2. Open `UNCATEGORIZED` category and find `Source SDK 2013 Multiplayer`
3. Click on `INSTALL` button then on `NEXT` and wait for it to download
![Image 1](./images/1.png)
4. **YOU MUST RUN HAMMER FROM SOURCE SDK 2013 MULTIPLAYER NOW BEFORE CONTINUING** (Steps below explain how to do this)
5. Right click on `Source SDK 2013 Multiplayer` and hover over `Manage` and then click `Browse local files`
![Image 2](./images/2.png)
6. Navigate into `bin` folder and double click `hammer.exe`, small window should pop out, choose `Half-Life 2`
7. When hammer opens and fully initializes, close it
![Image 3](./images/3.png)

### (Optional) How to install Slammin' Tools?
**Slammin' Tools are not neccessery but are good thing to have especially if you are compiling Statua's maps.**

1. Navigate to this [link](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ) and and download file ending with `.7z`
![Image 4](./images/4.png)
2. Once downloaded, open archive and drag and drop the files into `bin` folder of `Source SDK 2013 Multiplayer` (it will ask you if you want to override some files and you have to click yes)
![Image 5](./images/5.png)
![Image 6](./images/6.png)
3. Now repeat step `6` and `7` of installing `Source SDK 2013 Multiplayer`

## Installing and configuring Hammer++
Now without any more bullshitting as I already hate myself to the point of punching myself in the face, we get to grand finale which is installing and configuring Hammer++.

### Installing
1. Navigate to this [link](https://ficool2.github.io/HammerPlusPlus-Website/pages/download.html) and download for version for `Source SDK 2013 Multiplayer`
![Image 7](./images/7.png)
2. Once downloaded, open archive and navigate inside folder you see and into `bin` folder inside then drag and drop the files into `bin` folder of `Source SDK 2013 Multiplayer`
![Image 8](./images/8.png)
![Image 9](./images/9.png)
3. Now repeat step `6` and `7` of installing `Source SDK 2013 Multiplayer`

### Configuring
This part of the tutorial will be written only, so read it carefully and every step written here is very important.

1. Navigate into root folder of `Source SDK 2013 Multiplayer` and open folder named `hl2`
2. Open `gameinfo.txt` with the editor of your choice
3. You will add those lines to your `gameinfo.txt`, **Don't forget to change "<Steam's common folder>" to proper path**
```
// Game contents
game				"<Steam's common folder>/Counter-Strike Source/cstrike/cstrike_pak.vpk"
game				"<Steam's common folder>/Half-Life 2/episodic/ep1_pak.vpk"
game				"<Steam's common folder>/Half-Life 2/ep2/ep2_pak.vpk"
game				"<Steam's common folder>/Half-Life 2/lostcoast/lostcoast_pak.vpk"
game				"<Steam's common folder>/Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
game				"<Steam's common folder>/infra/infra/pak01.vpk"
game				"<Steam's common folder>/GarrysMod/garrysmod/garrysmod.vpk"
```
You add them after those lines:
```
// Where the game's binaries are
gamebin				hl2/bin
platform			|all_source_engine_paths|platform
```
Those lines mount contents from source games, list goes as follow
- Counter-Strike:Source
- Half-Life 2: Episode One
- Half-Life 2: Episode Two
- Half-Life 2: Lost Coast
- Half-Life 2: Deathmatch
- Infra
- Garry's Mod

4. Now navigate into root folder of `Source SDK 2013 Multiplayer` and then into bin folder
5. Double click `hammerplusplus.exe` and when small window appear you have to choose `Half-Life 2`, yes you won't be adding `Garry's Mod` into that list
6. Once hammer is open you have to open `Tools` dropdown and from there choose `Options...`
7. New window will appear, click on `Game Configurations` and you will see small button `Add` click it
8. Navigate into your `Garry's Mod` root folder and then into `bin` folder and find there file called `garrysmod.fgd` and load it
9. Click on the `2D Views` tab and in `Options` section tick everything in the right column
10. In `Build Programs` tab you are going to change path of `Game executable` to `<Garry's Mod root folder>/hl2.exe`
11. In `Build Programs` tab you are going to change path of `Maps Folder` to `<Garry's Mod root folder>/garrysmod/maps`
12. In `Hammer++` disable Anisotropic Filtering

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
			
			// Some game contents
			game				"F:/Steam/steamapps/common/Counter-Strike Source/cstrike/cstrike_pak.vpk"
			game				"F:/Steam/steamapps/common/Half-Life 2/episodic/ep1_pak.vpk"
			game				"F:/Steam/steamapps/common/Half-Life 2/ep2/ep2_pak.vpk"
			game				"F:/Steam/steamapps/common/Half-Life 2/lostcoast/lostcoast_pak.vpk"
			game				"F:/Steam/steamapps/common/Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
			game				"F:/Steam/steamapps/common/infra/infra/pak01.vpk"
			game				"F:/Steam/steamapps/common/GarrysMod/garrysmod/garrysmod.vpk"

			// Other contents
			// game				"<location>"
		}
	}
}

```

## Last words
Now you are ready to use Hammer++ and it should work. The only problem you have is that you have to double mount contents as hammer++ does not support Garry's Mod mounting way for now. So if you are using hammer++ you are most propably familiar with `mount.cfg` of gmod, so to mount content into hammer++ you have to mount it in `gameinfo.txt` you edited earlier and add right after those lines you added earlier `game "<path to your content>"`. If you think that I could improve something then messege me on github or you can ping me on discord (ParSec#4563) on [Statua Mapping](https://discord.gg/3Uq4WKNRuF) server, I do recommend you drop by and say hello, a lot of people there can help you with a lot of your problems.

Now if you don't mind I'm gonna shoot myself in the face.
Oh and I couldn't forget about you CoolGuy for asking me everyday the same question when will I make it and reminding me how disorganized I am.
