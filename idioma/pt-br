| Languages |
| --- |
| **en**, [ru](./lang/ru/), [pt-br](./lang/pt-br/) |

# Como usar o Hammer++ com o Garry's Mod

## Por que eu criei isso?
A resposta é bem simples... Eu me odeio. Não, mas realmente vi muitas pessoas lutando para instalar o Hammer++ em si, mas tiveram mais problemas para instalá-lo para o Garry's Mod, então essa é uma maneira que encontrei para fazê-lo funcionar.

## Requisitos:
- Um computador rodando Windows
- [7-Zip](https://www.7-zip.org/)
- [Garry's Mod](https://store.steampowered.com/app/4000)
- Jogos Source:
	- [Counter-Strike: Source](https://store.steampowered.com/app/240)
	- [Half-Life 2](https://store.steampowered.com/app/220)
	- [Half-Life 2: Deathmatch](https://store.steampowered.com/app/320)
	- [Half-Life 2: Episode One](https://store.steampowered.com/app/380)
	- [Half-Life 2: Episode Two](https://store.steampowered.com/app/420)
	- [Half-Life 2: Lost Coast](https://store.steampowered.com/app/340)
	- (Opicional) [INFRA](https://store.steampowered.com/app/251110)
	- (Opicional) [Black Mesa](https://store.steampowered.com/app/362890)
- Source SDK 2013 Multiplayer
- (Opicional) [Slammin' Tools](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ)
- [Hammer++](https://ficool2.github.io/HammerPlusPlus-Website/index.html)

**Sobre a compatibilidade das versões do Windows**  
O Windows é necessário para executar o Hammer++, pois outros sistemas operacionais não são totalmente suportados pela Valve, portanto, o Hammer não está disponível para nenhum outro sistema operacional além do Windows. Quando se trata de versões específicas não há nenhuma, eu testei pessoalmente no Windows 10 Pro versão 20H2 build 19042.928 e todas as versões até o Windows 10 Pro versão 21H2 build 19044.1526 (sendo a versão mais recente disponível em canal público no momento em que escrevo este ). Dito isto, desde que publiquei este guia há quase um ano, as pessoas o seguiram e conseguiram instalá-lo em várias versões diferentes do Windows, incluindo o Windows 11.

## Como instalo os requisitos?
Neste tutorial, suponho que você tenha o Garry's Mod, bem como todos os jogos de origem que mencionei instalados e também o 7-Zip instalado.

### Como instalar o Source SDK 2013 Multijogador
1. Navegue até sua biblioteca Steam e verifique se as ferramentas estão marcadas em seus filtros de pesquisa
2. Abra a categoria `UNCATEGORIZED` e encontre `Source SDK 2013 Multiplayer`, alternativamente, basta pesquisá-lo
3. Clique no botão `INSTALL` depois em `NEXT` e aguarde o download
![Image 1](./images/1.png)
4. **VOCÊ DEVE EXECUTAR O HAMMER FROM SOURCE SDK 2013 MULTIPLAYER AGORA ANTES DE CONTINUAR** (As etapas abaixo explicam como fazer isso)
5. Clique com o botão direito do mouse em `Source SDK 2013 Multiplayer`, passe o mouse sobre `Manage` e clique em `Browse local files`
![Image 2](./images/2.png)
6. Navegue até a pasta `bin` e clique duas vezes em `hammer.exe`. Uma pequena janela deve aparecer, escolha `Half-Life 2` a partir daí.
7. Quando o Hammer abrir e inicializar totalmente, feche-o
![Image 3](./images/3.png)

### (Opcional) Como instalar o Slammin' Tools?
**Ferramentas Slammin' não são necessárias, mas é bom ter, especialmente se você estiver compilando os mapas do Statua.**

1. Navegue até este [link](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ) e baixe o arquivo que termina com `.7z`
![Image 4](./images/4.png)
2. Depois de baixado, abra o arquivo e arraste e solte os arquivos na pasta `bin` do `Source SDK 2013 Multiplayer` (Ele perguntará se você deseja substituir alguns arquivos, clique em sim.)
![Image 5](./images/5.png)
![Image 6](./images/6.png)
3. Agora repita os passos `6` e `7` da instalação do `Source SDK 2013 Multiplayer`

## Instalando e configurando o Hammer++
Agora sem mais enrolação pois já me odeio a ponto de me dar um soco na cara, chegamos ao gran finale que é instalar e configurar o Hammer++.

### Instalando
1. Navegue até este [link](https://ficool2.github.io/HammerPlusPlus-Website/pages/download.html) e baixe a versão para `Source SDK 2013 Multiplayer`
![Image 7](./images/7.png)
2. Uma vez baixado, abra o arquivo, navegue dentro da pasta que você vê e na pasta `bin` dentro, arraste e solte os arquivos na pasta `bin` do `Source SDK 2013 Multiplayer`
![Image 8](./images/8.png)
![Image 9](./images/9.png)
3. Agora repita os passos `6` e `7` da instalação do `Source SDK 2013 Multiplayer`

### Configurando
Esta parte do tutorial será apenas texto, então leia com muita atenção, pois cada passo escrito aqui é muito importante.

1. Navegue até a pasta raiz do `Source SDK 2013 Multiplayer` e abra a pasta chamada `hl2`
2. Abra `gameinfo.txt` com um editor de texto de sua escolha
3. Você vai precisar adicionar essas linhas em seu `gameinfo.txt`, ** não se esqueça de mudar "<pasta comum do Steam>" para o caminho correto!**
Exemplo: [link](https://github.com/RealParSec/realparsec.github.io/blob/master/README.md#example-gameinfotxt)

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

Você os adiciona após essas linhas:

```
// Where the game's binaries are
gamebin				hl2/bin
platform			|all_source_engine_paths|platform
```

Essas linhas montam o conteúdo dos jogos de origem, a lista é a seguinte
- Garry's Mod
- Counter-Strike: Source
- Half-Life 2: Episode One
- Half-Life 2: Episode Two
- Half-Life 2: Lost Coast
- Half-Life 2: Deathmatch
- Infra
- Black Mesa

4. Agora navegue até a pasta raiz do `Source SDK 2013 Multiplayer` e depois para a pasta bin
5. Clique duas vezes em `hammerplusplus.exe` e quando uma pequena janela aparecer, você deve escolher `Half-Life 2`, sim, você não adicionará `Garry's Mod` a essa lista
6. Assim que o hammer estiver aberto, você deve abrir o menu suspenso 'Tools' e, a partir daí, escolher 'Options...'
7. Uma nova janela aparecerá, clique em `Game Configurations` e você verá um pequeno botão `Add` clique nele
8. Navegue até a pasta raiz `Garry's Mod` e depois para a pasta `bin` e encontre o arquivo chamado `garrysmod.fgd` e carregue-o
9. Clique na guia `2D Views` e na seção `Options` marque tudo na coluna da direita
10. Na aba `Build Programs`, você vai mudar o caminho do `Game executable` para `<Garry's Mod root folder>/hl2.exe`
11. Na aba `Build Programs`, você vai alterar o caminho de `Place compiled maps in this directory before running the game` para `<Garry's Mod root folder>/garrysmod/maps`
12. Em `Hammer++`, desabilite a Filtragem Anisotrópica

## Exemplo `gameinfo.txt`

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

## Últimas palavras
Agora você está pronto para usar o Hammer++ ele deve funcionar. O único problema é que você tem que montar o conteúdo duas vezes, pois o Hammer++ não suporta a forma de montagem do Garry's Mod por enquanto. Portanto, se você estiver usando o Hammer++, provavelmente está familiarizado com `mount.cfg` do gmod, portanto, para montar o conteúdo no Hammer++, você deve montá-lo no arquivo `gameinfo.txt` editado anteriormente e adicioná-lo, logo após essas linhas você adicionou anteriormente `game "<path to your content>"`. Se você acha que eu poderia melhorar alguma coisa, envie-me uma mensagem no Github ou você pode me enviar um ping no discord (ParSec#4563) no servidor [Statua Mapping] (https://discord.gg/3Uq4WKNRuF), eu recomendo que você visite e diga olá, muitas pessoas lá podem ajudá-lo com muitos dos seus problemas.

Agora, se não se importa, vou dar um tiro na minha cara.
Ah, e não poderia me esquecer de você, CoolGuy, por me fazer a mesma pergunta todos os dias quando vou conseguir e me lembrar de como sou desorganizado.
