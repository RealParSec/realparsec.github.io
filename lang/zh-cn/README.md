# 如何将 Hammer++ 用于 Garry's Mod

# 为什么我创建了这个文档？
答案非常的简单... 我活腻了。开玩笑的，但是我真的看到很多人因为在给 Garry's Mod 安装 Hammer++ 时饱受折磨，所以以下是我找到的实现方法。 

## 环境需求:
- 一台运行 Windows 操作系统的计算机
- [7-Zip](https://www.7-zip.org/)
- [Garry's Mod](https://store.steampowered.com/app/4000)
- 起源游戏
	- [反恐精英：起源](https://store.steampowered.com/app/240)
	- [Half-Life 2](https://store.steampowered.com/app/220)
	- [Half-Life 2: 死亡竞赛](https://store.steampowered.com/app/320)
	- [Half-Life 2: 第一章](https://store.steampowered.com/app/380)
	- [Half-Life 2: 第二章](https://store.steampowered.com/app/420)
	- [Half-Life 2: 迷失的海岸线](https://store.steampowered.com/app/340)
	- (可选) [INFRA](https://store.steampowered.com/app/251110)
	- (可选) [Black Mesa](https://store.steampowered.com/app/362890)
- Source SDK 2013 Multiplayer
- (可选) [Slammin' Tools](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ)
- [Hammer++](https://ficool2.github.io/HammerPlusPlus-Website/index.html)

**关于 Windows 版本兼容**  
需要 Windows 来运行 Hammer++，因为其它系统尚未被 Valve 完全支持，hammer 也还未在 Windows 以外的任何操作系统上可用。虽然目前还没有一个精确的版本号，但是我个人已经在从 Windows 10 专业版 20H2 构建 19042.928 到 Windows 10 专业版 21H2 构建 19044.1526(也是我在撰写这个的时候在公开发布通道上最新的版本) 上进行了测试。尽管如此，自从我在将近一年前发布本指南以来，已有很多人按照本指南在许多不同的 Windows 版本（包括 Windows 11）上成功安装了 Hammer++ 。

## 我该如何安装环境需求？
在这个教程中，我想你已经安装了 Garry's Mod 以及我提到的所有起源游戏，还安装了 7-Zip。

### 如何安装 Source SDK 2013 Multiplayer
1. 导航至 Steam 库，确保在搜索过滤器中勾选了工具 
2. 打开 `未分类` 分类然后找到 `Source SDK 2013 Multiplayer`，或者直接搜索。
3. 点击 `安装` 按钮然后按 `继续` 接着等待它下载完成
![Image 1](../../images/1.png)
1. **「在继续之前你必须先从 SOURCE SDK 2013 MULTIPLAYER 运行一次 HAMMER」** (下面的步骤讲述了该如何操作)
2. 右键 `Source SDK 2013 Multiplayer`，移到 `管理` 然后点击 `浏览本地文件`
![Image 2](../../images/2.png)
1. 导航到 `bin` 文件夹然后双击 `hammer.exe` 。弹出一个小窗口，从里面选择 `Half-Life 2` 。
2. 当 Hammer 打开并完全初始化，关闭它
![Image 3](../../images/3.png)

### (可选) 如何安装 Slammin' Tools？
**Slammin' Tools 并不是很必要，但是是个很好的选择，特别是当你在编译 Statua 的地图时。**

1. 导航到这个 [链接](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ) 并下载后缀为 `.7z` 的文件
![Image 4](../../images/4.png)
1. 下载完成后，打开压缩包并把所有文件拖拽进 `Source SDK 2013 Multiplayer` 的 `bin` 文件夹 (I它会询问你是否要覆盖某些文件，选择是)
![Image 5](../../images/5.png)
![Image 6](../../images/6.png)
1. 接下来重复安装 `Source SDK 2013 Multiplayer` 的步骤 `6` 和 `7` 

## 安装并配置 Hammer++
好了现在别再放狗屁了，我已经活腻到要对自己的脸使用大力冲拳了（bushi），现在让我们进入最终阶段：安装并配置 Hammer++ 。

### 安装
1. 导航到这个 [链接](https://ficool2.github.io/HammerPlusPlus-Website/pages/download.html) 并下载 `Source SDK 2013 Multiplayer` 的版本
![Image 7](../../images/7.png)
2. 下载完成后，打开压缩包，导航到你看到的唯一的文件夹中，打开里面的 `bin` 文件夹并把里面所有的文件拖拽到 `Source SDK 2013 Multiplayer` 的 `bin` 文件夹
![Image 8](../../images/8.png)
![Image 9](../../images/9.png)
3. 接下来重复安装 `Source SDK 2013 Multiplayer` 的步骤 `6` 和 `7` 

### 配置
这部分教程只有文字，请仔细阅读，因为这里写的每一步都非常重要。

1. 导航到 `Source SDK 2013 Multiplayer` 的根目录并打开文件夹 `hl2`
2. 使用一个文本编辑器打开 `gameinfo.txt`
3. 你需要把以下内容添加到你的 `gameinfo.txt`，**别忘记修改 "<Steam 的 common 文件夹>" 到正确的路径！**
示例：[链接](https://github.com/RealParSec/realparsec.github.io/blob/master/README.md#example-gameinfotxt)

```
// 起源游戏内容
game				"<Steam 的 common 文件夹>/GarrysMod/garrysmod/garrysmod.vpk"
game				"<Steam 的 common 文件夹>/Half-Life 2/episodic/ep1_pak.vpk"
game				"<Steam 的 common 文件夹>/Half-Life 2/ep2/ep2_pak.vpk"
game				"<Steam 的 common 文件夹>/Half-Life 2/lostcoast/lostcoast_pak.vpk"
game				"<Steam 的 common 文件夹>/Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
game				"<Steam 的 common 文件夹>/Counter-Strike Source/cstrike/cstrike_pak.vpk"
game				"<Steam 的 common 文件夹>/infra/infra/pak01.vpk"

// Black Mesa 内容 - 上次我发现了一些 hammer++ 中的问题且导致了 hammer++ 崩溃
game				"<Steam 的 common 文件夹>/Black Mesa/bms/bms_materials.vpk"
game				"<Steam 的 common 文件夹>/Black Mesa/bms/bms_models.vpk"
game				"<Steam 的 common 文件夹>/Black Mesa/bms/bms_sound_vo_english.vpk"
game				"<Steam 的 common 文件夹>/Black Mesa/bms/bms_sounds_misc.vpk"
game				"<Steam 的 common 文件夹>/Black Mesa/bms/bms_textures.vpk"
```

您可以将它们添加到这几行之后：

```
// 游戏的二进制文件所在的目录
gamebin				hl2/bin
platform			|all_source_engine_paths|platform
```

以下的内容适用于装载到起源游戏，列表如下
- Garry's Mod
- 反恐精英：起源
- Half-Life 2: 第一章
- Half-Life 2: 第二章
- Half-Life 2: 迷失的海岸线
- Half-Life 2: 死亡竞赛
- Infra
- Black Mesa

1. 现在导航到 `Source SDK 2013 Multiplayer` 的根目录然后打开 bin 文件夹
2. 双击 `hammerplusplus.exe` 然后当小窗口出现时选择 `Half-Life 2`，是的你没的选择 `Garry's Mod`
3. 一旦 hammer 打开，你必须打开 `Tools/工具` 下拉菜单并选择 `Options.../选项...`
4. 将会打开一个新窗口，点击 `Game Configurations/游戏配置` 然后你就会看到一个小按钮 `Add/添加` 点击它
5. 导航到你的 `Garry's Mod` 根目录然后打开 `bin` 文件夹接着找到文件 `garrysmod.fgd` 并加载
6. 点击 `2D Views/2D 视图` 选项卡然后打开 `Options/选项` 勾选右栏中的所有内容
7.  在 `Build Programs/构建程序` 选项卡，修改 `Game executable/游戏可执行文件` 到 `<Garry's Mod 根目录>/hl2.exe`
8.  在 `Build Programs/构建程序` 选项卡，修改 `Place compiled maps in this directory before running the game/请在运行游戏前把编译好的地图填入此目录` 到 `<Garry's Mod 根目录>/garrysmod/maps`
9.  在 `Hammer++`，关闭 Anisotropic Filtering/各向异性过滤

## 示例 `gameinfo.txt`

```
"GameInfo"
{
	game 		"HALF-LIFE 2"
	title 		"HALF-LIFE'"
	type		singleplayer_only
	supportsvr	1

	FileSystem
	{
		SteamAppId				220		// 这将装入我们需要的所有 GCF（240=CS:S，220=HL2）。
		
		//
		// 自动加载该文件的代码在这里做了几件事：
		//
		// 1. 给每个 "游戏" 搜索路径，添加一个 "游戏Bin" 路径，在 <dir>\bin
		// 2. 给每个 "游戏" 搜索路径，添加另一个 "游戏" 路径在它前面，一个 _<langage> 在它后面。
		//    示例：c:\hl2\cstrike 在法语的机器上会获取一个 c:\hl2\cstrike_french 的路径添加进去。
		// 3. 给第一个 "游戏" 搜索路径，添加一个搜索路径名为 "MOD" 。
		// 4. 给第一个 "游戏" 搜索路径，添加一个搜索路径名为 "DEFAULT_WRITE_PATH".
		//

		//
		// 搜索路径相对于基本目录，也就是 hl2.exe 所在的目录。
		//
		// |gameinfo_path| 指向 gameinfo.txt 所在的目录。
		// 我们始终希望将该目录挂载到 gameinfo.txt 的相对位置，
		// 这样人们就能把东西挂载到 c:\mymod 里，而主要的游戏资源则始终都在
		// 类似 c:\program files\valve\steam\steamapps\half-life 2 的地方。
		//
		SearchPaths
		{
			// 首先，加载所有用户自定义设置。这会搜索 VPK 和子文件夹，并按字母顺序加载。
			// 要“安装”一个 MOD，只需将其放入该文件夹即可。
			// 分发 MOD 的最简单方法是将自定义内容打包到 VPK 中。
			//
			// 注意，只有在启动游戏时才会扫描该文件夹。
			game+mod			hl2/custom/*

			// 我们先搜索 VPK 文件，然后再搜索普通文件夹，
			// 因为大多数文件都能在 VPK 中找到，而且我们可以避免进行成千上万次文件系统调用，
			// 试图打开文件夹中不存在的文件。（搜索 VPK 要比调用操作系统快得多）。
			game_lv				hl2/hl2_lv.vpk
			game+mod			hl2/hl2_sound_vo_english.vpk
			game+mod			hl2/hl2_pak.vpk
			game				|all_source_engine_paths|hl2/hl2_textures.vpk
			game				|all_source_engine_paths|hl2/hl2_sound_misc.vpk
			game				|all_source_engine_paths|hl2/hl2_misc.vpk
			platform			|all_source_engine_paths|platform/platform_misc.vpk

			// 现在搜索松散的文件。我们将把包含 gameinfo.txt 文件的目录
			// 设为第一个“mod”搜索路径（在用户自定义之后）。
			// 这也是写入“mod”路径时使用的路径。
			mod+mod_write+default_write_path		|gameinfo_path|.

			// 将 HL2 目录添加为游戏搜索路径。
			// 这也是写入“游戏”路径的位置。
			game+game_write		hl2

			// 游戏的二进制文件所在的目录
			gamebin				hl2/bin

			// 最后，装入共享的 HL2 松散文件
			game				|all_source_engine_paths|hl2
			platform			|all_source_engine_paths|platform

			// 起源游戏
			game				"|all_source_engine_paths|../GarrysMod/garrysmod/garrysmod.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/episodic/ep1_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/ep2/ep2_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/lostcoast/lostcoast_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
			game				"|all_source_engine_paths|../Counter-Strike Source/cstrike/cstrike_pak.vpk"
			game				"|all_source_engine_paths|../infra/infra/pak01.vpk"

			// Black Mesa 内容 - 上次我发现了一些 hammer++ 中的问题且导致了 hammer++ 崩溃
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_materials.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_models.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_sound_vo_english.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_sounds_misc.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_textures.vpk"


			// 其它的内容
			// game				"E:/gmod/maps/rp_riverden/content/"
		}
	}
}
```

## 结语
现在您已准备好使用 Hammer++，它应该可以正常工作。唯一的问题是，由于 Hammer++ 暂时不支持 Garry's Mod 的挂载方式，您必须重复挂载内容。因此，如果您正在使用 Hammer++，您很可能熟悉 gmod 的 `mount.cfg`，所以要将内容挂载到 Hammer++，您必须将其挂载到您之前编辑的 `gameinfo.txt` 文件中，并将其添加到您之前添加的 `game"<到你内容的路径>"` 行之后。如果您认为我可以改进某些地方，请在 Github 上与我联系，或者您可以在 Discord（ParSec#4563）的 [Statua Mapping](https://discord.gg/3Uq4WKNRuF) 服务器上与我联系，我建议您过来打声招呼，那里有很多人可以帮助您解决很多问题。

现在如果你不介意的话我就要朝我的脸当头一枪了。

哦对我还不能忘了你个byd，每天都问我同样的问题，问我什么时候整出来，顺便还提醒我自己是多么的杂乱无章。
