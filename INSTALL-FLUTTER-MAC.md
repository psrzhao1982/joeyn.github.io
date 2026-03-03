# Mac 上安装 Flutter

任选一种方式即可。

---

## 方式一：官网下载（推荐）

1. 打开 **https://docs.flutter.dev/get-started/install/macos**
2. 点击 **Download Flutter SDK**，或直接：**https://storage.googleapis.com/flutter_infra_release/releases/stable/macos/flutter_macos_arm64_*.zip**（Apple Silicon）或 **flutter_macos_*.zip**（Intel）
3. 解压到目录，例如：`~/development/flutter`（不要放在需要 sudo 的目录）
4. 把 Flutter 加到 PATH，在终端执行（把路径改成你的解压位置）：
   ```bash
   echo 'export PATH="$HOME/development/flutter/bin:$PATH"' >> ~/.zprofile
   source ~/.zprofile
   ```
5. 验证：
   ```bash
   flutter --version
   flutter doctor
   ```
6. 按 `flutter doctor` 的提示安装缺失项（Xcode、Android Studio、命令行工具等）

---

## 方式二：用 Homebrew 安装

若已安装 Homebrew：

```bash
brew install --cask flutter
```

然后**新开一个终端**，执行：

```bash
flutter --version
flutter doctor
```

---

## 安装完成后

在项目目录执行：

```bash
cd /Users/ryan_zhao/Desktop/cursor/food_tracker
flutter create .
flutter pub get
flutter run
```

然后可按 `PROMPT_FOR_CURSOR.md` 用 Cursor Agent 生成完整代码。
