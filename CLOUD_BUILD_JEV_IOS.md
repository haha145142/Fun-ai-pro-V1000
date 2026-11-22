# 狗头军师 iOS 云编译（未签名 IPA）

本仓库的 GitHub Actions 会从上游下载 iOS 源码，并在 GitHub 的 macOS runner 上编译成 **iPhone 设备版未签名 IPA**。无需 Mac；下载 IPA 后由你用全能签重新签名安装。

## 云编译步骤（iPhone 操作）

1. 打开本仓库： https://github.com/haha145142/Fun-ai-pro-V1000
2. 点 **Actions**。
3. 选择 **云编译狗头军师 iOS 未签名 IPA**。
4. 点 **Run workflow**，上游源码分支保持默认 `main`。
5. 等待任务完成（通常数分钟至几十分钟，首次可能更久）。
6. 打开本次 workflow run 页面底部 **Artifacts**，下载 `Jev-GoutouJunshi-unsigned-IPA`。
7. 解压 artifact ZIP，取出 `Jev-GoutouJunshi-unsigned.ipa`，导入全能签，选择自己的证书/描述文件签名并安装。

## 签名注意事项

- 这是**未签名 IPA**，不能直接安装；必须用自己的证书或个人签名方式重新签名。
- App、键盘扩展、截图扩展需要使用一致的签名 Team 和 App Group。若全能签提示 App Groups / Keychain Sharing 权限不匹配，需在签名工具中处理相应 entitlements，或改用自己的 Apple Team 配置后重新构建。
- 安装后：设置 → 通用 → 键盘 → 添加新键盘 → 狗头军师；开启「允许完全访问」以便联网调用模型和读取剪贴板。
- 模型 API Key 在 App 内自行填写。不要把 API Key、证书、P12 或 provisioning profile 上传到 GitHub。
- iOS 端分析需要手动复制聊天内容后点键盘分析；发送仍由你自己确认。可选直播/OCR功能会使用 iOS 系统广播录屏提示，识别文本仅在触发分析时发往你配置的模型服务。

## 源码来源

上游： https://github.com/shengjidaguai-china/goutoujunshi-jev-chat  
iOS 工程：`integrations/jev_ios/GoutouJunshi.xcodeproj`

工作流仅编译上游公开源码，不修改上游仓库。
