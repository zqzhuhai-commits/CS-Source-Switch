# CS:Source-Switch（Counter-Strike: Source 任天堂Switch移植版）

基于 naga（NaGaa95）的 **css_nx** 移植项目（v1.0.1）：https://github.com/NaGaa95/css_nx
该移植把 nillerusr 的 Android 版 Source 引擎（v1.17.0025）ARM64 库原样跑在 Switch 上。

## 已包含内容

| 文件/目录 | 说明 |
|---|---|
| `css_nx.nro` | 移植外壳 v1.0.1（含体感瞄准支持） |
| `lib/` | Source Engine Android 共享库（27个 .so，来自 source-engine v1.17.0025） |
| `files/` | 字体文件（dejavusans.ttf 等 5 个） |
| `config.txt` | 体感默认开启 + 推荐参数 |

## 安装到 Switch SD 卡

把整个 `css_nx` 文件夹放到 SD 卡的 `switch` 目录下：

```
/switch/css_nx/
  css_nx.nro
  config.txt
  lib/          <- 27 个 .so
  files/        <- 字体
  assets/       <- 需自备 extras_dir.vpk
  cstrike/      <- 需自备 CS:S 游戏数据
  hl2/          <- 需自备 Source 共享内容
  platform/     <- 需自备平台内容
```

启动方式：**必须用游戏覆盖模式（长按 R 进入 title）或 forwarder**，不能在相册/Applet 模式运行；需要完整应用内存池。

## 还需自备的材料（版权内容，请合法获取）

1. **cstrike APK**（CS:S Android 版）：用其 `lib/arm64-v8a/libclient.so` 和 `libserver.so` **覆盖** `lib/` 中同名文件；把 `assets/extras_dir.vpk` 放到 `assets/`
2. **PC Steam 版 CS:S 数据**：把 `cstrike/`、`hl2/`、`platform/` 三个文件夹放到 `/switch/css_nx/` 下

## 体感配置（config.txt，已默认开启）

- `gyro_enabled 1` — 开启体感瞄准
- `gyro_sensitivity_x 200` / `gyro_sensitivity_y 150` — 灵敏度（百分比）
- `gyro_invert_x 0` / `gyro_invert_y 0` — 轴反转
- `gyro_space 2` — 玩家空间偏航混合
- `gyro_tighten 1` — 收微小抖动、降低漂移
- `gyro_accel 1` — 快速甩动时最多 2 倍灵敏度加速

体感支持掌机模式、Pro 手柄、配对 Joy-Con；仅在游戏相对鼠标模式激活时注入，不会移动菜单光标。

## 许可与致谢

- 移植外壳：MIT License（NaGaa95/css_nx）
- Source Engine for Android：nillerusr 发布，非商业使用
- Counter-Strike: Source 游戏版权归 Valve Corporation，本项目不含游戏本体数据
