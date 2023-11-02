
# files-delta-updater

## Installation

You need node.js and npm.

```
npm install files-delta-updater --save-dev
```

## Usage

```
const { DeltaUpdater } = require('files-delta-updater');

const deltaUpdater = new DeltaUpdater({
	baseRootPath: "C:\\Program Files\\myapp\\dist",
	updateRootPath: "C:\\Program Files\\myapp_source\\dist",
	remoteRootUrl: "https://oss.template.com/myapp", 
	channels: ["1.0.0","stable"]
})

deltaUpdater.getLatestVersionAfterSwitch().then(({path, version}) => {
	console.log(path); // The directory where the latest version of the file is located
	console.log(version); // the latest version

	deltaUpdater.checkUpdate(); // Start checking for updates
})
```


`new DeltaUpdater(options)`
- `options` DeltaUpdaterConfig
	- `baseRootPath` string (必填) - 更新器基础目录。当无已下载的更新资源时，则更新器使用该目录进行工作。
	- `updateRootPath` string (必填) - 更新器版本管理目录。新生成的目录将保存在此目录下。
	- `remoteRootUrl` string (必填) - 远程资源的URL。
	- `channels` string[] (可选) - 更新渠道。分渠道更新资源。
	- `clearOldVersion` boolean (可选) - 是否清理老版本资源。默认值为`true`，当更新器qie'huan'z