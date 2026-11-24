# 节拍画册 (BeatSync Gallery) Android APK 打包工程

本工程已针对 Android WebView 做了完整适配：
- 使用 `WebViewAssetLoader` 在离线环境下以 HTTPS 安全上下文运行，确保 **麦克风收音 (`getUserMedia`)** 与 **Web Audio API** 正常可用。
- 已重写 `onShowFileChooser`（支持多选本地图片、选择本地音频）与 `onPermissionRequest`（动态申请录音权限）。
- 已配置屏幕常亮、沉浸式状态栏、横竖屏切换不重载。

## 方式一：免装环境，用 GitHub 云端一键生成 APK（最推荐）
1. 在 GitHub 新建一个仓库（公开或私有均可）。
2. 将本压缩包解压后的所有文件（包含隐藏目录 `.github/workflows/build-apk.yml`）上传到仓库根目录。
3. 打开仓库顶部的 **Actions** 页面，等待 `Build BeatSync Gallery APK` 运行完成（约 2 分钟）。
4. 点击完成的构建记录，在底部 **Artifacts** 下载 `BeatSyncGallery-APK`，解压即可得到 `app-debug.apk`，传到安卓手机直接安装。

## 方式二：用 Android Studio 本地构建
1. 解压后用 Android Studio 选择 `Open` 打开项目文件夹。
2. 等待 Gradle Sync 完成。
3. 点击顶部菜单 **Build -> Build Bundle(s) / APK(s) -> Build APK(s)** 即可输出安装包。

## 替换网页版本
如果你想使用此前对话预览中导出的 HTML 文件，只需将其重命名为 `index.html`，直接覆盖替换 `app/src/main/assets/index.html` 后重新构建即可。
