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

- Chromium 93.0.4577.58.
    - [New in 93](https://developer.chrome.com/blog/new-in-chrome-93/)
    - [New in 92](https://www.chromestatus.com/features#milestone%3D92)
- Node v14.17.0.
    - [v14.17.0 release notes](https://github.com/nodejs/node/blob/master/doc/changelogs/CHANGELOG_V14.md#14.17.0)
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
- `electron`现在，在使用 x64 版本的 Node 时在 M1 MacBook 上安装该软件包将自动下载 Arm64 版本的 Electron，而不是 x64 版本 （开发者工具，性能分析g）。[#29953](https://github.com/electron/electron/pull/29953)

## 重大变化

- `nativeWindowOpen: true`现在是默认值。[#28552](https://github.com/electron/electron/pull/28552)