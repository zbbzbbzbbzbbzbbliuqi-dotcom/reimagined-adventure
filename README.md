# 我的头像（Flutter Android）

一个离线的 Android 头像选择/预览/保存 App。

## 功能

- 使用 Android Photo Picker 选择一张图片。
- 本地内存预览，不上传服务器。
- 使用 Gal 保存到系统相册。
- 不需要账号、网络、定位、通讯录、短信等权限。
- Android 10+ 使用系统存储机制；仅针对 API 29 保留受限的 WRITE_EXTERNAL_STORAGE 声明，并使用 requestLegacyExternalStorage。

## GitHub Actions

仓库内的 `.github/workflows/build_apk.yml` 会在 `main` 推送或手动运行时：

1. 安装 Java 17
2. 安装 Flutter Stable
3. `flutter pub get`
4. `flutter analyze`
5. `flutter build apk --release`
6. 上传 `app-release.apk` 为 GitHub Actions Artifact

## 手机上下载 APK

GitHub 仓库 → Actions → Build Android APK → 选择一次运行 → 等待完成 → 页面底部 Artifacts → 下载 `avatar-picker-release-apk` → 解压 → 安装 `app-release.apk`。

## 注意

首次在 Android 10/更低版本上保存到相册时，系统可能根据版本要求处理存储权限。Android 10+ 不使用 WRITE_EXTERNAL_STORAGE。
