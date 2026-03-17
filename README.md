# H-Download

H-Download 是一个原生 macOS 下载管理器，面向大文件、断点续传、多连接分段下载和多镜像下载场景设计。
程序基于 Swift、SwiftUI、URLSession、SQLite 和 Swift async/await 构建，适用于 macOS 13 及以上系统。

## 主要功能

- 支持 HTTP / HTTPS 下载
- 支持断点续传与应用重启后的任务恢复
- 支持分段下载与并发连接加速
- 支持多镜像 / Metalink 下载
- 支持 SHA256、SHA1、MD5 哈希校验
- 支持下载历史记录、状态筛选与搜索
- 支持速度限制、重试策略和镜像选择模式设置
- 支持中文简体与英文界面切换

## 当前界面与交互

- 左侧边栏提供主要导航：进行中、已完成、失败、历史记录、设置
- 左侧边栏顶部提供固定的“新建下载”按钮
- 当任务列表为空时，列表区域会显示空状态引导和新建下载入口
- 任务详情页可以查看下载进度、速度、ETA、连接数、镜像、校验状态等信息

## 默认存储位置

- 下载目录：
  `~/Downloads/SwiftFetch`
- 数据库文件：
  `~/Library/Application Support/SwiftFetch/swiftfetch.sqlite3`

## 当前版本

- 程序名称：H-Download
- 版本号：1.0
- 最低系统版本：macOS 13+

## 签名说明

当前版本已经做了 ad-hoc 签名，可用于本机测试和私下分发。但它不是 Apple Developer ID 正式签名版本，因此在其他 Mac 上打开时，系统仍可能弹出安全提示。

## 技术架构

- UI：SwiftUI
- 下载引擎：DownloadManager / ChunkScheduler / MirrorSelector / AccelerationEngine
- 网络层：URLSession
- 持久化：SQLite
- 校验：CryptoKit / CommonCrypto 封装
- 并发：Swift async/await 与 actor
