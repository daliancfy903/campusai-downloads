# CampusAI 1.1.0 Windows 安装指南

## 扫码安装

1. 用手机相机或微信扫描 CampusAI 下载二维码。
2. 在下载页确认版本是 **1.1.0**，下载 `CampusAI-Setup-1.1.0.exe`。
3. 可按下载页提供的 SHA-256 核对文件完整性。
4. 双击安装程序，按提示完成安装。CampusAI 默认安装到当前用户目录，不要求管理员权限。
5. 桌面出现 **CampusAI** 后双击，等待“CampusAI 已准备好”，主页面会自动打开。

学生不需要安装 Python、Node.js、npm、Git，也不需要打开 PowerShell。

## Windows 安全提示

当前测试版安装器可能没有 Authenticode 签名，Windows SmartScreen 因此可能显示未知发布者提示。请仅从
CampusAI 官方下载页取得文件并核对 SHA-256。CampusAI 不会要求关闭 Defender、SmartScreen 或 UAC。

## 第一次启动

启动窗口会显示准备进度。主页面的“本地运行状态”会显示：

- CampusAI 是否就绪；
- DeepSeek 是否配置；
- 语义检索是基础模式还是增强模式；
- OCR 是否就绪；
- 创建第一个项目入口。

没有 DeepSeek Key 时，本地浏览、Source、Draft、Artifact、Archive 和基础检索仍可使用。

## 配置 DeepSeek

在 CampusAI 启动窗口选择“配置 DeepSeek”，输入自己的 Key 后保存。界面不会回显完整 Key，诊断信息也不会
包含 Key。配置保存在当前 Windows 用户的本地配置目录，不进入安装目录、Git 或遥测。

## 语义检索与 OCR

- 基础 lexical retrieval 安装后即可使用。
- 约 500+ MiB 的增强语义模型不随 Lite Installer 静默下载；只有用户明确选择时才下载。
- OCR 模型随安装包提供，用于扫描 PDF；原生文本 PDF 不依赖 OCR。

## 数据位置与备份

项目、Sources、Drafts、Artifacts、History、Defense 和 Archives 位于：

`%LOCALAPPDATA%\CampusAI\data\`

程序升级和默认卸载不会删除此目录。重要项目仍应定期使用 CampusAI Archive 导出备份。

## 卸载和重装

从 Windows“已安装的应用”卸载 CampusAI。卸载程序默认保留用户数据；只有明确选择删除时才会清除
`%LOCALAPPDATA%\CampusAI`。重装或覆盖安装会继续使用已有数据、配置和模型。

## 常见问题

- **端口被占用**：退出其他 CampusAI 窗口或占用 3000/8000 的程序，再选择重试。
- **杀毒软件或文件锁**：允许当前安装结束，关闭占用文件的程序后重试；不要关闭 Defender。
- **Backend/Frontend 启动失败**：使用启动窗口的“复制诊断”，提交脱敏信息后重新安装。
- **可选模型缺失**：基础检索仍可使用；按界面提示显式安装增强模型。
- **安装损坏**：从正式下载页重新下载，核对 SHA-256 后覆盖安装。

诊断只包含版本、Windows、端口和能力状态，不包含 API Key、Source 内容或项目正文。
