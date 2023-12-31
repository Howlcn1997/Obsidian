# 12.x
## 重大变化

- 将默认值`crashReporter.start({ compress })`从更改`false`为`true`。[#25288](https://github.com/electron/electron/pull/25288)
- 将默认值更改`contextIsolation`为`true`。[#27949](https://github.com/electron/electron/pull/27949)
- 将默认值更改`worldSafeExecuteJavaScript`为`true`。[#27502](https://github.com/electron/electron/pull/27502)
- 已弃用该`remote`模块。它被替换为[`@electron/remote`](https://github.com/electron/remote). [#25293]
- 已弃用`new-window`WebContents 事件。它被替换为[`webContents.setWindowOpenHandler()`](https://releases.electronjs.org/releases/api/web-contents#contentssetwindowopenhandlerhandler). [第24517章](https://github.com/electron/electron/pull/24517)

# 13.x
## 重大变化

- 修复了 window.open() 参数_frameName_不再设置为窗口标题的问题。[#27481](https://github.com/electron/electron/pull/27481)
- 更改`session.setPermissionCheckHandler(handler)`为允许 的`handler`第一个参数`webContents`为`null`。[第19903章](https://github.com/electron/electron/pull/19903)

# 14.x
## 堆栈升级
- V8
    - [v9.3 blog post](https://v8.dev/blog/v8-release-93)  JS的编译速度提升44%
    - [v9.2 blog post](https://v8.dev/blog/v8-release-92)

## 重大变化

- 子窗口不再从其父窗口继承 BrowserWindow 构造选项。[#28550](https://github.com/electron/electron/pull/28550)
- 已弃用的`worldSafeExecuteJavaScript`选项已从 中删除`webPreferences`。[#28456](https://github.com/electron/electron/pull/28456)
- 从WebContents 事件中删除了已弃用的`additionalFeatures`属性。[#28548](https://github.com/electron/electron/pull/28548)`new-window``did-create-window`[](https://github.com/electron/electron/pull/28548)
- 删除了已弃用的选项`app.allowRendererProcessReuse`和 BrowserWindow`affinity`选项。[#26874](https://github.com/electron/electron/pull/26874)
# 15.x
## 修复

- 修复了以编程方式关闭可拖动无框架子窗口时潜在的崩溃。[#31027](https://github.com/electron/electron/pull/31027)
- `electron`现在，在使用 x64 版本的 Node 时在 M1 MacBook 上安装该软件包将自动下载 Arm64 版本的 Electron，而不是 x64 版本 （开发者工具，性能分析工具的修复）。[#29953](https://github.com/electron/electron/pull/29953)

## 重大变化

- `nativeWindowOpen: true`现在是默认值。[#28552](https://github.com/electron/electron/pull/28552)

# 16.x

## 重大变化

- 该`crashReporter`API 现在由 Linux 上的 Crashpad 提供支持。[#30278](https://github.com/electron/electron/pull/30278)
- 渲染器进程中使用`desktopCapturer.getSources`API 的做法已被弃用并将被删除。[30721](https://github.com/electron/electron/pull/30721)

# 17.x

## 修复

- 修复了在 macOS Big Sur 及更新版本上使用 child_process.spawn 和相关方法时的缓慢问题。[#](https://github.com/electron/electron/pull/33408) 33408 （也在[16、18](https://github.com/electron/electron/pull/33405) [）](https://github.com/electron/electron/pull/33407) 【目前renderer的解压缩任务是使用IPC转接给主进程执行】
## 重大变化

- `desktopCapturer.getSources`现在仅在主进程中可用。[第30720章](https://github.com/electron/electron/pull/30720)

# 18.x
## 重大变化

- 删除了旧的`BrowserWindowProxy`基于`window.open`. 这也`nativeWindowOpen`从 中删除了该选项`webPreferences`。[#29405](https://github.com/electron/electron/pull/29405)

# 20.x

## 重大变化

- 渲染器现在默认处于沙箱状态，除非指定`nodeIntegration: true`或。[#35125](https://github.com/electron/electron/pull/35125)`sandbox: false`[](https://github.com/electron/electron/pull/35125)
- 使用 nan 构建本机模块时添加了保护措施。重建本机模块时，请使用 node-gyp >=8.4.0 和 electro-rebuild >=3.2.9。[#35160](https://github.com/electron/electron/pull/35160)

# 21.x
## 重大变化

- 为外部缓冲区启用 V8 内存笼。有关更多详细信息，请参阅 https://www.electronjs.org/blog/v8-memory-cage。[#34724](https://github.com/electron/electron/pull/34724)  【V8堆大小减少40%，CPU、GC性能提升5% - 10%， 但会导致ffi-napi无法使用，因为ffi-napi还在使用v8栈内内存，且ffi-napi已无人维护】
# 22.x
## 修复

- 修复了已弃用`gpu-process-crashed`/`renderer-process-crashed`事件被发出两次且参数不正确的问题。[#40119](https://github.com/electron/electron/pull/40119) （也在[24](https://github.com/electron/electron/pull/40110) , [25](https://github.com/electron/electron/pull/40113) , [26](https://github.com/electron/electron/pull/40112) , [27](https://github.com/electron/electron/pull/40111)）
- 修复了在 Electron 中运行 Node.js 时 v8.serialize() 中的内存泄漏。[#37774](https://github.com/electron/electron/pull/37774) （也在[23](https://github.com/electron/electron/pull/37030)中）
## 重大变化

- 添加了 WebContents`input-event`事件。
    - 已弃用的 BrowserWindow`scroll-touch-*`事件。[#35531](https://github.com/electron/electron/pull/35531)
- 已弃用的`new-window`事件已被删除。[#34526](https://github.com/electron/electron/pull/34526)