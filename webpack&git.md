# webpack构建流程
从配置文件初始化参数，
加载plugin,初始化compiler对象,从entry出发，针对module调用loader,组合成chunk,再输出成文件。

# 常见的loader
babelloader:将es6转换成es5

# 常见的plugin

# 热更新原理
在不需要刷新整个页面的同时更新模块，能够提升开发的效率和体验。热更新时只会局部刷新页面上发生了变化的模块，同时可以保留当前页面的状态。

浏览器获取到chunk diff,通过他们之间的websocket,webpack-serve发送更新，并带上hash,客户端对比时就会发送ajex请求，来进行更新。

# 提高构建速度
js,css,html压缩\
缩小打包域\

# git常用命令
查看分支：git branch\
合并分支：git merge\
切换到分支xxx：git checkout xxx\
创建分支xxx并切换到该分支：git checkout -b xxx

# git merge和git rebase的区别
git merge会⾃动创建⼀个新的commit，如果合并时遇到冲突的话，只需要修改后重新commit。
