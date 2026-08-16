# 啊勾妮库 (AgoniLibrary)

Android 工具类库, 包含崩溃日志、反射、文件/IO、日志、通知、屏幕适配等实用工具。

## 模块说明

| 模块 | 说明 |
|------|------|
| `agonilibrary` | 工具类库(发布到 JitPack 的模块) |
| `app` | 示例/测试 App |

工具类代码位于 `io.github.zeroaicy.util` 包:
- `crash/` — 崩溃捕获与界面
- `reflect/` — 反射工具(HiddenApiBypass、ReflectPie、UnsafeX)
- `ContextUtil`、`DebugUtil`、`FileUtil`、`IOUtils`、`Log`、`MD5Util`、`NotificationUtil`、`ScreenUtil`、`SystemMemory`、`UriUtil`

## 发布到 GitHub + JitPack

1. 在 GitHub 上新建一个仓库(公开), 例如 `agonilibrary`
2. 把本仓库代码推送到 GitHub
3. 打一个版本 tag, 例如 `1.0.0`
4. 访问 <https://jitpack.io/#你的GitHub用户名/仓库名> , 点击 **Get it**, 页面上会显示构建状态和准确的依赖坐标

## 在别的项目中使用

1. 在 `settings.gradle`(或根 `build.gradle`)的 repositories 里加 JitPack:

```gradle
maven { url "https://jitpack.io" }
```

2. 在 `app/build.gradle` 的 dependencies 里添加依赖:

```gradle
implementation 'com.github.你的GitHub用户名.仓库名:agonilibrary:版本号'
```

> 例如仓库名是 `agonilibrary`, 用户名是 `agoni`:
> `implementation 'com.github.agoni.agonilibrary:agonilibrary:1.0.0'`
>
> 版本号可以是 GitHub 的 tag(如 `1.0.0`)、commit 哈希, 或 `master-SNAPSHOT`(最新提交)。
> 准确的坐标以 jitpack.io 页面显示的为准。

## 启用崩溃日志功能

在你的 App 的 `AndroidManifest.xml` 的 `<application>` 上添加 `android:name`:

```xml
<application
    android:name="io.github.zeroaicy.util.crash.CrashApplication"
    ... >
```

并在代码中调用:

```java
io.github.zeroaicy.util.DebugUtil.debug(getApplicationContext());
```
