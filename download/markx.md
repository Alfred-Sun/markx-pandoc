#Pandoc Markdown写作规范

##写在前面

本文是远程集体写书的格式规范说明文档。考虑到不少作者，已熟悉Markdown格式，因此，特别撰写一份基于Pandoc Markdown的写作格式规范。

##语法导读

* [Pandoc’s Markdown 語法中文翻譯]

##标题

规范

 * 使用 Markdown 的标题格式 `# 一级标题文字`、`## 二级标题文字` 等来书写标题，毋需人工指定标题序号如 1、1.1 等。
 * 标题层次深度至多为四级。
 * 建议在 `#` 号后面添加一个半角空格。

技巧与帮助

* 可以直接使用Github在线编辑
* [Markdown语法说明]

##提示语

规范

* 本书仅使用`note`, `danger`, `error`, `important`, `tip`, `warning`（注意，危险，错误，重要，提示，警告）六种提示语
* 写法为在引用第一行，写： `**note**` 用来表示此段为提示的文本，再空一行后，开始写提示的正文，如下所示：


	> **note**
	>
	> Marr，一个大牛。

检查了自定义生成的note、tip等的LaTex代码，优雅漂亮，如下：

    \begin{quote}
    \textbf{note}
    
    Marr，一个大牛。
    \end{quote}

##定义

规范

* 使用Term开头，空格，然后写定义。

        Term 1
        
        :   Definition 1
        
        Term 2 with *inline markup*
        
        :   Definition 2
        
                { some code, part of Definition 2 }
        
            Third paragraph of definition 2.

##数学公式

规范

* 统一使用LaTex输出数学公式，参见：[Pandoc数学一节]
* 使用`$`表示行内输出；使用`$$`表示显示模式输出：

示范：

- Inline mode $e=mc^2$
- Display mode: $$\frac{df(x)}{dt}=lim_{x \to 0}{\frac{f(x+h)-f(x)}{h}}$$

技巧与帮助

* LaTex数学公式，参见：[LaTeX/数学公式]

##图片

规范

* 图片在各章下面，分别建立`figures`目录保存图片；并在`figures`目录下面建立`big`目录，用以保存制图的源文件，如ppt、keynote、gephi等；
* 非矢量图片需300dpi及以上，以达到堪用的印刷品质，；
* 引用图片，统一使用 Markdown 的规范：`![图片标题](图片相对地址)`；
* 图片标题是否人工指定序号由写作者决定。如果打算人工指定，需按章定序，如如：`图16-1 社会网络分析结果示意图`；
* 图片地址写法为：`figures/small_world.png`，图片命名由英文、数字和下划线构成，不能包括空格、非英文字符。

##表格

规范

* 如无意外，使用pandoc简单表格；
* 可使用R包`pander`或其他RMarkdown输出表格。
* 表的命名方式，统一为: `表3-1 不同中心性测量指标之间的关系`

技巧与帮助

参考：[Pandoc简单表格]

##脚注

脚注用于表示参考文献之外的内容，如本章部分没涉及到的内容或者有争议的话题。

规范

* 在正文中，写脚注的地方，前后加空格，如：` 我们发现社会网络是由一个强大的（但大部分是无形的）的“秘书”统治 [^7] `
* 脚注统一写在参考文献之前,写完脚注了，才是参考文献。
* 注的开头，统一使用：`注：`的写法。

如：

	[^7]:注：作者此处秘书指的是第一章中“非正式网络的力量”一节介绍的ACME咨询公司的例子中所提到的秘书处。

##版本

规范

* RStudio当前最新版本，`0.97`
* R当前最新版本，`3.0`

##R代码

规范

* 在各章下面，创建`code`目录。然后，使用R包：`ProjectTemplate`创建本章的项目。如果本章都是同一个数据源，则创建为一个项目；如果数据源差异较大，则创建为不同项目。

技巧与帮助

* [ProjectTemplate教程]
* [ProjectTemplate]

##日常Github提交

规范

* 基于`Git Flow`
* 如果不熟悉`Git`与`Git Flow`，建议直接在线编辑、在线提交。

技巧与帮助

* [Git flow 备忘清单]
* [Git flow 開發流程]
* [Git-flow 使用笔记]

备注：如果是Windows下的朋友，也可以直接使用本在线编辑器，通过`signinToGithub`，登陆Github后，找到你的相应章节，提交即可。



##参考文献

规范

* 统一使用APA第6版格式输出引文与文末参考文献；
* 将每一章的参考文献保存在一个`bibtex`文件中；
* 推荐使用参考文献软件为`Zotero`或`Endnote`。
* Pandoc默认支持参考文献，请使用``参考文献``作为末尾标题。
* 参考文献写法是：`[@yangzhiping2001]`或者`[@__2003]`，@符号后面直接写bib文件的引用文献的唯一编号，如yangzhiping2001或者__2003 

示例：

bib文件的内容是：

	@article{yangzhiping2003,
		title = {试评卡尼曼经济心理学研究及其影响 [J]},
		volume = {26},
		number = {4},
		urldate = {2013-05-27},
		journal = {心理科学},
		author = {阳志平},
		year = {2003},
		pages = {724–726}
	}


引用键是：`yangzhiping2003`，那么，引用格式直接这么写：

	阳志平在`[@yangzhiping2001]` 、`[@yangzhiping2002]`、`[@yangzhiping200]`中写道。。。


技巧与帮助

在[EndNote]中，一个较好的习惯是，写完论文之后，借助于它的`Export Traveling Library`功能，将每篇论文的参考文献导出为一个新的Endnote文献管理库，如下图所示：

![image](http://www.yangzhiping.com/images/psy/endnote.png)

## 参考文献

请加载附件中的`ouyang.bib`文件，即会出来本文引用的参考文献。点击`Citations`=> `Load a Bibliography file`


##其它有用链接

请参考：

* [Customizing Markdown Rendering]
* [RStuido Markdown]
* [StackOverFlow pandoc节点]
* [Try Pandoc]

[Pandoc’s Markdown 語法中文翻譯]:http://pages.tzengyuxio.me/pandoc/
[Markdown语法说明]:http://markdown.tw/
[ProjectTemplate教程]:http://projecttemplate.net/getting_started.html
[ProjectTemplate]:http://www.johnmyleswhite.com/notebook/2010/08/26/projecttemplate/
[EndNote]:http://www.endnote.com/
[Customizing Markdown Rendering]:http://www.rstudio.com/ide/docs/authoring/markdown_custom_rendering
[RStuido Markdown]:http://www.rstudio.com/ide/docs/authoring/using_markdown_equations
[StackOverFlow pandoc节点]:http://stackoverflow.com/tags/pandoc/hot
[Try Pandoc]:http://johnmacfarlane.net/pandoc/try/
[Git flow 备忘清单]:http://danielkummer.github.io/git-flow-cheatsheet/index.zh_CN.html
[Git flow 開發流程]:http://ihower.tw/blog/archives/5140
[Git-flow 使用笔记]:http://fann.im/blog/2012/03/12/git-flow-notes/
[ProjectTemplate教程]:http://projecttemplate.net/getting_started.html
[ProjectTemplate]:http://www.johnmyleswhite.com/notebook/2010/08/26/projecttemplate/
[Pandoc简单表格]:http://pages.tzengyuxio.me/pandoc/#簡單表格
[LaTeX/数学公式]:http://zh.wikibooks.org/zh-cn/LaTeX/%E6%95%B0%E5%AD%A6%E5%85%AC%E5%BC%8F
[Pandoc数学一节]:http://pages.tzengyuxio.me/pandoc/#數學

	