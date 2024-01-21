| Languages |
| --- |
| [en](/../../), [ru](/../../lang/ru/), [pt-br](/../../lang/pt-br/), **fr**|

## Comment utiliser Hammer++ avec Garry's Mod

## Pourquoi ai-je créé ceci ?
La réponse est assez simple... Je me déteste. Non, mais en réalité, j'ai vu beaucoup de gens galérer pour installer Hammer++ lui-même, mais ils avaient plus de problèmes à l'installer pour Garry's Mod, donc ce guide a un moyen que j'ai trouvé pour le faire fonctionner.

## Vous avez besoin de :
- Un ordinateur équipé de Windows
- [7-Zip](https://www.7-zip.org/)
- [Garry's Mod](https://store.steampowered.com/app/4000)
- Jeux "Source"
	- [Counter-Strike: Source](https://store.steampowered.com/app/240)
	- [Half-Life 2](https://store.steampowered.com/app/220)
	- [Half-Life 2: Deathmatch](https://store.steampowered.com/app/320)
	- [Half-Life 2: Episode One](https://store.steampowered.com/app/380)
	- [Half-Life 2: Episode Two](https://store.steampowered.com/app/420)
	- [Half-Life 2: Lost Coast](https://store.steampowered.com/app/340)
	- (Optional) [INFRA](https://store.steampowered.com/app/251110)
	- (Optional) [Black Mesa](https://store.steampowered.com/app/362890)
- Source SDK 2013 Multiplayer
- (Optionnel) [Slammin' Tools](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ)
- [Hammer++](https://ficool2.github.io/HammerPlusPlus-Website/index.html)

**Compatibilité des versions Windows**  
Windows est nécessaire pour exécuter Hammer++, comme d'autres OS ne sont pas entièrement pris en charge par Valve ainsi Hammer n'est pas disponible pour tout autre OS que Windows. Quand il s'agit de versions spécifiques, il n'y en a pas, je l'ai personnellement testé sur Windows 10 Pro version 20H2 build 19042.928 et toutes les versions jusqu'à Windows 10 Pro version 21H2 build 19044.1526 (étant la version la plus récente disponible publiquement au moment d'écrire ceci). Ceci étant dit, depuis que j'ai publié ce guide il y a presque un an, des personnes l'ont suivi et ont réussi à l'installer sur de nombreuses versions différentes de Windows, y compris Windows 11.



## Comment installer la configuration requise ?
Dans ce tutoriel, je suppose que vous avez Garry's Mod ainsi que tous les jeux sources que j'ai mentionnés installés et également 7-Zip installé.

### Comment installer Source SDK 2013 Multiplayer
1. Naviguez dans votre bibliothèque steam et assurez-vous que vous avez coché `OUTILS` dans vos filtres de recherche.
2. Ouvrez la catégorie `SANS CATEGORIE` et trouvez `Source SDK 2013 Multiplayer`, ou bien recherchez-le simplement.
3. Cliquez sur le bouton `INSTALLER` puis sur `SUIVANT >` et attendez qu'il se télécharge.
![Image 1](../images/fr/1.png)
4. **Vous devez exécuter HAMMER DU SOURCE SDK 2013 MULTIPLAYER MAINTENANT AVANT DE CONTINUER** (Les étapes ci-dessous expliquent comment faire)
5. Faites un clic droit sur `Source SDK 2013 Multiplayer`, survolez `Gérer` et cliquez ensuite sur `Parcourir les fichiers locaux`.
![Image 2](../images/fr/2.png)
6. Naviguez dans le dossier `bin` et double-cliquez sur `hammer.exe`. Une petite fenêtre devrait apparaître, choisissez `Half-Life 2` à partir de là.
7. Lorsque Hammer s'ouvre et s'initialise complètement, fermez-le.
![Image 3](../images/3.png)

### (Facultatif) Comment installer Slammin' Tools ?
**Slammin' Tools n'est nécessaire mais c'est une bonne chose à avoir, surtout si vous compilez les cartes de Statua.**

1. Allez sur ce [lien](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ) et téléchargez le fichier se terminant par `.7z`.
![Image 4](../images/fr/4.png)
2. Une fois téléchargé, ouvrez l'archive, glissez et déposez les fichiers dans le dossier `bin` de `Source SDK 2013 Multiplayer` (Il vous sera demandé si vous voulez remplacer certains fichiers, cliquez sur oui).
![Image 5](../images/5.png)
![Image 6](../images/6.png)
3. Maintenant répétez les étapes `6` et `7` de l'installation du `Source SDK 2013 Multiplayer`.

## Installation et configuration Hammer++
Maintenant, sans dire plus de conneries, car je me déteste déjà au point de me frapper dans le visage, nous arrivons à la grande finale qui est l'installation et la configuration de Hammer++.

### Installation
1. Allez sur ce [lien](https://ficool2.github.io/HammerPlusPlus-Website/download.html) et téléchargez la version du `Source SDK 2013 Multiplayer`.
![Image 7](../images/7.png)
2. Une fois téléchargé, ouvrez l'archive, naviguez dans le dossier que vous voyez et dans le dossier `bin` à l'intérieur, glissez et déposez les fichiers dans le dossier `bin` de `Source SDK 2013 Multiplayer`.
![Image 8](../images/8.png)
![Image 9](../images/9.png)
3. Maintenant, répétez les étapes 6 et 7 de l'installation de `Source SDK 2013 Multiplayer`.

### Configuration
Cette partie du tutoriel ne sera que du texte, lisez-la donc très attentivement car chaque étape écrite ici est très importante.

1. Naviguez dans le dossier racine de `Source SDK 2013 Multiplayer` et ouvrez le dossier nommé `hl2`.
2. Ouvrez `gameinfo.txt` avec un éditeur de texte de votre choix.
3. Vous allez devoir ajouter ces lignes dans votre `gameinfo.txt`, **n'oubliez pas de changer "<Dossier common de Steam>" par le bon chemin! (chemin vers `Steam/steamapps/common`)**.
Exemple : [lien](https://github.com/RealParSec/realparsec.github.io/blob/master/README.md#example-gameinfotxt)

```
// Source games content
game				"<Steam's common folder>/GarrysMod/garrysmod/garrysmod.vpk"
game				"<Steam's common folder>/Half-Life 2/episodic/ep1_pak.vpk"
game				"<Steam's common folder>/Half-Life 2/ep2/ep2_pak.vpk"
game				"<Steam's common folder>/Half-Life 2/lostcoast/lostcoast_pak.vpk"
game				"<Steam's common folder>/Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
game				"<Steam's common folder>/Counter-Strike Source/cstrike/cstrike_pak.vpk"
game				"<Steam's common folder>/infra/infra/pak01.vpk"

// Black Mesa content - last time I checked a bit buggy in hammer++ and caused hammer++ to crash
game				"<Steam's common folder>/Black Mesa/bms/bms_materials.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_models.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_sound_vo_english.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_sounds_misc.vpk"
game				"<Steam's common folder>/Black Mesa/bms/bms_textures.vpk"
```

Vous ajoutez cela apres ces lignes

```
// Where the game's binaries are
gamebin				hl2/bin
platform			|all_source_engine_paths|platform
```

Ces lignes ajoutent le contenu des jeux sources, la liste est la suivante
- Garry's Mod
- Counter-Strike: Source
- Half-Life 2: Episode One
- Half-Life 2: Episode Two
- Half-Life 2: Lost Coast
- Half-Life 2: Deathmatch
- Infra
- Black Mesa

4. Maintenant, naviguez dans le dossier racine de `Source SDK 2013 Multiplayer` et ensuite dans le dossier bin.
5. Double cliquez sur `hammerplusplus.exe` et quand la petite fenêtre apparaît vous devez choisir `Half-Life 2`. (Non, vous n'ajouterez pas `Garry's Mod` dans cette liste...)
6. Une fois que Hammer est ouvert, vous devez ouvrir le menu déroulant `Tools` et de là, choisissez `Options...`.
7. Une nouvelle fenêtre va apparaître, cliquez sur "Game Configurations" et vous verrez un petit bouton "Ajouter", cliquez dessus.
8. Naviguez dans le dossier racine de votre `Garry's Mod`, puis dans le dossier `bin` et trouvez le fichier appelé `garrysmod.fgd` et chargez-le.
9. Cliquez sur l'onglet `2D Views` et dans la section `Options`, cochez tout ce qui se trouve dans la colonne de droite.
10. Dans l'onglet "Build Programs", vous allez changer le chemin de l'exécutable du jeu en "<dossier racine de Garry's Mod>/hl2.exe".
11. Dans l'onglet `Build Programs`, vous allez changer le chemin de `Place compiled maps in this directory before running the game` en `<Garry's Mod root folder>/garrysmod/maps`.
12. Dans `Hammer++`, désactivez le Filtrage Anisotropique (`Anisotropic Filtering`)

## Example de `gameinfo.txt`

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

## En conclusion
Vous êtes maintenant prêt à utiliser Hammer++ et cela devrait fonctionner. Le seul problème est que vous devez "mount" deux fois le contenu car Hammer++ ne supporte pas la méthode de "mount" de Garry's Mod pour le moment. Donc, si vous utilisez Hammer++, vous êtes probablement familier avec `mount.cfg` de gmod, donc pour monter du contenu dans Hammer++ vous devez le monter dans le fichier `gameinfo.txt` que vous avez édité plus tôt et l'ajouter juste après ces lignes que vous avez ajoutées plus tôt `game "<chemin du contenu>"`. Si vous pensez que je peux améliorer quelque chose, envoyez-moi un message sur GitHub ou vous pouvez me joindre sur discord (ParSec#4563) sur le serveur [Statua Mapping](https://discord.gg/3Uq4WKNRuF), je vous recommande de passer et de dire bonjour (en anglais uniquement ;-) ), beaucoup de gens là-bas peuvent vous aider avec beaucoup de vos problèmes.


Maintenant, si cela ne vous dérange pas, je vais me tirer une balle dans le visage.
Oh et je ne pourrais pas oublier CoolGuy qui me pose tous les jours la même question quand est-ce que je vais le faire et qui me rappelle à quel point je suis désorganisé.

Et merci à TabbyGarf pour la traduction!
