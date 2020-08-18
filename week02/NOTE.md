# 每周总结可以写在这里

1. 编程语言通识

```js
50年代计算机发展黄金期

非形式语言
    中文，英文

形式语言（乔姆斯基谱系）
    0型 无限制文法
    1型 上下文相关文法
        一个词放在不同的上下文含义不同
        对引擎的实现者来说特别不友好
    2型 上下文无关文法
        一个词放在不同上下文都是一个意思
        大部分计算机语言都㐊主体上，上下文无关文法
        JavaScript 不是上下文无关文法（但是比较节制的，在小的点上违反上下文无关，99%都是上下文无关）
    3型 正则文法
        能用正则表达式解释的文法
        对表达能力限制非常强


现代语言采取比较折中的办法
    把所有的文法分成词法、语法两个部分
    词法：使用正则做一遍粗处理，把语言做成单个的词，再把这些词作为输入流，去做语法分析
    语法：

```

产生式（BNF）
```js
1.用尖括号括起来的名称来表示语法结构名
2.语法结构分成基础结构和需要用其他语法结构定义的复杂结构
    1.基础结构成终结符
    2.复合结构成非终结符
3.引号和中间的字符表示终结符
4.可以有括号
5.*表示重复多次
6.|表示或
7.+表示至少一次


一门语言只有 a b 两种字符组成

"a"

"b"

<Program> = "a"+ | "b"+
<Program> = <Program> "a"+ |<Program> "b"+
--------------------------------------------------------------------------------
定义数字、数字加法表达式

<Number> = "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"

<DecimalNumber> = "0" | (("1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9") <Number>* )

<Expression> = <DecimalNumber> | <Expression> "+" <DecimalNumber>

--------------------------------------------------------------------------------
四则运算
    加法、乘法
        <AdditiveExpression> = <DecimalNumber> | <AdditiveExpression> "+" <DecimalNumber>

        <MultiplicativeExpression> = <DecimalNumber> | <MultiplicativeExpression> "*" <DecimalNumber>

        1.涉及算数运算优先级，将定义进行改写并改变定义顺序
            <MultiplicativeExpression> = <DecimalNumber> | <MultiplicativeExpression> "*" <DecimalNumber>

            <AdditiveExpression> = <MultiplicativeExpression> | <AdditiveExpression> "+" <MultiplicativeExpression>

        2.补全 + - * /
            <MultiplicativeExpression> = <DecimalNumber> | 
                <MultiplicativeExpression> "*" <DecimalNumber> |
                <MultiplicativeExpression> "/" <DecimalNumber>

            <AdditiveExpression> = <MultiplicativeExpression> | 
                <AdditiveExpression> "+" <MultiplicativeExpression> |
                <AdditiveExpression> "-" <MultiplicativeExpression>
        
        3.逻辑运算，逻辑表达式递归，操作主体加法表达式（由加法表达式递归，操作主体是乘法表达式）
            <logicalExpression> = <AdditiveExpression> | 
                <logicalExpression> "||" <AdditiveExpression> |
                <logicalExpression> "&&" <AdditiveExpression>

        4.带括号的四则运算，定义括号表达式，再更改基础操作对象“乘法表达式”，优先级越高（越会成为其他表达式的基础，十进制数字表达式是整个算数运算的基础）
            <PrimaryExpression> = <DecimalNumber> |
                "(" <PrimaryExpression> ")"

            <MultiplicativeExpression> = <PrimaryExpression> | 
                    <MultiplicativeExpression> "*" <PrimaryExpression> |
                    <MultiplicativeExpression> "/" <PrimaryExpression>

            <AdditiveExpression> = <MultiplicativeExpression> | 
                <AdditiveExpression> "+" <MultiplicativeExpression> |
                <AdditiveExpression> "-" <MultiplicativeExpression>

        
--------------------------------------------------------------------------------
无限制文法，一次可产生多个
<a> <b> ::= "c"

--------------------------------------------------------------------------------
限制型文法，只能变化 x 
"a" <b> "c" ::= "a" "x" "c"

--------------------------------------------------------------------------------
上下文相关文法
"```四则运算" <LogicalExpression> "```" = "```四则运算"
    (<AdditiveExpression> = <MultiplicativeExpression> | 
    <AdditiveExpression> "+" <MultiplicativeExpression> |
    <AdditiveExpression> "-" <MultiplicativeExpression>)
    "```"

--------------------------------------------------------------------------------
上下文无关文法，无论在哪都产生这个A
<A> ::= ? 

--------------------------------------------------------------------------------
正则文法，只允许左递归
<A> ::= <A>?
<A> ::= ?<A>  错误的

--------------------------------------------------------------------------------
思考题，用正则表达式写一下四则运算
<DecimalNumber> = /0|[1-9][0-9]*/





第一遍用正则表达式进行的扫描叫做词法分析，根据产生式去建立抽象语法树的过程（一开始建立语法树，再进行剪枝操作变成抽象语法树）

1 型
    {
        get a {return 1},
        get: 1
    }


2型
    JavaScript 绝大多数是 2 型语言


3型
    1 ** 2，如果没有 **，JavaScript 可以用这则表示
    JavaScript 正则不是回溯，甚至不是线性，可能是平方



```

JavaScript 语法
```js
AGrammar Summary ~ A.5Scripts and Modules   JavaScript所有语法
    JavaScript 所有终结符都是加粗黑体字
    词法定义都是双冒号，语法定义都是单冒号

    JavaScript 做了很多工程化的妥协

通过实战进行学习总会有漏掉的，因此还是要从理论上学习

```

现代语言的特例
```js
1.C++ 中，*可能表示称号或者指针，具体是哪个，取决于星号前面的标识符是否被声明为类型
    C++，语法和语义关联了，C++ 非形式化语言

2.VB中，< 可能是小于号，也可能是XML直接量的开始，取决于当前位置是否可以接受 XML 直接量

3.Python中，行首的 tab 符和空格会根据上一行的行首空白以一定规则被处理成虚拟终结符 indent 或者 dedent
    词法分析阶段就会处理掉，强制缩进也会对语言产生影响

4.JavaScript中，/ 可能是除号，也可能是正则表达式开头，处理方式类似于VB，字符串模板中也需要特殊处理 }，还有自动插入分号规则

```

练习：尽可能寻找你知道的计算机语言，尝试把他们分类

图灵完备性
```js
图灵完备性
    1.命令式-图灵机（凡是可计算的都能计算出来），世界是不是都可计算的呢，图灵无法计算另一个台计算机是否停机，从数学上证明了世界上的一切不都是能够用计算机解决的
        goto
            可去任何地方，是图灵完备的
        if 和 while
            有分支和循环，也是图灵完备的
    2.声明式-lambda
        递归

源编程：生成代码
编程：自己写代码

--------------------------------------------------------------------------------
动态与静态
    动态
        1.在用户的设备/在线服务器上
        2.产品实际运行时
        3.Runtime
    静态：
        1.在程序员的设备上
        2.产品开发时
        3.Compiletime

--------------------------------------------------------------------------------
类型系统
    1.动态类型系统与静态类型系统
        {
            a:T1
            b:T2
        }
    2.强类型与弱类型
        String + Number         转换成String
        String == Boolean       Boolean 转换为 Number
        弱类型开发起来更爽，纠错更难
        (T1, T2) => T3
        有隐式转换语言的都是弱类型
    3.复合类型
        1.结构体
            对象就是结构体
        2.函数签名
            函数的参数与返回值构成函数签名。
        凡是能用 Array<Parent> 的地方，都能用 Array<Child>
    4.子类型
        逆变/斜变

        凡是能用 Fuction<child> 的地方，都能用 Function<Parent>
            Function<child> 自然而然能用 Function<Parent> 的方法，这就是斜变
            Function<Parent> 自然而然能用 Function<Child> 的方法，这就是逆变

--------------------------------------------------------------------------------
一般命令式编程语言
    Atom 原子，+ - * /这种符号、变量名、直接量、
        Identifier
        Literal
    Expression 原子经过操作符或者() 构成了表达式
        Atom
        Operator
        Punctuator
    Statement 表达式 + if 等变成语句
        Expression
        Keyword
        Punctuator
    Structure 产生域等
        Function
        Class
        Process
        Namespace
        ......
    Program
        Program
        Module
        Package
        Library

语法 语义  运行时
--------------------------------------------------------------------------------
```


2. 重学 JavaScript | 词法，类型
```js

209 page
    any Unicode code unit
    字符都对应着码点，a 的码点 97，A 65
    unicode


Atom

Expression
    
Statement
    
Structure
    
Program
        


```

Unicode
```js
<script>
for(let i = 0; i< 120; i++) {
    // console.log(String.fromCharCode(i));
    document.write("<sapn style='background-color:lightgreen;'>" + String.fromCharCode(i) + "</span><br />");
}
</script>

将汉字转换成 16 进制
"厉害".codePointAt(0).toString(16)
"5389"
"厉害".codePointAt(1).toString(16)
"5bb3"

var 厉害 = 1; <==> var \u5389\u5bb3 = 1;



ImputElement
    WhiteSpace
        tab 
            制表符，手写列表中间的间隙很好用，有 size 限制
        VT  
            纵向制表符，字符串表示"\v" 。大多数排版系统都不会给它特殊待遇
            U+000B  11
        FF  
            FORM FEED
            U+000C  
        SP  普通空格
            U+0020  32
        &nbsp;
            NO-BREAK SPACE
            U+00A0  160
            通常页面的字符，如果超出页面行宽，会以整个单词换行，而使用 &nbsp; 连接两个单词，换行的时候一起换行或一起不换行
        ZWNBSP 
            Zero Width No-Break Space
            U+FEFF
            不知道文件是什么编码格式，大头小头什么的
            0 宽空格，根据0宽空格的顺序反猜整个文件的编码格式
                如果第一个字符传来是 FF 就是尾巴在前
                如果收到 FFE 后面的字符就是前两个在前后两个在后
                如果收到 FEFF 是大的在前小的在后
            别名，BOM   bit Order Mask
            淘宝规范，js的HTML代码一定要在前面加一个回车

            推荐使用 <SP>，其他的都用 unicode 转义
    LineTerminator
        U+000A  最好统一使用这个
        u+000D

        把代码限制在 ascii  内
        把代码限制在 BMP    内
    Comment
        * 不能转码
        \u002a 代替 * 是不可以的
        必须是 /**/ 真实的 / * 等
    Token
        一切有效的东西都叫做 Token
        形成结构用的
            Punctuator
                符号
            

        写出来的有效信息
            IdentifierName
                Keywords
                Identifier
                    标识符
                        变量名
                            不能和关键字重合
                        属性名
                            可以和关键字重合

                    词法扫描时都认为是 Identifier，语法解析时才会尝试着解释为关键字或者是其他的东西

                    不带关键字，起到了关键字的作用
                    {
                        get a()
                    }
                Future reserved Keywords: enum
            Literal
                True False Null等
                Number
                    IEEE 754 Double Float 内存布局
                    Sign (1)
                    Exponent(11)
                    Fraction(52)
                String
                Boolean
                Object
                Null
                Undefined
                Symbol

        
    

```