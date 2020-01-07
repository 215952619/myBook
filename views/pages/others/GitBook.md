### 简介

这个工具链 (GitBook) 是一个使用 Git 和 Markdown 来快速构建书籍的工具。它可以把你的书本生成为许多格式：PDF，ePub，mobi，或者成为一个网站。

#### 目录结构
```
├── _book    打包生成文件目录
  ├── gitbook 打包后插件所在目录
  ├── views 书本页面解析后所在目录（名称与解析前保持一致）
    └── content.html    页面解析后的文件（目录结构与解析前保持一致）
  └── index.html  书本首页
├── node_modulds    使用插件所在目录
  └── gitbook-plugin-[pluginname]   使用的插件
├── views   书本所有页面所在目录（名称可自定义）
  └── content.md    具体页面内容
├── book.json   书本详细信息，配置与插件等
├── GLOSSARY.md 词汇/注释术语列表
├── README.md   说明文档
└── SUMMARY.md  书本目录
```