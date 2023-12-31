
目前差量更新的代码范围（以下称作 更新范围代码）有：
- `src/__common__`
- `src/main`
- `src/index.js`

差量版本号说明：
	形如`[id].[YYYYMMDD]`，例如`0.20231109`
比较版本号大小仅仅使用id来比较，例如 `1.20231110` 大于`0.20231111`的，一下比较版本号都是id大小的变化
# 流程

1. 开发：修改 更新范围 代码
2. 构建：执行`npm run build -- --new`
3. 确认：确认本次差量更新的发布渠道
	- `delta-updater.json`中`channels`字段用来标识发布渠道；`%CLIENT_VERSION%`表示当前客户端版本；`%CURRENT_OS%`表示当前平台系统；`stable`为稳定版本，该字段可以用来做`alpha`或`beta`更新
4. 确认：确认灰度发布比例,`stagingPercentage`Int 用于标识灰度发布比例，选值范围为`[0,100]`
5. 发布：执行`npm run delta:release`，执行过程中会展示待发布信息和线上信息，请确认信息都正确且 __待发布版本号大于线上版本号__
6. 归档：每一个差量更新版本发布结束，请立刻以`delta-{主进程版本}-{差量更新版本}`为格式，新建`git tag`并推送到远程仓库，并新建发行版以说明本次更新的内容，可参照https://codeup.aliyun.com/6188cda5f1ae9b61971da6ac/izihun/ifonts_client_desktop/tags/release/detail/release-950ecc72-1cba-43?release=release-950ecc72-1cba-43