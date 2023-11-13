
目前差量更新的代码范围（以下称作 更新范围代码）有：
- `src/__common__`
- `src/main`
- `src/index.js`
# 流程
1. 修改 更新范围 代码
2. 执行`npm run build -- --new`
3. 确认本次差量更新的发布渠道
	- `delta-updater.json`中`channels`字段用来标识发布渠道；`%CLIENT_VERSION%`表示当前客户端版本；`%CURRENT_OS%`表示当前平台系统；`stable`为稳定版本，该字段可以用来做`alpha`或`beta`


# 2、构建


# 3、发布


# 4、归档