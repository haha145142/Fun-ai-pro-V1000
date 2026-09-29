# JevJarvis iOS · 狗头军师 + 恋爱大师版

这个仓库用于在没有 Mac 的情况下，通过 GitHub Actions 云编译 JevJarvis iOS。

## iPhone 使用方式

1. 在 GitHub 手机页面进入本仓库。
2. 点 Add file → Upload files。
3. 上传你拿到的 JevJarvis ZIP（文件名不同也可以，只要是 .zip）。
4. 提交后，打开 Actions。
5. 选择“云编译 · ZIP 解压后生成未签名 IPA”，点 Run workflow。
6. 运行成功后，在 Actions 运行记录下方的 Artifacts 下载 JevJarvis-unsigned-ipa。
7. 得到 JevJarvis-unsigned.ipa 后，用全能签等工具签名安装。

ZIP 里的工程会自动解压后执行 Xcode 构建，不需要 Mac。

> API Key 和模型配置由你在 App 内填写，本仓库不提供中转服务。
