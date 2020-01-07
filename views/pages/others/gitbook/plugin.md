# gitbook 插件

插件安装三种方式：
* 在 book.json 的 'plugins' 字段中添加 插件名字，然后执行 gitbook install
* 在 book.json 的 'plugins' 字段中添加 插件名字，然后执行 npm install gitbook-plugin-[插件名]
* 在 book.json 的 'plugins' 字段中添加 插件名字，然后下载插件源码解压到根目录下 node_modules 文件夹

    > 专用插件可以托管在 GitHub 上,并使用 git urls:
    ```json
    {
        "plugins": [
            "pre@git+https://github.com/215952619.git#2.0.0"
        ]
    }
    ```


# gitbook 常用插件推荐

1. **back-to-top-button**   回到顶部

1. **chapter-fold** 导航目录折叠,支持多层目录，点击导航栏的标题名就可以实现折叠扩展。

1. **code** 代码添加行号&复制按钮
    ```json
    "pluginsConfig": {
        "code": {
            "copyButtons": false // 可关闭复制按钮
        }
    }
    ```

1. **insert-logo**  将logo插入到导航栏上方中
    ```json
    "pluginsConfig": {
        "insert-logo": {
            "url": "images/logo.png",
            "style": "background: none; max-height: 30px; min-height: 30px"
        }
    }
    ```

1. **search-pro**   高级搜索，支持中文，需要将默认的`search`和`lunr`插件去掉

1. **advanced-emoji** 支持emoji表情

    emoji可选列表参考
    [https://www.webfx.com/tools/emoji-cheat-sheet/](https://www.webfx.com/tools/emoji-cheat-sheet/)

1. **github**   在右上角添加github图标
    ```json
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/zhangjikai"
        }
    }
    ```

1. **emphasize**    为文字加上底色

    使用示例：

    ```
    This text is {% pre _tag="em" %}highlighted{% endpre %} !
    This text is {% pre _tag="em" %}highlighted with **markdown**{% endpre %} !
    This text is {% pre _tag="em",type="green" %}highlighted in green{% endpre %} !
    This text is {% pre _tag="em",type="red" %}highlighted in red{% endpre %} !
    This text is {% pre _tag="em",color="#ff0000" %}highlighted with a custom color{% endpre %} !
    ```

    ```
    {% raw %}This text is {% em %}highlighted{% endem %} !
    This text is {% em %}highlighted with **markdown**{% endem %} !
    This text is {% em type="green" %}highlighted in green{% endem %} !
    This text is {% em type="red" %}highlighted in red{% endem %} !
    This text is {% em color="#ff0000" %}highlighted with a custom color{% endem %} !
    {% endraw %}
    ```

    效果如下：  
    This text is {% em %}highlighted{% endem %} !

    This text is {% em %}highlighted with **markdown**{% endem %} !

    This text is {% em type="green" %}highlighted in green{% endem %} !

    This text is {% em type="red" %}highlighted in red{% endem %} !

    This text is {% em color="#ff0000" %}highlighted with a custom color{% endem %} !

1. **splitter** 侧边栏宽度可调节

1. **sharing-plus** 分享当前页面，比默认的 sharing 插件多了一些分享方式，需要去掉原始 sharing 插件

    当前版本（0.0.2）所有支持的分享方式：
    > douban,facebook,google,hatenaBookmark,instapaper,line,linkedin,messenger,pocket,qq,qzone,stumbleupon,twitter,viber,vk,weibo,whatsapp

    配置示例如下：

    ```json
    {
        "plugins": ["-sharing", "sharing-plus"],
        "pluginsConfig": {
            "sharing": {
                "qq": true,
                "qzone": true,
                "weibo": true,
                "all": [
                    "douban", "weibo", "qq", "qzone", "whatsapp"
                ]
            }
        }
    }
    ```

    > 所有方式默认为 false，在 pluginsConfig-sharing下改为 true 后会在 gitbook 工具栏增加该项的分享按钮。
    
    > 其中，值为 all 的项为特殊项，这一项的所有值会出现在分享按钮 hover 事件触发的下拉框中。

1. **tbfed-pagefooter** 页面添加页脚

    ```josn
    {
        "plugins": [
        "tbfed-pagefooter"
        ],
        "pluginsConfig": {
            "tbfed-pagefooter": {
                "copyright":"Copyright &copy xxxx.com 2017",
                "modify_label": "该文件修订时间：",
                "modify_format": "YYYY-MM-DD HH:mm:ss"
            }
        }
    }
    ```

1. **klipse**   使用指定的代码格式，可嵌入类似IDE的功能，代码块可编辑，可实时显示结果

    当前版本支持的语言有：

    > eval-clojure,eval-js,eval-python,eval-php,eval-scheme,eval-ruby,reagent,google-chart,eval-es2017,eval-jsx,transpile-jsx,render-jsx,react,render-markdown,render-lambdaway,eval-cpp,render-html,eval-sql,eval-brainfuck,transpile-cljs

    实例：

    >{% raw %}\```eval-js  
    (()=>{return 123})()  
    \```{% endraw %}

    效果如下：
    ```eval-js
    (()=>{return 123})()
    ```

    实例：
    ```
    {% raw %}{% klipse "eval-js", loopMsec="1000" %}
    new Date()
    {% endklipse %}{% endraw %}
    ```

    效果如下：

    {% klipse "eval-js", loopMsec="1000" %}
    new Date()
    {% endklipse %}

1. **donate** 打赏插件

1. **change_girls** 可自动切换的背景

1. **pageview-count** 阅读量计数

1. **click-reveal** 点击显示

    使用示例：
    ```
    {% raw %}{% reveal text="点击显示" %}
    要被隐藏的内容
    {% endreveal %}{% endraw %}
    ```
    效果如下：
    {% reveal text="点击显示" %}
    要被隐藏的内容
    {% endreveal %}

1. **custom-favicon** 修改浏览器标题栏图标
    > 需要在`pluginsConfig`中指定`favicon`字段，只能使用`.ico`文件

1. **hide-element** 隐藏元素
    > 需要在`pluginsConfig`中指定`elements`,即需要隐藏的元素数组

1. **accordion** 折叠模块
    实例：

    ```md
    # 模板遍历以`<p>%accordion%`开头，注意不能有空格
    %accordion%Some title here%accordion%
    # 此处需要遍历`%accordion%</p>`，注意换行
    Any content here
    # 插件需要遍历`<p>%/accordion%</p>`，所以需要换行
    %/accordion%
    ```
    效果如下：
    <p>%accordion%Some title here%accordion%</p>
    <p>Any content here</p>
    <p>%/accordion%</p>