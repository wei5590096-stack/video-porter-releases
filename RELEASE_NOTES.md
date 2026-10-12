轻存 2.8.2 修复了 macOS 下载助手被禁用、重启后无法运行的问题，升级了官方视频解析器，并改善当前代理下的连接超时处理。

## 本次更新

- macOS 安装器重新启用本地下载服务，并验证启动成功。
- 解析器升级至官方 yt-dlp 2026.08.19。旧解析器可随签名应用升级通过官方更新器补齐，失败时保留现有版本。
- 解析和下载跟随已启用的 macOS 系统代理；仅连接错误时重试现有系统路由。
- 支持公开 HLS `.m3u8` / DASH `.mpd` 链接由本地助手处理。
- Windows 安装器固定解析器版本并检查官方 SHA-256。

## 下载与升级

- [macOS 安装包](https://github.com/wei5590096-stack/video-porter-releases/releases/download/v2.8.2/video-downloader-macos.zip)
- [Windows 安装包](https://github.com/wei5590096-stack/video-porter-releases/releases/download/v2.8.2/video-downloader-windows.zip)

已安装且服务正常运行：在轻存底部点“检查更新”。如果提示“下载服务未启动”，请解压完整安装包，重新运行 `Install-macOS.command` 或 `Install-Windows.cmd`。Edge 始终加载安装器提供的固定 `extension` 目录。

## 验证与适用范围

- 155 项逻辑测试、22 项浏览器扩展测试通过。
- Mac 的扩展、助手均已安装为 2.8.2，完成 CC0 公开视频实际下载，并确认 H.264 视频与 AAC 音频。
- Windows 包完成结构与校验检查，未在 Windows 真机执行安装。
- 各平台可能要求登录、授权或可用网络线路；本版本不绕过 DRM、付费墙、地区限制或其他访问控制。以上测试不代表每个平台、每个链接均已通过真实下载验证。

安装包包含扩展及本地助手；`latest.json` 和签名更新包用于自动更新，普通用户无需单独下载。
