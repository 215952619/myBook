# gitbook 快速入门

*前提：需要安装node环境*

* <code>npm install gitbook-cli -g</code> 下载全局gitbook包
* <code>gitbook -V</code> 查看版本号
* <code>gitbook ls</code> 列出本地所有的gitbook版本
* <code>gitbook init</code> 初始化
* <code>gitbook install</code> 安装插件
* <code>gitbook serve</code> 预览
* <code>gitbook build</code> 生成
* <code>gitbook build --gitbook=2.6.7</code> 生成时指定gitbook的版本, 本地没有会先下载
* <code>gitbook uninstall 2.6.7</code> 卸载指定版本号的gitbook
* <code>gitbook fetch [version]</code> 获取[版本]下载并安装<版本>
* <code>gitbook --help</code> 显示gitbook-cli帮助文档
* <code>gitbook help</code> 列出 gitbook 所有的命令
* <code>gitbook ls-remote</code> 列出NPM上的可用版本

> 使用--log=debug和--debug可以获得更详细的错误消息，如下：  
> gitbook build ./ --log=debug --debug  
> gitbook serve ./ --log=debug --debug