# 杂项
## 模块ID
模块ID是表示一个模块的字符串，允许使用大小写英文字母、数字、英文句号、下划线，建议使用Java语言包名命名<sup>[1]</sup>。

更新时可以改变模块的模块ID，但是这样原本依赖于这个模块的模块将会失效。这是一个明确表示其不再兼容旧版API的方法。同时依然可以使用原本的GID。

示例：
```javascript
cavenightingale.mcbbs.modules.noeee
```
## ML Global ID 全局ID
全局ID（下称GID）代表了一个文件的下载地址。GID的格式如下

其中`<文件名>`不需要写文件后缀，会根据所需的文件类型确定后缀
```
<github/gitee>:<用户名>:<仓库名>:<文件名>:<分支名>
```
github可省略不写
```
<用户名>:<仓库名>:<文件名>:<分支名>
```
默认分支名可以不写
```
<用户名>:<仓库名>:<文件名>
```
文件名若与仓库名相同也可以不写
```
<用户名>:<仓库名>
```
若仓库在MCBBS-Loader名下则用户名也可以不写
```
<仓库名>
```
以上的每个&lt;...&gt;都可以用~表示和当前文件相同，称为相对GID。例如当前模块仓库下的dep.js可以用如下表示
```
~:~:~:dep:~
```

目前GID可以用于代替`updateURL`中的链接以及`depend`指定依赖下载地址。也可以用于加载JS和CSS<sup>[2]</sup>。

---
1) 撤回旧版文档中关于使用文件名命名代替包名命名的建议。
2) 参考api章节