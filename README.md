# myRime

## 使用

1. 下载 [Rime](http://rime.im/) 并安装

2. 下载 [myRime](https://github.com/ASC8384/myRime/archive/master.zip) 并解压

3. 打开 Rime 的`用户文件夹`，把压缩包里的东西扔进去，选择性覆盖，重新部署即可

4. 由于现在的小狼毫官方并没有给出 64 位版本的 `WeaselDeployer.exe` 和 `rime.dll`，因此无法部署某些大词典（比如维基词典）。解决方案是下载 @fxliang 大佬制作的 [rimedeployerx64.zip](https://github.com/rime/weasel/issues/953#issuecomment-1702396237) 并放置到程序文件夹中，运行 `rimedeployerx64.exe` 就可以部署大词库了，并期待 [Weaseldeployer x64](https://github.com/rime/weasel/pull/1006) 能早日合并

5. 开始打字

## 说明

0. 使用小鹤双拼；
1. 开启 mysymbols.yaml 方便输入特殊符号，并更新了一波源文件（从`0.8.1`升级至`1.3`）；
2. 候选词竖排；
3. 提供颜文字；
4. 提供 emoji 开关；
5. 默认不显示生僻字；
6. 引入维基词库、四叶草词库等一系列词库；
7. 在小狼毫平台上，新增一种 [扶风 / Gruvbox](https://github.com/ASC8384/myRime/issues/1) 的界面风格。

## 按键

1. `\man`：调出符号帮助
2. `\`：自定义符号
3. `yw`：调出所有颜文字
4. `\``：笔画输入法反查，hspnz/一丨丿丶乙
5. `;`：候选项的第二项
6. `'`：候选项的第三项

## 各文件说明

采用 UTF-8 编码的 [YAML](http://yaml.org/) 文本。

### dicts

存放词库，详情请见 [词库](./dicts/readme.md)。

### lua

存放 `lua` 脚本。

### 用户文档夹 - UserData

从 Rime 的 [wiki](https://github.com/rime/home/wiki/UserData) 里 copy 的。

#### 默认位置

* 小狼毫： 用户文档夹的默认路径为 `%APPDATA%\Rime`。也可以通过「开始菜单＼小狼毫输入法＼用户文档夹」打开。
* 鼠须管： 用户文档夹的路径为 `~/Library/Rime`。也可以通过「系统输入法菜单／鼠须管／用户设置…」打开。
* ibus-rime: `~/.config/ibus/rime`
* fcitx-rime: `~/.config/fcitx/rime`
* fcitx5-rime: `~/.local/share/fcitx5/rime/`

#### 内容

用家下载或定制的文档：

* `<输入方案代号>.schema.yaml` - 用户下载或自定义的 _输入方案_。
* `<韵书代号>.dict.yaml` - 用户下载或自定义的 _韵书_。
* `<词典名称>.txt` - 文本格式的词典，如缺省词汇表、用户 _自定义词组_。
* `<配置代号>.custom.yaml` - 应用于配置文档 `<配置代号>.schema.yaml` 或 `<配置代号>.yaml` 的 _补丁_。
* `opencc/*` - [OpenCC](https://github.com/BYVoid/OpenCC) 字形转换配置及字典文档。

输入法程序记录的使用习惯等信息：

* `<输入法语言代号>.userdb/` - 输入法程序为保存用户的输入习惯而创建的 _用户词典_。
* `installation.yaml` - 安装信息。输入法程序在首次运行及升级后写入安装、升级时间、程序版本等。
* `user.yaml` - 用户状态信息。包括在 _方案选单_ 选取的输入方案、输入法选项状态如「中／西」「简／繁」等。

部署时生成的文档：

* `build/*` - 缓存文档。为使输入法程序高效运行，在部署过程中将配置、韵书等编译为机读格式。
* `trash/*` - 失效的文档。因 Rime 升级而不再使用的旧文档会自动移入这个文档夹。用家确认不再需要后可以删除。

注：`librime` 1.3 版本之前，编译后的缓存文档（包括应用了补靪的 YAML 配置）直接存放在用户文档夹；`librime` 升级后将其移入 `trash/`。如果某个 YAML 源文档已经找不到了，无法在升级后重新编译，可以从 `trash/` 里面找回一份副本。

## 致谢

感谢的大佬太多了，有很多没敲上😂，还请谅解。

[🍀四叶草拼音输入方案](https://github.com/fkxxyz/rime-cloverpinyin)

[fcitx5-pinyin-zhwiki](https://github.com/ipcjs/fcitx5-pinyin-zhwiki)

[rime-aca](https://github.com/rime-aca/dictionaries)

[半月湾 C](http://tieba.baidu.com/p/3288634121)

[imy0823](http://tieba.baidu.com/p/4125987751)

[Rime's wiki](https://github.com/rime/home/wiki)

[佛振](https://github.com/lotem)、[等 Rime 全体贡献者](https://github.com/orgs/rime/people)

[OpenCC](https://github.com/BYVoid/OpenCC)

[深蓝词库转换器作者](https://code.google.com/p/imewlconverter/) 及全体贡献者

[just4u1314](http://tieba.baidu.com/p/2757690418)

[ACsediment](https://github.com/ACsediment/RimeNewbie)

[Aixtuz](https://github.com/Aixtuz/Rime-Config)

搜狗细胞词库工作人员及贡献者

百度输入法词库工作人员及贡献者

QQ 输入法词库工作人员及贡献者
