### 发布自己npm包
> 转自: [如何发布自己的NPM包(模块)](https://juejin.im/post/5b95c2ed6fb9a05cd67699d1)

1. 注册NPM 账号  
    注册地址：[www.npmjs.com/](www.npmjs.com/)

1. 初始化自己要发布的项目  
    搭建本地环境：安装node.js，包含了npm命令。  
    新建目录，在该目录下，初始化项目：npm init。  
    按照提示填写初始化信息，我的模块名称为：finitxu-npm-test，初始版本号：v1.0.0。  
    模块名称需遵循相关政策要求：www.npmjs.com/policies ，不能够与已有NPM模块名冲突等等。

1. 登录npm，发布自己的npm包  
    > npm login // 根据提示输入之前注册的账号、密码以及邮箱

1. 发布npm包
    > npm publish // 发布成功后可以在自己的npm主页可以看到该包

1. 更新NPM包（模块）及 readme文件
    > npm version patch  
    > npm publish  

    npm version后面参数说明：  
    * patch：小变动，比如修复bug等，版本号变动 v1.0.0->v1.0.1
    * minor：增加新功能，不影响现有功能,版本号变动 v1.0.0->v1.1.0
    * major：破坏模块对向后的兼容性，版本号变动 v1.0.0->v2.0.0

    > tips: 相同的包相同的版本号无法重复发布

1. 使用更新后的NPM包
    * 针对patch：  
        > npm install finitxu-npm-test
    * 针对minor：  
        > npm install finitxu-npm-test
    * 针对major：  
        > npm install finitxu-npm-test@2.0.0