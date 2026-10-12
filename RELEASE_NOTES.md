轻存 2.8.3 是针对 Windows“下载服务未启动”的预发布修复包。上一版 Windows 安装验证不足，遗漏了 PowerShell 5.1 的编码与下载命令兼容问题。

## 修复

- Windows PowerShell 安装脚本使用 UTF-8 BOM，避免含中文的脚本被当作 ANSI 解码。
- 下载命令使用 `-UseBasicParsing`，避免依赖 Internet Explorer DOM 组件或停在额外确认提示；二进制校验文件支持正确解码。
- 使用 PowerShell 启动助手，不再依赖 VBScript；记录 `companion.log` 和 `companion-error.log`。
- 检查 Node.js 版本，复用可用的专用运行环境；健康检查核对助手版本与 Windows 平台。
- 更新器兼容新的 PowerShell 启动入口，并保留旧版入口的回退。

## Windows 修复步骤

1. [下载 Windows 修复安装包](https://github.com/wei5590096-stack/video-porter-releases/releases/download/v2.8.3/video-downloader-windows.zip)，核对同版本 `SHA256SUMS.txt` 后完整解压。
2. 运行最外层 `Install-Windows.cmd`。不要只更新或加载浏览器扩展。
3. Edge 固定加载 `%LOCALAPPDATA%\Video Porter\extension`，已有实例点击“重新加载”。
4. 检查 `http://127.0.0.1:48620/health`，应返回 `ok: true`、`version: 2.8.3`、`platform: win32`。
5. 若仍失败，运行 `%LOCALAPPDATA%\Video Porter\start-companion.cmd` 查看前台错误，并检查 `companion-error.log`。

## 验证范围

- 155 项现有逻辑测试与构建通过。
- 使用 PowerShell 7 的解析器，在 macOS 上复现旧脚本按 CP1252 解码出现 13 个语法错误；新安装脚本和生成的启动脚本无语法错误，中文、空格、撇号路径通过检查。
- 发行包已检查 UTF-8 BOM、版本、脚本结构与 SHA-256；签名更新包通过校验。
- Win11 原生安装、实际后台启动与下载尚未验证，因此本版本标为预发布。以上脚本检查不能替代 Windows 真机验证。

既有稳定版仍为 2.8.2。服务离线时无法从扩展内升级，需要重新运行上述修复安装包。
