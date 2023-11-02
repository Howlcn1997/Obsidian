
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
	baseRootPath: "/The/Base/Source/Path", // Updated most basic resource files
	updateRootPath: "/The/New/Source/Path", // The directory where the updated files are located
	remoteRootUrl: "/The/Origin/Source/Url", // Remote resource address
	channels: ["version","win32","stable"], // Configuration updated by channel
	clearOldVersion: true, // Whether to clean up old version resource files
	versionAvailable: (localVersion, remoteVersion) => localVersion !== remoteVersion, // Customize whether to enable upgrades based on version
	requestInstanceCreator: function (axios) { return axios.create({ timeout: 6000 }) }, // The axios instance used by the custom updater to check for updates
})

deltaUpdater.getLatestVersionAfterSwitch().then(({path, version}) => {
	console.log(path); // The directory where the latest version of the file is located
	console.log(version); // the latest version

	deltaUpdater.checkUpdate(); // Start checking for updates
})
```


`new DeltaUpdater(options)`
- `options` DeltaUpdaterConfig
	- `baseRootPath` string (必填) - 更新器基础目录。当无已下载的更新资源时，则更新器使用该目录进行工作
	- `updateRootPath` string (必填) - 更新zai