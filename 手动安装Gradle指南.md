# 手动安装Gradle解决超时问题指南

## 📂 Gradle缓存目录位置

您的Gradle缓存目录在：
```
C:\Users\80801\.gradle\wrapper\dists
```

## 📥 方法一：手动放置Gradle压缩包

### 步骤：

1. **确认您需要的Gradle版本**
   - 查看项目需要的版本：打开 `android/gradle/wrapper/gradle-wrapper.properties`
   - 当前项目需要的版本：`gradle-7.4.2-all.zip`

2. **找到您下载好的文件**
   - 确保文件名是：`gradle-7.4.2-all.zip`

3. **查看缓存目录结构**
   打开文件夹：`C:\Users\80801\.gradle\wrapper\dists`
   
   应该会看到类似这样的文件夹结构：
   ```
   .gradle/
   └── wrapper/
       └── dists/
           └── gradle-7.4.2-all/
               └── <一串随机字符>/
                   ├── gradle-7.4.2-all.zip.part  (这是未下载完的文件)
                   └── gradle-7.4.2-all.zip.ok    (如果有这个文件，说明下载完成)
   ```

4. **放置压缩包**
   - 将您下载好的 `gradle-7.4.2-all.zip` 复制到那个随机字符的文件夹中
   - 删除该文件夹中的 `.part` 和 `.lck` 文件（如果存在）
   - 创建一个空文件，命名为 `gradle-7.4.2-all.zip.ok`

5. **目录结构应该像这样**：
   ```
   C:\Users\80801\.gradle\wrapper\dists\gradle-7.4.2-all\<随机字符串>\
   ├── gradle-7.4.2-all.zip          (您下载的文件)
   └── gradle-7.4.2-all.zip.ok       (空文件，手动创建)
   ```

## 🔧 方法二：使用国内镜像源（推荐）

修改Gradle下载地址为国内镜像：

### 步骤：

1. **打开文件**
   ```
   d:\code_work\school_today_eat\android\gradle\wrapper\gradle-wrapper.properties
   ```

2. **修改下载地址**
   将 `distributionUrl` 改为国内镜像（比如腾讯云镜像）：
   
   **原内容：**
   ```properties
   distributionUrl=https\://services.gradle.org/distributions/gradle-7.4.2-all.zip
   ```
   
   **改为：**
   ```properties
   distributionUrl=https\://mirrors.cloud.tencent.com/gradle/gradle-7.4.2-all.zip
   ```

3. **其他可用的国内镜像**
   - 腾讯云：`https://mirrors.cloud.tencent.com/gradle/`
   - 华为云：`https://mirrors.huaweicloud.com/gradle/`
   - 阿里云：`https://maven.aliyun.com/mirror/gradle/`

4. **保存文件后重新运行构建命令**

## 📝 方法三：配置Gradle使用本地已安装的版本

如果您电脑上已经安装了Gradle，可以配置项目使用本地版本：

### 步骤：

1. **检查是否已安装Gradle**
   ```bash
   gradle --version
   ```

2. **如果已安装**
   - 在Android Studio中：`File` → `Settings` → `Build, Execution, Deployment` → `Build Tools` → `Gradle`
   - 选择 "Use local Gradle distribution"
   - 指定您本地Gradle的安装目录

## 🚀 完成后继续构建

配置好Gradle后，继续构建APK：

### 方式A：使用Android Studio
```bash
npx cap open android
```
然后在Android Studio中构建。

### 方式B：使用命令行
```bash
cd android
./gradlew assembleDebug
```

## 💡 提示

- **随机文件夹名称**：每次尝试下载时，Gradle会创建一个不同的随机字符文件夹
- **.ok文件**：这个文件告诉Gradle下载已完成，不需要再下载
- **.lck文件**：这是锁文件，表示正在下载中，可以安全删除

如果还有问题，请告诉我！
