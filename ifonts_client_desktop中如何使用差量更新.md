
目前差量更新的代码范围（以下称作 更新范围代码）有：
- `src/__common__`
- `src/main`
- `src/index.js`

差量版本号
# 流程
1. 开发：修改 更新范围 代码
2. 构建：执行`npm run build -- --new`
3. 确认：确认本次差量更新的发布渠道
	- `delta-updater.json`中`channels`字段用来标识发布渠道；`%CLIENT_VERSION%`表示当前客户端版本；`%CURRENT_OS%`表示当前平台系统；`stable`为稳定版本，该字段可以用来做`alpha`或`beta`更新
4. 确认：确认灰度发布比例,`stagingPercentage`Int 用于标识灰度发布比例，选值范围为`[0,100]`
5. 发布：执行`npm run delta:release`，执行过程中会展示待发布信息和线上信息，请确认信息都正确且待发布版本号大于线上版本号


# 2、构建


# 3、发布


# 4、归档