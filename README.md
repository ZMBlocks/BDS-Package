# BDS-Package

BDS 整合包，一键安装+配置 BDS

## 使用方法

1. 安装[Lip](https://github.com/futrime/lip/releases)
   1. 前往[Lip](https://github.com/futrime/lip/releases)发行版页面
   2. 下载最新版`lip-windows-amd64-setup.exe`(Lip 安装程序)
   3. 运行`lip-windows-amd64-setup.exe`并按照提示完成安装`(请勿取消勾选Add to PATH)`
2. `[可选]`设置 Github 镜像 →`lip config GitHubMirrorURL https://github.bibk.top`
3. `[可选]`设置 Go 模块代理镜像 →`lip config GoModuleProxyURL https://goproxy.cn`
4. 安装整合包 → `lip install -y github.com/ZMBlocks/BDS-Package`

## 安装列表
<!-- - [7-zip(命令行式压缩工具)](https://gitea.litebds.com/ShrBox/7-zip) -->
- [BDS(服务端本体)](https://github.com/LiteLDev/bds)
- [PreLoader(预加载工具)](https://github.com/LiteLDev/PeEditor)
- [MagicBlob(BDS运行数据)](https://github.com/LiteLDev/bedrock-runtime-data)
- [LeviLamina(Native 插件加载器)](https://github.com/LiteLDev/LeviLamina)
- [CrashLogger(崩溃信息收集/崩溃日志)](https://github.com/LiteLDev/CrashLogger)
- [LeviLamina-loc(LeviLamina 语言包)](https://github.com/LiteLDev/levilamina-loc)
<!-- - [legacy-script-engine-lua(Lua 插件加载器)](https://gitea.litebds.com/LiteLDev/legacy-script-engine-lua)
- [legacy-script-engine-nodejs(NodeJS 插件加载器)](https://gitea.litebds.com/LiteLDev/legacy-script-engine-nodejs)
- [legacy-script-engine-quickjs(QuickJS 插件加载器)](https://gitea.litebds.com/LiteLDev/legacy-script-engine-quickjs)
- [node-binaries(NodeJS 运行环境)](https://gitea.litebds.com/LiteLDev/node-binaries)
- [LegacyMoney(经济系统)](https://github.com/LiteLDev/LegacyMoney)
- [LegacyParticleAPI(粒子生成器 API)](https://github.com/LiteLDev/LegacyParticleAPI)
- [LegacyRemoteCall(远程调用 API)](https://github.com/LiteLDev/LegacyRemoteCall)
- [GMLIB(API 前置库)](https://github.com/GroupMountain/GMLIB-Release)
- [GMLIB-LegacyRemoteCallApi(GMLIB 的 LSE 插件兼容)](https://github.com/GroupMountain/GMLIB-LegacyRemoteCallApi)
- [LeviAntiCheat(Lac 反作弊)](https://github.com/LiteLDev/LeviAntiCheat)
- [LeviOptimize(BDS 优化插件)](https://github.com/LiteLDev/LeviOptimize)
- [more-dimensions(多维度插件)](https://github.com/LiteLDev/MoreDimensions) -->
- [iListenAttentively(事件前置库)](https://github.com/MiracleForest/iListenAttentively-Release)
<!-- - [BackupHelper(热备份)](https://github.com/ShrBox/BackupHelper) -->

## 命令帮助

- LeviLamina
  - `teleportdim/tpdim` - 附带维度的传送命令
    - `/tpdim <目的地坐标> <维度ID> [忽略维度坐标转换]`
      - `/tpdim 0 0 0 overworld` - 传送自己到主世界 0 0 0 位置
      - `/tpdim 0 0 0 nether true` - 传送自己到主世界 0 0 0 位置(忽略维度坐标转换)
      - `/tpdim ~ ~ ~ nether true` - 传送自己到当前坐标位置的地狱维度
    - `/tpdim <实体> <目的地坐标> <维度ID> [忽略维度坐标转换]`
      - `/tpdim @p 0 0 0 overworld` - 传送最近玩家到主世界 0 0 0 位置
      - `/tpdim @e[type=minecraft:player] 0 0 0 overworld` - 传送所有玩家到主世界 0 0 0 位置
      - `/tpdim @e[type=minecraft:player] 0 0 0 nether true` - 传送所有玩家到地狱 0 0 0 位置(忽略维度坐标转换)
  - `crash` - 崩溃命令
    - `/crash [异常ID]`
      - `/crash` - 崩溃
      - `/crash 1` - 崩溃(异常 ID 为 1)
  - `version` - 查看版本
    - `/version` - 查看当前服务端 BDS 和 LeviLamina 版本
      - `/version` - 查看当前服务端 BDS 和 LeviLamina 版本
  - `memstats` - 查看内存占用
    - `/memstats` - 查看当前服务端内存占用
      - `/memstats` - 查看当前服务端内存占用
  - `levilamina/ll` - Mod 管理命令
    - `ll load <模组名称>` - 加载 Mod
      - `ll load GMLIB` - 加载 GMLIB 插件
    - `ll <enable|disable|show> <模组名称>` - 启用 Mod/禁用 Mod/显示 Mod 信息
      - `ll enable GMLIB` - 启用 GMLIB 插件
      - `ll disable GMLIB` - 禁用 GMLIB 插件
      - `ll show GMLIB` - 显示 GMLIB 插件信息
    - `ll <reload|unload|reactivate> <模组名称>` - 重载 Mod/卸载 Mod/重新激活 Mod
      - `ll reload GMLIB` - 重载 GMLIB 插件(unload 再 load)
      - `ll unload GMLIB` - 卸载 GMLIB 插件
      - `ll reactivate GMLIB` - 重新激活 GMLIB 插件(disable 再 enable)
    - `ll list` - 列出所有已加载的 Mod
      - `ll list` - 列出所有已加载的 Mod
<!-- - LegacyMoney
  - `money` - 经济系统命令
    - `/money <adds|reduces|sets> <玩家选择器> <金额>` - 增加/减少/设置金额(目标选择器)
      - `/money adds @p 100` - 给最近玩家增加 100 金额
      - `/money reduces @a 100` - 给所有玩家减少 100 金额
      - `/money sets @s 100` - 给自己设置 100 金额
    - `/money <set|add|reduce|pay> <玩家名> <金额>` - 增加/减少/设置金额(玩家名,支持离线玩家)
      - `/money set LiteLDev 100` - 给 LiteLDev 设置 100 金额
      - `/money add LiteLDev 100` - 给 LiteLDev 增加 100 金额
      - `/money reduce LiteLDev 100` - 给 LiteLDev 减少 100 金额
      - `/money pay LiteLDev 100` - 给 LiteLDev 转账 100 金额
    - `/money hist <玩家名> [多长时间内(单位:秒)]` - 查看玩家历史交易记录
      - `/money hist LiteLDev` - 查看 LiteLDev 一天内的历史交易记录
      - `/money hist LiteLDev 3600` - 查看 LiteLDev 最近 1 小时内历史交易记录
    - `/money purge confirm [多久之前(单位:秒)]` - 清除历史交易记录`(所有玩家,不是个人)`
      - `/money purge confirm` - 清除所有历史交易记录
      - `/money purge confirm 3600` - 清除 1 小时之前的所有历史交易记录
    - `/money query [玩家名]` - 查看金额
      - `/money query` - 查看自己金额
      - `/money query LiteLDev` - 查看 LiteLDev 的金额
    - `/money querys <玩家选择器>` - 查看玩家金额
      - `/money querys @a` - 查看所有玩家金额
      - `/money querys @p` - 查看最近玩家金额
    - `/money top [数量(最大100)]` - 查看金额排行榜
      - `/money top` - 查看金额排行榜前十
      - `/money top 5` - 查看金额排行榜前五
- LeviAntiCheat
  - `lac` - lac 命令
    - `/lac reload` - 重载配置文件
      - `/lac reload` - 重载 lac 配置文件
    - `lac <ban|unban> <玩家名> [原因] [封禁时间(单位:分钟)]` - 封禁/解封玩家
      - `/lac ban LiteLDev` - 封禁 LiteLDev
      - `/lac unban LiteLDev` - 解封 LiteLDev
      - `/lac ban LiteLDev "作弊" 60` - 封禁 LiteLDev 60 分钟,原因:作弊
    - `lac <mute|unmute> <玩家名> [禁言时间(单位:分钟)]` - 禁言/解禁玩家
      - `/lac mute LiteLDev` - 禁言 LiteLDev 10分钟
      - `/lac unmute LiteLDev` - 解禁 LiteLDev
      - `/lac mute LiteLDev 60` - 禁言 LiteLDev 60 分钟
- LeviOptimize
  - `timing` - 显示服务器性能统计信息
    - `/timing` - 显示服务器性能统计信息
- BackupHelper
  - `backup` - 备份命令
    - `/backup [list|reload|cancel]` - 备份主要命令
      - `/backup` - 备份存档
      - `/backup list` - 列出所有备份
      - `/backup reload` - 重载配置文件
      - `/backup cancel` - 取消当前备份
    - `/backup recover <备份索引ID>` - 恢复备份(索引ID 通过 /backup list 获取)
      - `/backup recover 1` - 恢复备份列表中第一个备份
- legacy-script-engine-lua
  - `luadebug` - Lua 代码调试命令
    - `/luadebug [代码]` - 调试代码
      - `/luadebug` - 进入 Lua 代码调试模式
      - `/luadebug print("Hello World!")` - 调试代码`print("Hello World!")`
- legacy-script-engine-nodejs
  - `nodejsdebug` - NodeJS 代码调试命令
    - `/nodejsdebug [代码]` - 调试代码
      - `/nodejsdebug` - 进入 NodeJS 代码调试模式
      - `/nodejsdebug console.log("Hello World!")` - 调试代码`console.log("Hello World!")`
- legacy-script-engine-quickjs
  - `jsdebug` - QuickJS 代码调试命令
    - `/jsdebug [代码]` - 调试代码
      - `/jsdebug` - 进入 QuickJS 代码调试模式
      - `/jsdebug log("Hello World!")` - 调试代码`log("Hello World!")` -->