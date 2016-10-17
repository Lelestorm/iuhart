# Markdown 语法说明
> [语法说明-简体中文版](http://wowubuntu.com/markdown/#list)

### 兼容HTML

> Markdown格式的语法只涵盖纯文本可以涵盖的范围。不在Markdown涵盖范围之内的标签都可以直接在文档里面用HTML撰写，不需要额外标注这是HTML或是Markdown。  
> 要制约的只有一些HTML区块元素——比如`<div>`、`<table>`、`<pre>`、`<p>`等标签。
> 
> 注: 在HTML区块标签内的Markdown格式语法不会被处理；但是在Markdown格式内可以随意使用HTML标签
> 
### 语法高亮
> 
> ```html   
>   
>  代码块   
> ```

```php
function test(){
    return 'This is php code';    
}
```

### 快捷键
> 输入 mdl + Tab 插入链接标记 `[](link)`  
> 输入 mdi + Tab 插入图片标记 `![Alt text](/path/to/img.jpg "Optional title")`
### 特殊字符自动转换
> 版权符号：&copy; `&copy;`
> 
### 区块元素
> ##### 换行
> >在插入处连续输入两个空格，然后回车。  
> ##### 标题
> > Markdown支持两种标题语法，类Select和类Atx形式。  
> > 1. 类Selext形式：用底线形式；利用=（最高标题形式）和-（第二阶标题形式）。任何数量的=和-都可以有效果。  
> > 2. 类Atx形式：在行首插入1~6个#，对应标题1~6阶(H1-H6)。
> ##### 区块引用 Blockquotes
> > 1. 区块引用在行首加上" > "。  
> > 2. 区块引用可以嵌套（引用套引用）。
> > 3. 引用区块内可以使用其他的Markdown语法，包括标题、列表、代码区块等。 
> ##### 列表  
> > * 无序列表：`* + -`
> > * 有序列表：数字接上一个英文句号 `1.`   
> > * 首行出现非序列(例：`2016\. `是非序列的实际意义上的字符)可以使用反斜杠(\\)转义  
> ##### 分割线
> > 使用3个以上的 `*` 或 `-` 或 `_` 建立一个分割线，行内不可有其他除空格外的其他字符  
> > 
> > 星号：`*** or * * *`
> > * * *  
> > 减号：`--- or - - - `  （注：-在一行代码下面会解析为Selext二阶标题）
> > 
> > ---
> > 底线：`___ or _ _ _`  
> > ___ _ _ 
> > 
> ##### 链接
> > Markdown支持两种链接语法：行内式，参考式；自动链接 
> > 
> > ###### 行内式：`[text](link title)` 其中 title 可以省略。
> > > `[an example](http://www.github.com/Lelestorm "title")`   
> > > `<p><a href="http://www.github.com/Lelestorm" title="title">an example</a>`
> > 
> > ###### 参考式：`[text] [id]` id为辨识链接的标记。   
> > > `This is [an example][id] reference-style link.`   
> > > 也可以选择性的在两个中括号中间加上一个空格   
> > > `This is [an example] [id] reference-style link.`   
> > 
> > > 接着，在文件的任意处，你可以把这个标记的链接内容定义出来：  
> > > `[id]: http://www.github.com/Lelestorm`   
> > 
> > > 隐式链接标记：可省略指定链接标记   
> > > `[Google][] 相当于 [Google][Google]`
> > 
> > > 链接内容定义形式：   
> > > > * \[](方括号，前面可以选择性地加上至多3个空格来缩进；里面输入链接文字)  
> > > > * : 接着一个冒号
> > > > * 接着一个以上的空格或制表符
> > > > * 接着链接的网址；可以用尖括号(<>)包起来   
> > > > * 选择性地接着title内容，可以使用单引号、双引号或小括号；可以放到下一行或加一些缩进；这样网址太长方便查看。
> >
> > > 以下三种定义都是相同的：   
> > > `[foo]: http://github.com/Lelestorm/ "lele github home  page"`   
> > > `[foo]: http://github.com/Lelestorm/ 'lele github home  page'`   
> > > `[foo]: http://github.com/Lelestorm/ (lele github home  page)`  
> > > 
> > ###### 自动链接
> > > Markdown支持简短的自动链接形式；只要把链接地址用尖括号括起来，Markdown就会自动转成链接形式。   
> > > `<http://github.com>  转成 <a herf="http://github.com">http://github.com</a>`   
> > > 
> > > 邮件地址的自动链接；Markdown会先把字符转换成16进制的HTML实体，防止邮址收集机器人。
> 
> ##### 强调
> > Markdown使用星号(*)和底线(_)作为强调词的符号，被 * 或 _ 包围的字词会被转成`<em>`；用两个 * 或 _ 包括，则会转成`<strong>`    
> > 注：如果 * 和 _ 两边都空白字符，则会被当作普通字符；插入普通 * 或 _ 使用反斜杠(\\)转义  
> > > *This is `* or _`*   
> > > __ This is `** or __`__
> 
> ##### 代码 Code
> 
> >  标记一小段行内代码，使用反引号(`)包括起来。   
> >  如果代码区段内有插入反引号，你可以用多个反引号来开启和结束代码区段。   
> >  在代码区段内， &和括号都会被自动转化为HTML实体。
> >
> ##### 图片
> > Markdown同样支持两种图片标记语法：行内式，参考式  
> > Markdown暂时还不能指定图片的宽高，如需要请使用普通`<img>`标签 
> > ###### 行内式   
> > `![alt text](image file path)`   
> > ###### 参考式
> > `![alt text] [id]`   
> > `[id]: /images/pic.png "title attr"`
> > 
> 
> ##### 反斜杠 \
> > Markdown支持以下这些符号前面加上反斜杠转化为普通符号。   
> > \   反斜杠   
> > `   反引号   
> > \*   星号   
> > _   底线   
> > {}  花括号   
> > []  方括号   
> > ()  括号   
> > \#  井号   
> > \+   加号   
> > \-   减号   
> > .   英文句号   
> > !   感叹号   
> >   