正则表达式匹配所有 Number 直接量
```js
<DecimalNumber> = /(\.([0-9]*)) | (0|[1-9][0-9]*)(\.*)[0-9]*/
```

正则表达式匹配所有 Number，四则运算表达式
```js

<MultipleExpression> = <DecimalNumber> | 
    <MultipleExpression> "*" <DecimalNumber> |
    <MultipleExpression> "/" <DecimalNumber>

<AdditiveExpression> = <MultipleExpression> | 
    <AdditiveExpression> "+" <MultipleExpression> |
    <AdditiveExpression> "-" <MultipleExpression>
```