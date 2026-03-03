# Flutter 国内镜像（解决无法连接 GitHub）

当出现 `Failed to connect to github.com port 443` 时，用国内镜像替代。

---

## 第一步：设置 Flutter 镜像环境变量

在终端执行（**建议写进配置文件，长期生效**）：

```bash
# 清华镜像（二选一即可）
export FLUTTER_STORAGE_BASE_URL="https://mirrors.tuna.tsinghua.edu.cn/flutter"
export PUB_HOSTED_URL="https://mirrors.tuna.tsinghua.edu.cn/dart-pub"
```

**写入配置文件，以后每次开终端都生效：**

```bash
echo 'export FLUTTER_STORAGE_BASE_URL="https://mirrors.tuna.tsinghua.edu.cn/flutter"' >> ~/.zprofile
echo 'export PUB_HOSTED_URL="https://mirrors.tuna.tsinghua.edu.cn/dart-pub"' >> ~/.zprofile
source ~/.zprofile
```

---

## 第二步：让 Flutter SDK 本身不再访问 GitHub

你的 Flutter 装在 **桌面** 的 `development/flutter` 下，那个目录其实是一个 git 仓库，默认指向 GitHub，所以会执行 `git fetch --tags` 失败。

**做法：把该仓库的远程地址改成国内镜像**

在终端执行（路径按你的实际安装位置改）：

```bash
cd ~/Desktop/development/flutter
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/flutter-sdk/flutter.git
```

若你的 Flutter 在别处，把 `~/Desktop/development/flutter` 改成实际路径即可。

---

## 第三步：再执行 Flutter 命令

**新开一个终端**（或执行 `source ~/.zprofile`），然后：

```bash
cd /Users/ryan_zhao/Desktop/cursor/food_tracker
flutter create .
flutter pub get
flutter run
```

若仍有报错，把完整报错贴出来即可。
