# 如何將 Hammer++ 用於 Garry's Mod

# 爲什麼我創建了這個文檔？
答案非常的簡單... 我活膩了。開玩笑的，但是我真的看到很多人因爲在給 Garry's Mod 安裝 Hammer++ 時飽受折磨，所以以下是我找到的實現方法。 

## 環境需求:
- 一部運行 Windows 操作系統的電腦
- [7-Zip](https://www.7-zip.org/)
- [Garry's Mod](https://store.steampowered.com/app/4000)
- Source 遊戲
	- [絕對武力：Source](https://store.steampowered.com/app/240)
	- [Half-Life 2](https://store.steampowered.com/app/220)
	- [Half-Life 2: 死亡競賽](https://store.steampowered.com/app/320)
	- [Half-Life 2: 第一章](https://store.steampowered.com/app/380)
	- [Half-Life 2: 第二章](https://store.steampowered.com/app/420)
	- [Half-Life 2: 迷失的海岸線](https://store.steampowered.com/app/340)
	- (可選) [INFRA](https://store.steampowered.com/app/251110)
	- (可選) [Black Mesa](https://store.steampowered.com/app/362890)
- Source SDK 2013 Multiplayer
- (可選) [Slammin' Tools](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ)
- [Hammer++](https://ficool2.github.io/HammerPlusPlus-Website/index.html)

**關於 Windows 版本相容**  
需要 Windows 來運行 Hammer++，因爲其它系統尚未被 Valve 完全支援，hammer 也還未在 Windows 以外的任何操作系統上可用。雖然目前還沒有一個精確的版本號，但是我個人已經在從 Windows 10 專業版 20H2 構建 19042.928 到 Windows 10 專業版 21H2 構建 19044.1526(也是我在撰寫這個的時候在公開發布通道上最新的版本) 上進行了測試。儘管如此，自從我在將近一年前發佈本指南以來，已有很多人按照本指南在許多不同的 Windows 版本（包括 Windows 11）上成功安裝了 Hammer++ 。

## 我該如何安裝環境需求？
在這個教程中，我想你已經安裝了 Garry's Mod 以及我提到的所有 Source 遊戲，還安裝了 7-Zip。

### 如何安裝 Source SDK 2013 Multiplayer
1. 導航至 Steam 庫，確保在搜索過濾器中勾選了工具 
2. 打開 `未分類` 分類然後找到 `Source SDK 2013 Multiplayer`，或者直接搜索。
3. 點擊 `安裝` 按鈕然後按 `繼續` 接着等待它下載完成
![Image 1](../../images/1.png)
1. **「在繼續之前你必須先從 SOURCE SDK 2013 MULTIPLAYER 運行一次 HAMMER」** (下面的步驟講述了該如何操作)
2. 右鍵 `Source SDK 2013 Multiplayer`，移到 `管理` 然後點擊 `瀏覽本機檔案`
![Image 2](../../images/2.png)
1. 導航到 `bin` 資料夾然後雙擊 `hammer.exe` 。彈出一個小窗口，從裏面選擇 `Half-Life 2` 。
2. 當 Hammer 打開並完全初始化，關閉它
![Image 3](../../images/3.png)

### (可選) 如何安裝 Slammin' Tools？
**Slammin' Tools 並不是很必要，但是是個很好的選擇，特別是當你在編譯 Statua 的地圖時。**

1. 導航到這個 [鏈接](https://drive.google.com/drive/folders/17pQY8wDkednZi0kMZOSpAtNBNmFWm6GJ) 並下載後綴爲 `.7z` 的檔案
![Image 4](../../images/4.png)
1. 下載完成後，打開壓縮檔案並把所有檔案拖拽進 `Source SDK 2013 Multiplayer` 的 `bin` 資料夾 (I它會詢問你是否要覆蓋某些檔案，選擇是)
![Image 5](../../images/5.png)
![Image 6](../../images/6.png)
1. 接下來重複安裝 `Source SDK 2013 Multiplayer` 的步驟 `6` 和 `7` 

## 安裝並配置 Hammer++
好了現在別再放狗屁了，我已經活膩到要對自己的臉使用大力衝拳了/jk，現在讓我們進入最終階段：安裝並配置 Hammer++ 。

### 安裝
1. 導航到這個 [鏈接](https://ficool2.github.io/HammerPlusPlus-Website/pages/download.html) 並下載 `Source SDK 2013 Multiplayer` 的版本
![Image 7](../../images/7.png)
2. 下載完成後，打開壓縮檔案，導航到你看到的唯一的資料夾中，打開裏面的 `bin` 資料夾並把裏面所有的檔案拖拽到 `Source SDK 2013 Multiplayer` 的 `bin` 資料夾
![Image 8](../../images/8.png)
![Image 9](../../images/9.png)
3. 接下來重複安裝 `Source SDK 2013 Multiplayer` 的步驟 `6` 和 `7` 

### 配置
這部分教程只有文字，請仔細閱讀，因爲這裏寫的每一步都非常重要。

1. 導航到 `Source SDK 2013 Multiplayer` 的根目錄並打開資料夾 `hl2`
2. 使用一個文本編輯器打開 `gameinfo.txt`
3. 你需要把以下內容添加到你的 `gameinfo.txt`，**別忘記修改 "<Steam 的 common 資料夾>" 到正確的路徑！**
示例：[鏈接](https://github.com/RealParSec/realparsec.github.io/blob/master/README.md#example-gameinfotxt)

```
// Source 遊戲內容
game				"<Steam 的 common 資料夾>/GarrysMod/garrysmod/garrysmod.vpk"
game				"<Steam 的 common 資料夾>/Half-Life 2/episodic/ep1_pak.vpk"
game				"<Steam 的 common 資料夾>/Half-Life 2/ep2/ep2_pak.vpk"
game				"<Steam 的 common 資料夾>/Half-Life 2/lostcoast/lostcoast_pak.vpk"
game				"<Steam 的 common 資料夾>/Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
game				"<Steam 的 common 資料夾>/Counter-Strike Source/cstrike/cstrike_pak.vpk"
game				"<Steam 的 common 資料夾>/infra/infra/pak01.vpk"

// Black Mesa 內容 - 上次我發現了一些 hammer++ 中的問題且導致了 hammer++ 崩潰
game				"<Steam 的 common 資料夾>/Black Mesa/bms/bms_materials.vpk"
game				"<Steam 的 common 資料夾>/Black Mesa/bms/bms_models.vpk"
game				"<Steam 的 common 資料夾>/Black Mesa/bms/bms_sound_vo_english.vpk"
game				"<Steam 的 common 資料夾>/Black Mesa/bms/bms_sounds_misc.vpk"
game				"<Steam 的 common 資料夾>/Black Mesa/bms/bms_textures.vpk"
```

您可以將它們添加到這幾行之後：

```
// 遊戲的二進制檔案所在的目錄
gamebin				hl2/bin
platform			|all_source_engine_paths|platform
```

以下的內容適用於裝載到 Source 遊戲，列表如下
- Garry's Mod
- 絕對武力：Source
- Half-Life 2: 第一章
- Half-Life 2: 第二章
- Half-Life 2: 迷失的海岸線
- Half-Life 2: 死亡競賽
- Infra
- Black Mesa

1. 現在導航到 `Source SDK 2013 Multiplayer` 的根目錄然後打開 bin 資料夾
2. 雙擊 `hammerplusplus.exe` 然後當小窗口出現時選擇 `Half-Life 2`，是的你沒的選擇 `Garry's Mod`
3. 一旦 hammer 打開，你必須打開 `Tools/工具` 下拉菜單並選擇 `Options.../選項...`
4. 將會打開一個新窗口，點擊 `Game Configurations/遊戲配置` 然後你就會看到一個小按鈕 `Add/添加` 點擊它
5. 導航到你的 `Garry's Mod` 根目錄然後打開 `bin` 資料夾接着找到檔案 `garrysmod.fgd` 並加載
6. 點擊 `2D Views/2D 視圖` 選項卡然後打開 `Options/選項` 勾選右欄中的所有內容
7.  在 `Build Programs/構建程序` 選項卡，修改 `Game executable/遊戲可執行檔案` 到 `<Garry's Mod 根目錄>/hl2.exe`
8.  在 `Build Programs/構建程序` 選項卡，修改 `Place compiled maps in this directory before running the game/請在運行遊戲前把編譯好的地圖填入此目錄` 到 `<Garry's Mod 根目錄>/garrysmod/maps`
9.  在 `Hammer++`，關閉 Anisotropic Filtering/各向異性過濾

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
		SteamAppId				220		// 這將裝入我們需要的所有 GCF（240=CS:S，220=HL2）。
		
		//
		// 自動加載該檔案的代碼在這裏做了幾件事：
		//
		// 1. 給每個 "遊戲" 搜索路徑，添加一個 "遊戲Bin" 路徑，在 <dir>\bin
		// 2. 給每個 "遊戲" 搜索路徑，添加另一個 "遊戲" 路徑在它前面，一個 _<langage> 在它後面。
		//    示例：c:\hl2\cstrike 在法語的機器上會獲取一個 c:\hl2\cstrike_french 的路徑添加進去。
		// 3. 給第一個 "遊戲" 搜索路徑，添加一個搜索路徑名爲 "MOD" 。
		// 4. 給第一個 "遊戲" 搜索路徑，添加一個搜索路徑名爲 "DEFAULT_WRITE_PATH".
		//

		//
		// 搜索路徑相對於基本目錄，也就是 hl2.exe 所在的目錄。
		//
		// |gameinfo_path| 指向 gameinfo.txt 所在的目錄。
		// 我們始終希望將該目錄掛載到 gameinfo.txt 的相對位置，
		// 這樣人們就能把東西掛載到 c:\mymod 裏，而主要的遊戲資源則始終都在
		// 類似 c:\program files\valve\steam\steamapps\half-life 2 的地方。
		//
		SearchPaths
		{
			// 首先，加載所有用戶客製化設置。這會搜索 VPK 和子資料夾，並按字母順序加載。
			// 要“安裝”一個 MOD，只需將其放入該資料夾即可。
			// 分發 MOD 的最簡單方法是將客製化內容打包到 VPK 中。
			//
			// 注意，只有在啓動遊戲時纔會掃描該資料夾。
			game+mod			hl2/custom/*

			// 我們先搜索 VPK 檔案，然後再搜索普通資料夾，
			// 因爲大多數檔案都能在 VPK 中找到，而且我們可以避免進行成千上萬次檔案系統調用，
			// 試圖打開資料夾中不存在的檔案。（搜索 VPK 要比調用操作系統快得多）。
			game_lv				hl2/hl2_lv.vpk
			game+mod			hl2/hl2_sound_vo_english.vpk
			game+mod			hl2/hl2_pak.vpk
			game				|all_source_engine_paths|hl2/hl2_textures.vpk
			game				|all_source_engine_paths|hl2/hl2_sound_misc.vpk
			game				|all_source_engine_paths|hl2/hl2_misc.vpk
			platform			|all_source_engine_paths|platform/platform_misc.vpk

			// 現在搜索鬆散的檔案。我們將把包含 gameinfo.txt 檔案的目錄
			// 設爲第一個“mod”搜索路徑（在用戶客製化之後）。
			// 這也是寫入“mod”路徑時使用的路徑。
			mod+mod_write+default_write_path		|gameinfo_path|.

			// 將 HL2 目錄添加爲遊戲搜索路徑。
			// 這也是寫入“遊戲”路徑的位置。
			game+game_write		hl2

			// 遊戲的二進制檔案所在的目錄
			gamebin				hl2/bin

			// 最後，裝入共享的 HL2 鬆散檔案
			game				|all_source_engine_paths|hl2
			platform			|all_source_engine_paths|platform

			// Source 遊戲
			game				"|all_source_engine_paths|../GarrysMod/garrysmod/garrysmod.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/episodic/ep1_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/ep2/ep2_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2/lostcoast/lostcoast_pak.vpk"
			game				"|all_source_engine_paths|../Half-Life 2 Deathmatch/hl2mp/hl2mp_pak.vpk"
			game				"|all_source_engine_paths|../Counter-Strike Source/cstrike/cstrike_pak.vpk"
			game				"|all_source_engine_paths|../infra/infra/pak01.vpk"

			// Black Mesa 內容 - 上次我發現了一些 hammer++ 中的問題且導致了 hammer++ 崩潰
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_materials.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_models.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_sound_vo_english.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_sounds_misc.vpk"
			//game				"|all_source_engine_paths|../Black Mesa/bms/bms_textures.vpk"


			// 其它的內容
			// game				"E:/gmod/maps/rp_riverden/content/"
		}
	}
}
```

## 結語
現在您已準備好使用 Hammer++，它應該可以正常工作。唯一的問題是，由於 Hammer++ 暫時不支援 Garry's Mod 的掛載方式，您必須重複掛載內容。因此，如果您正在使用 Hammer++，您很可能熟悉 gmod 的 `mount.cfg`，所以要將內容掛載到 Hammer++，您必須將其掛載到您之前編輯的 `gameinfo.txt` 檔案中，並將其添加到您之前添加的 `game"<到你內容的路徑>"` 行之後。如果您認爲我可以改進某些地方，請在 Github 上與我聯繫，或者您可以在 Discord（ParSec#4563）的 [Statua Mapping](https://discord.gg/3Uq4WKNRuF) 伺服器上與我聯繫，我建議您過來打聲招呼，那裏有很多人可以幫助您解決很多問題。

現在如果你不介意的話我就要朝我的臉當頭一槍了。

哦對我還不能忘了你個悾暗，每天都問我同樣的問題，問我什麼時候整出來，順便還提醒我自己是多麼的雜亂無章。