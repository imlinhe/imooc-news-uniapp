# imooc-news

uni-app 项目，根据慕课网视频开发

### cloudfunction 云函数库

- db_init.json 云数据库初始化

### api 封装

- 自动批量导出

```js
const requireApi = require.context(
	// api目录的相对路径
	'.',
	// 是否查询子目录
	false,
	// 查询文件的后缀
	/.js$/
)

let module = {}

requireApi.keys().forEach(item => {
	if (item === './index.js') return
	// 相当于把 requireApi(item) push 到 module 中
	Object.assign(module, requireApi(item))
})

export default module
```