# 每周总结可以写在这里
学习使我快乐


1.重学 | 学习方法
```js
领域知识                                    事件中学习

前端知识                                    建立知识体系（重学前端/前端训练营）

编程能力  架构能力  工程能力                   刻意练习（前端训练营），重点是这3个能力

编程能力：找题刷
架构能力：读源代码，看他人项目，如 vue3.0
工程能力：选择工作，在公司中争取


红黑树，前端用不到


不教追新追热点的技术，不教vue3.0，看文档会更好
不教包装简历应付面试的技巧
不教找捷径图省事的本领

    前端技术不是武林秘籍
    真正的能力是练出来的



学习方法--整理法
顺序关系，组合关系，维度关系，分类关系

        词法分析，语法分成一个个有意思的词
        语法分析，把一个一个词法分析产出的词编程抽象语法树 AST，先有语法树、再有抽象语法树。
编译    代码优化，基于AST的优化
        代码生成



组合关系

            选择器

CSS规则     属性

            值



维度关系
    从不同角度看（横看成岭侧成峰），从文法角度需要掌握词法和语法，词法和语法对于维度来说也是维度关系，写的Js也都是一个词，也都在语法结构里面
    文法都掌握了，是不是就知道js了，还需要知道语义

    运行时，另一个角度看js

                        词法
                文法    
                        语法

JavaScript      语义

                        类型
                运行时
                        执行过程



分类关系

                id选择器
                class选择器
                通用选择器
                属性选择器
CSS简单选择器      
                元素选择器
                伪类选择器
                伪元素选择器



整理法的案例教学

HTML中的标签

前端权威
w3.org
w3.org/TR

mdn
developer.mozilla.org

比较有约束性的地方，网站更好点，更纯粹点
whatwg.org
```

整理知识的时候，3个网站冲突如何办

|源头|标准和文档|大师|
|--|--|--|
|最早出现的论文，|w3.org|Tim Berners-Lee|
|杂志最初的实现案例|developer.mozilla.org|Brendan Eich|
||msdn.microsoft.com|Bjame Stroustrup|
||developer.apple.com||
||||



```js

closure(computer programming)

History and etymology

靠谱搜索
scholar.google.com
查找历史论文，会比较累，原始概念与新概念也会有变化


面向对象
    追溯法写篇文章


前端进阶之路
    番外：面试官怎么想

好的面试题三要素

    区分度：某个算法题（大草原算法题，所有人都不会，1+100加法都会的也不行），中等好、比较好、特别好
    覆盖面：最好的题（一问题就全覆盖掉了，弄一本前端的书的目录是什么，难度略高）
    深度：从哪个难度到哪个难度


    打断：
        意味着不感兴趣
        打断是一种提示
        不问问问题，直接到最后，面试失败
        直接打断，告诉面试失败

    争论：
        争论与压力面试
        争论的技巧

    难题：
        展现分析过程
        缩小规模


    题目类型
        项目类型
        知识性问题
        开放性问题
            设计一个机制
        案例性问题
        有趣性问题




    问题：整理法的实践中是否包含对知识对追溯，追溯的过程和结果是否也是整理的过程
    回答：
        整理、追溯建立知识体系的两个方法，两者结合起来用的

```


2.重学 | 构建知识体系
```js
前端技术
    HTML（将语言的同时将了实现，很奇怪）维度关系
        HTML as 计算机语言
            语法
            词法
        HTML as SGML
            DTD
            Entity
        HTML as XML（它与DTD从两个方面不同形式定义了文档）
            Namespace
                svg
                mathml
                Subtopic 3
                aria（被忽略的，在国外会被告）
            Tag（mdn是不错的选择，也可以从标准 ECMA-262 中选择）

    JavaScript
        Grammar
            Lex(词法)
                WhiteSpace
                LineTerminator
                Comment
                Token
                    Identifier
                    Keywords
                    Punctuator
                    NumericLiteral
                    StringLiteral
                    RegularExpressionLiteral
                    Template

            Syntax(语法)
                Atom(原子)
                Expression
                Structure
                    function 和 process 分开，偏 C 系都没有 process
                Script & Module
        语义（Semantics）
            在 ECMA-262 中语义伴随这语法一起解释
        运行时（Runtime）
            Type
                Number
                String
                Boolean
                Null
                Undefined
                Object
                Symbol
                内部类型
                    Referece
                    Completion Record
            
            执行过程
        
        
    CSS
        语法/词法
        @规则
        普通规则
            选择器
                简单选择器
                    .cls
                    #id
                    tagname
                    *
                    [attr=v]
                复合选择器
                复杂选择器
                选择器列表
            Property
            Value
        机制
            排版
            伪元素
            动画
    API
        Browser
            DOM（语法与HTML 一一对应的）
                Nodes
                Ranges
                Events
            BOM
            
        Node
        Electron
        小程序



语法：怎么写，一定有一定的写法
    单引号属性括起来的值，还想用单引号怎么办

nbsp; 定义，xhtml-symbol.ent
entity 补全

知道哪里去寻找，比寻找知识本身更重要

标签筛选
    $0 代表当前元素
    $0.querySelectorAll('code')  所有元素
    Array.prototype.map.call($0.querySelectorAll('code'), e => e.innerText).join('\n')
```


3.重学 | 工程体系
```js

领域知识，形成知识体系

    
------------------------------------------------------------


主观评价：
    不要写学习能力强等，
    多写客观存在的一些东西，成就

业务目标：
    ***公司业务的核心目标是什么，KPI是什么
    理解公司业务的核心目标
    目标转化为指标
        

        
技术方案：
    业务指标到技术指标的转化
    形成纸面方案、完成小规模试验
实施方案：
    确定实施目标、参与人
    管理实施进度
结果评估：
    数据采集、数据报表
    向上级汇报


1.业务型成就
案例--应用手势
    业务目标&指标：点击率
        技术方法：给 tab 组件增加手势操作
            原本首页有一个 tab，原来需要点击 tab 切换菜单，改成手势切换（左右一划）
        实施1：在业务中加入对应功能，并上线
        结果：点击率提升3倍
        实施2：编写通用 tab 组件，向所有导购业务推广，形成制度
        结果+：推广到所有导购业务，符合预期

2.技术性成就
目标：公认的技术难度
方案与实施：依靠扎实的编程能力、架构能力形成解决方案
结果：问题解决

案例--爬取商品价格（易淘项目，比价插件）
    背景：在某浏览器插件项目中，需要爬取各个网站价格比价，但是各个网站会采用图片价格等手段防御
    方案：引入 JS 端的数字识别技术，靠 AI 技术解决
    实施：直接上线
    结果：成功采集到信息

3.工程型成就
目标：
    质量
    效率
方案与实施：
    规章制度
    库
    工具
    系统
结果：
    线上监控

案例--XSS攻击的预防
目标&指标：XSS攻击白帽子反馈漏洞
技术方案：整理安全手册，review 历史代码，代码扫描工具
实施：对全体前端宣讲，整体 review 代码，更改代码发布流程
结果：XSS 漏洞大幅减少


数据驱动的思考方式：一个小故事


init run  publish 总是要保证的


init：项目的基本文件和架构都有了
run：隐藏了 build 的过程，要能跑起来
test：单元测试
publish：发布


工具链的作用
工具的分类
    脚手架
    本地调试
    单元测试
    发布
工具链体系的设计
    版本问题
    数据统计


平时大家各自集成自己的软件
每天集成一次
客户端软件持续集成
Daily build
    每天产生一个产品的版本
BVT
    检查今天的版本是否够好


Daily build  ↓
Check-in build
Lint + Rule Check
    设定规则进行检查，无头浏览器（不渲染，只生成DOM树等）
    单张图片不能大约50kb，整包不能大于200kb
    50%压缩+锐化
    4k  给 4倍图
    高清 给 2倍图
    2d网络，50%压缩图片，大约原来的1/4


前端的编译比较快
发布以周记、

如果图比较大的时候，可以压一下


技术架构
    客户端架构：
        解决软件需求规模带来的复杂性
    服务端架构：
        解决大量用户访问带来的复杂性
    前端架构：
        

```






HTML 标签元素
```js

4 The elements of HTML

4.1 Document element
    html

4.2 Document metadata
    head
    title
    base
    link
    media
    type
    meta
    style

4.3 Sections
    body
    article
    section
    nav
    aside
    h1
    h2
    h3
    h4
    h5
    h6
    hgroup
    header
    footer
    address

4.4 Grouping content
    p
    hr
    pre
    blockquote
    ol
    ul
    menu
    li
    dl
    dt
    dd
    figure
    figcaption
    main
    div

 4.5 Text-level semantics   
    a
    em
    strong
    small
    s
    cite
    q
    dfn
    abbr
    ruby
    rt
    rp
    data
    time
    code
    var
    samp
    kbd
    sub
    sup
    i
    b
    u
    mark
    bdi
    bdo
    span
    br
    wbr

4.6 Links
    a
    area

4.7 Edits
    ins
    del

4.8 Embedded content
    picture
    source
    img
    iframe
    embed
    object
    param
    video
    audio
    track
    map

4.9 Tabular data
    table
    caption
    colgroup
    col
    tbody
    thead
    tfoot
    tr
    td
    th

4.10 Forms
    form
    label
    input
    button
    select
    datalist
    optgroup
    option
    textarea
    output
    progress
    meter
    fieldset
    legend
   

4.11 Interactive elements
    details
    summary
    dialog

4.12 Scripting
    script
    noscript
    template
    slot
    canvas
```



Lex
```js
避开 javascript 的特殊，只有4类输入
    WhiteSpace
        "var\uFEFFa = 1"    --> "vara = 1"       vara 报错，a-->1
    LineTerminator(换行符)
    Comment
    Token()
        Identifier
        Keywords
        Punctuator
        NumericLiteral
        StringLiteral
        RegularExpressionLiteral
        Template

```

Synax
```js
计算机去解释、理解的方式，产生式
if(a<100)
    b += a++

IfStatement
    Expression
    Statement




语法结构
    从小到大的过程
    Expressions 从小的词法结构去合成表达式的这样的结构
    Statements 再往上合成语句这样的结构
    再往上 fuction and class
    再往上 scripts and modules
```

Runtime
```js

执行过程
    8.6 RunJobs() 是一切的开始
        调用初始化的 Realm，把内置对象创建好
    Required Job Queue
    将代码一段一段的交给 Job Queue，因此会有一些 EnqueueJob 等


javascript 执行的边界在下面，最大大不过 Job，最小小不过 Identifier
job
    Script/Module
        Promise
            Function
                Statemnent
                    Expression
                        Literal
                            Identifier

```


css
```css
w3c 标准状态
Candidate Recommendation            候选状态
Group Note
Proposed Edited Recommendation
Proposed Recommendation             委员会通过，建议大家提出建议和批评
Recommendation                      正是的推荐标准
Retired
Working Draft                       最初状态，不要相信


css2.1 比较完整
css3 语法散列在各处，不容易查找

```

Browser
```
Browser Object Model(BOM) 追溯法
wiki 中 navigator 现在不属于 BOM


```



