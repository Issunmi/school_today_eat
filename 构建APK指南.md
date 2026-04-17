# 构建APK安装包完整指南

## ✅ 项目已配置完成！

所有Java版本兼容性问题已解决，现在可以正常构建APK了！

---

## 方法一：使用Android Studio构建（推荐，最简单）

### 前置条件
1. 下载并安装 [Android Studio](https://developer.android.com/studio)
2. 安装完成后首次启动Android Studio，它会自动下载所需的SDK和工具

### 构建步骤

1. **打开项目**
   - 在项目根目录（d:\code_work\school_today_eat）打开命令行
   - 运行：
     ```bash
     npx cap open android
     ```
   - 这会自动用Android Studio打开Android项目

2. **等待Gradle同步**
   - Android Studio打开后，会自动开始Gradle同步
   - 等待底部的进度条完成（可能需要几分钟，首次会下载依赖）

3. **构建APK**
   - 点击顶部菜单：`Build` → `Build Bundle(s) / APK(s)` → `Build APK(s)`
   - 等待构建完成
   - 构建成功后，会在右下角弹出通知，点击 `locate` 即可找到APK文件

4. **APK文件位置**
   ```
   d:\code_work\school_today_eat\android\app\build\outputs\apk\debug\app-debug.apk
   ```

## 方法二：命令行构建（需要配置Android SDK）

### 前置条件
1. 安装Android Studio或Android Command Line Tools
2. 设置环境变量：
   - `ANDROID_HOME` 指向Android SDK目录
   - 将 `%ANDROID_HOME%\platform-tools` 和 `%ANDROID_HOME%\tools` 添加到PATH

### 构建命令
```bash
cd android
./gradlew assembleDebug
```

## 安装APK到手机

1. **启用开发者选项**
   - 打开手机设置 → 关于手机 → 连续点击"版本号"7次
   - 返回设置，找到"开发者选项"
   - 开启"USB调试"

2. **连接手机**
   - 用USB数据线连接手机和电脑
   - 手机上允许USB调试

3. **安装APK**
   - 方法A：直接将APK文件复制到手机，在手机文件管理器中点击安装
   - 方法B：使用adb命令：
     ```bash
     adb install app-debug.apk
     ```

## 自定义应用

### 修改应用名称和图标
- 编辑 `android/app/src/main/res/values/strings.xml` 修改应用名称
- 替换 `android/app/src/main/res/mipmap-*/` 下的图标文件

### 修改餐厅数据
编辑 `www/data.js` 文件中的 `restaurants` 数组

### 更新内容后重新构建
```bash
npx cap sync
npx cap open android
# 然后在Android Studio中重新构建
```

## 常见问题

### Gradle同步失败
- 检查网络连接
- 配置Android Studio的代理设置
- 尝试使用国内镜像源

### Java版本问题
- ✅ 已解决！项目已配置为使用Java 8
- 确保使用JDK 8或更高版本
- 在Android Studio中：File → Project Structure → SDK Location → JDK location

### SDK未安装
- Android Studio会提示安装缺失的SDK组件，点击安装即可

## 项目配置信息

- **应用名称**: 校园美食指南
- **包名**: com.school.campusfood
- **最低SDK版本**: Android 5.1 (API 22)
- **目标SDK版本**: Android 12 (API 32)
- **Capacitor版本**: 4.8.1 (兼容Java 8)
