# gitbook 配置

gitbook 配置位于根目录 book.json 中，常见配置如下：

- 常见配置
    1. root 配置项目根目录
        ```
        ├── book.json
        └── docs/
            ├── README.md
            └── SUMMARY.md
        ```
        配置为：
        ```json
        {
            "root": "./docs"
        }
        ```

    1. title 设置书本的标题
        ```json
        "title" : "Liyy's book"
        ```

    1. author 作者相关信息
        ```json
        "author" : "liyy"
        ```

    1. description 本书的简单描述
        ```json
        "description" : "Good Good Study, Day Day Up!"
        ```

    1. language Gitbook使用的语言, 版本2.6.4中可选的语言如下：
        > en, ar, bn, cs, de, en, es, fa, fi, fr, he, it, ja, ko, no, pl, pt, ro, ru, sv, uk, vi, zh-hans, zh-tw
        
        如果想要配置为简体中文，
        ```json
        "language" : "zh-hans"
        ```

    1. direction 文本阅读顺序
        > 可以是 rtl （从右向左）或 ltr （从左向右），默认值依赖于 language 的值

    1. gitbook 应该使用的GitBook版本，并接受类似于 >=3.0.0 的条件

    1. isbn 国际标准书号 ISBN

    1. structure 指定自述文件，摘要，词汇表等的路径

    1. links 在左侧导航栏添加链接信息
        ```json
        "links" : {
            "sidebar" : {
                "Home" : "https://www.baidu.com"
            }
        }
        ```

    1. styles 自定义页面样式， 默认情况下各generator对应的css文件
        ```json
        "styles": {
            "website": "styles/website.css",
            "ebook": "styles/ebook.css",
            "pdf": "styles/pdf.css",
            "mobi": "styles/mobi.css",
            "epub": "styles/epub.css"
        }
        ```

    1. plugins 插件列表
        ```json
        "plugins": [
            "-search",
            "back-to-top-button",
            "expandable-chapters-small",
            "insert-logo"
        ]
        ```
        插件名称前加'-'符合表示不使用此插件。gitbook 默认自带五个插件
        * highlight： 代码高亮
        * search： 导航栏查询功能（不支持中文）
        * sharing：右上角分享功能
        * font-settings：字体设置（最上方的"A"符号）
        * livereload：为GitBook实时重新加载

    1. pluginsConfig 配置插件的属性
        ```json
        "pluginsConfig": {
            "insert-logo": {
                "url": "images/logo.png",
                "style": "background: none; max-height: 30px; min-height: 30px"
            }
        }
        ```

    1. PDF选项 PDF输出可以使用book.json中的一组选项来定制

|变量|说明|
|:---:|:---:|
|pdf.pageNumbers|将页码添加到每个页面的底部(默认为'true')|
|pdf.fontSize|基本字体大小(默认为12)|
|pdf.fontFamily|基本字体系列(默认为Arial)|
|pdf.paperSize|纸张大小，选项为'a0','a1','a2','a3','a4','a5','a6','b0','b1','b2','b3','b4','b5','b6','legal','letter''(默认为'a4')|
|pdf.margin.top|顶部边距(默认为56)|
|pdf.margin.bottom|底边距(默认为56)|
|pdf.margin.right|右边距(默认为'62')|
|pdf.margin.left|左边距(默认为'62')|