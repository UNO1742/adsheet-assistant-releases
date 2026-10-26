# 广告表格助手：公开更新源

本仓库仅用于分发 Windows 安装包、版本清单和发布说明。应用源码保存在独立私有仓库，不在此公开；本仓库不收集用户的广告报告。

## 下载和使用

从 [最新正式版](https://github.com/UNO1742/adsheet-assistant-releases/releases/latest) 下载 `AdSheetAssistant-Setup-1.2.0.exe`（后续版本文件名随版本号变化），关闭旧程序后双击安装。

需要 Windows 10/11 64 位、桌面版 Microsoft Excel。无需安装 Python 或 Node。安装包保留应用图标、桌面快捷方式和卸载入口。

1.1.0 起可在主界面点击“检查更新”，确认后下载并显示进度，下载可取消；校验通过后再确认安装。程序先关闭再安装，可选择安装后重新打开。1.0.1 及更早版本需首次手动安装。

## 更新接口

- Release 查询：`https://api.github.com/repos/UNO1742/adsheet-assistant-releases/releases/latest`
- 每个正式 Release 包含 `latest.json`、完整安装包和 `SHA256SUMS.txt`。
- 程序使用 Release 附件中的清单；仓库根目录的同名文件仅供查看。
- 手动检查缓存至少 60 秒，不做后台轮询，避免消耗公开 API 额度。
- 清单字段：`version`、`minimum_supported_version`、`notes`、`installer_url`、`sha256`。最低支持版本指已安装应用版本。

## 校验及常见问题

PowerShell：`Get-FileHash .\AdSheetAssistant-Setup-1.2.0.exe -Algorithm SHA256`，结果与该 Release 的清单和 SHA256SUMS.txt 对比。

当前安装包未使用发布者数字签名。SHA-256 提供完整性检查，不等同于发布者身份认证。不要运行来自其他来源且摘要不匹配的安装包。

网络或限流错误请稍后重试；校验错误应重新下载并核对清单，不应继续安装。更新失败或取消会保留当前版本。不要在主程序运行时手动覆盖 EXE。

## 发布者维护

只上传最终安装包、清单、摘要和发布说明；勿上传源码、表格、日志、令牌或本机路径。先构建验收，计算最终安装包摘要，再创建版本号匹配的 Release。先以草稿上传全部附件，核对后发布；不要静默替换已发布安装包。

使用完整安装包更新，不使用未经验证的差分补丁。保留旧 Release 以便人工恢复；当前程序默认禁止降级。

1.1.0 检查更新存在打包缺件问题，需手动安装一次 1.1.1 修复包。

## 1.2.0 的指标汇总

导入原始报告可直接生成到普通指标汇总。已经有 Sheet2 时，使用“选择文件继续”或“使用当前Excel继续”。后者包含当前工作簿的未保存修改，结果另存副本。

CTR、CPC、ACOS、CVR、每单广告费保留 Excel 公式，分母为零时显示空白。原始报告、Sheet1、真实 Sheet2 透视表均保留；已有同结构汇总表会复用。

只完成指标计算，不做关键词筛选、词根分析或投放调整。
