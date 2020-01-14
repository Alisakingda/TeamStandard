# 团队规范

## 代码优化

> 多重三元表达式使用查表法优化

`const api = this.type === 'ups' ? upsOne : this.type === 'air' ? airOne : this.type === 'service' ? serviceOne : ''`

> 优化

```js
const apiMethodMap = {
  ups: upsOne,
  apr: airOne,
  service: serviceOne
}
const api = apiMethodMap[this.type] || upsOne
```

> 对象，数组，字符串，非空等判断，不要自己写逻辑，直接用 lodash 提供的函数

`Lodash.isEmpty()`

## commit 规范

[规范](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)

## 命名规范

> 单位

- 统一使用 rpx，固定尺寸除外（1px 边框之类）

> 点击事件统一使用@tap

> 组件命名规范

- 组件使用-方式命名，引用组件定义使用大写首字母驼峰命名

## CSS 规范

> 代码格式化

- 展开格式（Expanded）

```css
.jdc {
  display: block;
  width: 50px;
}
```

> 代码大小写

- 属性字符串允许使用大小写,驼峰命名

> 选择器

- 尽量少用通用选择器 \*
- 不使用 ID 选择器
- 不使用无具体语义定义的标签选择器

> 代码缩进

- tab

> 分号

- 每个属性声明末尾都要加分号；

```css
.jdc {
  width: 100%;
  height: 100%;
}
```

> 代码易读性

- 括号与类名之间一个空格，冒号与属性值之间一个空格

```css
.jdc {
  width: 100%;
}
```

> 属性值引号

- css 属性值需要用到引号时，统一使用单引号

> 边框样式写法

- 线条粗细 线条样式 颜色

`border: 1px solid #d9d9d9;`

> 属性书写顺序

1. 布局定位属性：display / position / float / clear / visibility / overflow
2. 自身属性：width / height / margin / padding / border / background
3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …

`平时写的很随意 -_-`

> CSS3 浏览器私有前缀写法

```css
.jdc {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -o-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

> 注释规范

- 单行注释
- 模块注释

```css
/* Module A 
---------------------- */
.mod_a {
}

/* Module B
 ---------------------- */
.mod_b {
}
```

- 文件信息注释

```css
@charset "UTF-8";
/**
 * @desc File Info
 * @author Author Name
 * @date 2019-10-10
 */
```

> 覆盖规范

- 尽可能少用 importnt
- vue 单文件组件统一使用 css/less/sass scoped
- 每个页面/组件需要有一个全局唯一的标识 id/class，属于它下面的样式都需要加上该唯一标识
- 避免全局修改已有样式，必须具体到页面上(通过权重)
- 禁用全匹配\*选择器（特殊情况除外，如初始化）

> 媒体查询

- 优先 PC 端

```css
body {
  background: gray;
}
@media screen and (max-width: 1366px) {
  body {
    background: red;
  }
}
@media screen and (max-width: 1200px) {
  body {
    background: yellow;
  }
}
@media screen and (max-width: 920px) {
  body {
    background: green;
  }
}
@media screen and (max-width: 768px) {
  body {
    background: black;
  }
}
```

> 单位规范

- 常用绝对单位

1.  px：像素 (计算机屏幕上的一个点)
2.  cm：厘米
3.  in：英寸
4.  pt：磅 (1 pt 等于 1/72 英寸

- 常用相对单位

1.  %：父元素百分比
2.  vw：视口宽度百分比
3.  vh：视口高度百分比
4.  em：当前字体倍数
5.  rem：根元素字体倍数
6.  rpx：微信小程序专用，规定屏幕宽为 750rpx

## JS 规范

```
1、缩进使用两个空格；
2、字符串使用单引号，除非是为了避免转义；
3、不出现未使用的变量
4、关键字后有一个空格
5、函数参数列表的括号前有一个空格
6、始终用===，不使用==
7、中辍操作符前后要有一个空格。
8、逗号后面有一个空格、
9、else与它的大括号同行
10、if语句如果包含多个执行体语句则使用大括号；若只有一条执行语句，可并行无括号，也可用大括号，但不可换行无大括号。
11、始终处理函数的err参数
12、浏览器全局变量始终添加前缀window.
13、不要有多个连续空行
14、三元表达式如果是多行，则？和：放在各自的行上
15、var声明，每个声明占一行
16、为了清除的表明它是一个赋值表达式（=），而不是一个等式（===）的误写，用括号包裹条件中的赋值表达式。
17、单行语句块的内侧要有空格
18、变量和函数的名字使用camelCase（驼峰）格式
19、无多余逗号
20、逗号必须放在当前行的末尾
21、. 应当与属性同行
22、文件以空行结尾
23、函数名字和调用括号之间没有空格
24、键名和键值之间要有空格
25、构造函数的名字以大写字母开始
26、没有参数的构造函数在调用时必须有括号
27、对象若定义了setter，则必须定义相应的getter
28、子类的构造器必须调用super
29、使用对象字面量，不使用对象构造函数
30、不使用argument.callee 和 argument.caller
31、不要给class赋值
32、不要修改由const声明的变量
33、在条件句中不要使用常亮，循环语句除外
34、正则表达式不要使用控制字符
35、不使用debugger语句
36、不要对变量使用delete操作符
37、函数定义无重复参数
38、class定义无重复成员
39、对象字面量无重复键名
40、switch语句无重复case语句
```

[JS 规范](https://zhangzhenfei.github.io/15257651425045.html#toc_0)
