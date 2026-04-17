# 校园美食指南 - 校园菜单汇总应用

一个使用 Material Design 3 设计风格的校园餐饮菜单汇总应用，已使用 Capacitor 配置为 Android 原生应用。

## 功能特性

- 📱 Material Design 3 UI 界面
- 🏪 展示多个校园餐厅信息
- 📋 详细的菜单展示
- 🔍 餐厅和菜品搜索功能
- 🏷️ 按菜系分类筛选
- ⭐ 餐厅评分显示
- 📍 餐厅位置和营业时间信息

## 项目结构

```
school_today_eat/
├── www/                      # Web 应用源码
│   ├── index.html           # 主 HTML 文件
│   ├── styles.css           # Material Design 3 样式
│   ├── data.js              # 餐厅和菜单数据
│   └── app.js               # 应用逻辑
├── android/                  # Android 原生项目
├── package.json             # NPM 配置
└── capacitor.config.json    # Capacitor 配置
```

## 构建 APK 步骤

### 前置要求

1. 安装 [Android Studio](https://developer.android.com/studio)
2. 安装 Android SDK (API 21 或更高版本)
3. 配置 Java 开发环境 (JDK 8 或更高版本)

### 使用 Android Studio 构建

1. **打开项目**
   ```bash
   npx cap open android
   ```
   
2. **在 Android Studio 中**
   - 等待 Gradle 同步完成
   - 点击菜单: `Build` → `Build Bundle(s) / APK(s)` → `Build APK(s)`
   - 构建完成后，点击通知中的 `locate` 查看 APK 文件

3. **APK 文件位置**
   ```
   android/app/build/outputs/apk/debug/app-debug.apk
   ```

### 命令行构建 (可选)

如果您已配置好 Android SDK 环境，可以使用命令行构建：

```bash
cd android
./gradlew assembleDebug
```

## 更新应用内容

1. 修改 `www/` 目录下的文件
2. 同步到 Android 项目：
   ```bash
   npx cap sync
   ```
3. 重新构建 APK

## 自定义餐厅数据

编辑 `www/data.js` 文件中的 `restaurants` 数组来自定义餐厅和菜单信息。

## 技术栈

- **前端**: HTML5, CSS3, JavaScript (原生)
- **UI**: Material Design 3
- **原生容器**: Capacitor 5
- **平台**: Android 5.0+ (API 21+)
