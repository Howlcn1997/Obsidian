# 12.x
## 
- 将默认值`crashReporter.start({ compress })`从更改`false`为`true`。[#25288](https://github.com/electron/electron/pull/25288)
- 将默认值更改`contextIsolation`为`true`。[#27949](https://github.com/electron/electron/pull/27949)
- 将默认值更改`worldSafeExecuteJavaScript`为`true`。[#27502](https://github.com/electron/electron/pull/27502)
- 已弃用该`remote`模块。它被替换为[`@electron/remote`](https://github.com/electron/remote). [#25293]
- 已弃用`new-window`WebContents 事件。它被替换为[`webContents.setWindowOpenHandler()`](https://releases.electronjs.org/releases/api/web-contents#contentssetwindowopenhandlerhandler). [第24517章](https://github.com/electron/electron/pull/24517)