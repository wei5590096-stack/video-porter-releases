# 轻存 2.8.1

> 本次版本重点解决扩展与本地下载服务版本不同步的问题，并重新整理首次安装流程。建议所有 2.7.x 和 2.8.0 用户升级。

## 立即下载

| 系统 | 安装包 | 使用方式 |
| --- | --- | --- |
| macOS | **[下载 macOS 安装包](https://github.com/wei5590096-stack/video-porter-releases/releases/download/v2.8.1/video-downloader-macos.zip)** | 解压后右键打开 `Install-macOS.command` |
| Windows 10/11 | **[下载 Windows 安装包](https://github.com/wei5590096-stack/video-porter-releases/releases/download/v2.8.1/video-downloader-windows.zip)** | 完整解压后双击 `Install-Windows.cmd` |

普通用户只需要下载上面两个 ZIP 之一。`latest.json`、`*.bundle.json` 和 `SHA256SUMS.txt` 是程序自动更新与校验使用的文件，不需要手动打开。

## 版本亮点

### 版本真正统一

- 扩展、本地下载服务、远程更新包和首次安装包统一为 `2.8.1`。
- 插件会分别检查扩展版本和下载服务版本，不再把两个版本混为一谈。
- 发现不一致时显示“版本需要同步”，并提供修复入口。

### 安装流程更可靠

- macOS 与 Windows 都会把扩展安装到固定目录。
- 安装包内部的扩展文件改为封装资源，避免误加载临时解压目录。
- 安装完成后自动打开 Edge 扩展管理页和正确的 `extension` 文件夹。
- 新增固定扩展 ID，从 2.8.1 开始，后续升级不再因为路径变化产生多个扩展。

### 更新过程更稳定

- 限制更新后的自动重载次数，避免弹窗反复关闭。
- 更新文件继续使用 Ed25519 签名和 SHA-256 摘要校验。
- 安装前保留可回退版本，更新失败时不会破坏现有可用版本。

## 产品预览

<table>
  <tr>
    <td align="center" width="50%">
      <img src="https://raw.githubusercontent.com/wei5590096-stack/video-porter-releases/main/assets/screenshots/popup-ready-2.8.1.png" alt="轻存识别与下载界面" width="380"><br>
      <strong>复制链接，一步保存</strong>
    </td>
    <td align="center" width="50%">
      <img src="https://raw.githubusercontent.com/wei5590096-stack/video-porter-releases/main/assets/screenshots/popup-repair-2.8.1.png" alt="轻存修复界面" width="380"><br>
      <strong>问题就地修复</strong>
    </td>
  </tr>
</table>

<p align="center">
  <img src="https://raw.githubusercontent.com/wei5590096-stack/video-porter-releases/main/assets/screenshots/settings-dark-2.8.1.png" alt="轻存设置界面" width="900"><br>
  <strong>自动跟随系统主题的简洁设置页面</strong>
</p>

## 首次安装

1. 完整解压下载的 ZIP。
2. 运行最外层的 `Install-macOS.command` 或 `Install-Windows.cmd`。
3. 等待安装程序显示“安装完成”。
4. 在 Edge 中打开“开发人员模式”。
5. 点击“加载解压缩的扩展”。
6. 选择安装程序自动打开的固定 `extension` 文件夹。

请勿选择安装包中的 `payload`、`companion` 或 `scripts` 文件夹。

## 旧版本升级说明

如果 Edge 中同时出现 2.7.7 和 2.8.1：

1. 保留并启用 2.8.1。
2. 停用旧版 2.7.7。
3. 确认新版能够正常打开后，再删除旧版。

这次需要进行一次固定目录迁移；从 2.8.1 开始，后续稳定版可以继续使用插件中的“检查更新”。

## 测试与校验

- 116 项核心逻辑与平台适配测试通过。
- 22 项真实浏览器扩展测试通过。
- macOS 与 Windows 安装包版本均核对为 2.8.1。
- 所有公开发布资产均已上传并生成 SHA-256 校验值。

## 使用边界

轻存仅用于用户有权访问和保存的公开或已获授权内容，不破解 DRM，不绕过登录、会员、付费墙、地区限制或其他访问控制。

遇到问题可前往 [Issues](https://github.com/wei5590096-stack/video-porter-releases/issues) 提交反馈。请勿上传 Cookie、账号密码、访问令牌或其他隐私信息。
