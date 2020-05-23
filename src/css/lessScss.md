## Scss与less的区别？  
### 什么是Sass/Scss、less？  
Sass (Syntactically Awesome Stylesheets)是一种动态样式语言，Sass语法属于缩排语法，比css比多出好些功能(如变量、嵌套、运算,混入(Mixin)、继承、颜色处理，函数等)，更容易阅读。  
Sass的缩排语法，对于写惯css前端的web开发者来说很不直观，也不能将css代码加入到Sass里面，因此sass语法进行了改良，Sass 3就变成了Scss(sassy css)。与原来的语法兼容，只是用{}取代了原来的缩进。  
Less也是一种动态样式语言. 对CSS赋予了动态语言的特性，如变量，继承，运算， 函数.  Less 既可以在客户端上运行 (支持IE 6+, Webkit, Firefox)，也可在服务端运行 (借助 Node.js)。  
### Sass/Scss与less区别？ 
**1.编译环境不一样**  
Sass的安装需要Ruby环境，是在服务端处理的，而Less是需要引入less.js来处理Less代码输出css到浏览器，也可以在开发环节使用Less，然后编译成css文件，直接放到项目中，也有 Less.app、SimpleLess、CodeKit.app这样的工具，也有在线编译地址。 
**2.变量声明不一样，Less是@，而Scss是$，而且变量作用域也不一样**  
```css
/* Less作用域 */
@color: #00c;
#header{
    @color: #c00;
    border: 1px solid @color;
}
#footer{
    border: 1px solid @color;
}
/* Less编译后的结果 */
#header{border: 1px solid #cc0000;}
#footer{border: 1px solid #0000cc;}


/* Scss作用域 */
$color: #00c;
#header{
    $color: #c00;
    border: 1px solid $color;
}
#footer{
    border: 1px solid $color;
}
/* Scss编译后的结果 */
#header{1px solid #c00;}
#footer{1px solid #c00;}
```
> 对比两者编译结果可得，scss元素内部定义的同名变量会改变外部定义的同名变量的值，而less不会。 
**3.输出设置，Less没有输出设置，Sass提供4种输出选项：nested、compact、compressed和expanded**  
输出样式风格可以有四种选择，默认为nested  
* nested: 嵌套进的css代码  
* expanded：展开的多行css代码  
* compact：简洁格式的css代码  
* compressed：压缩后的css代码  
**4.Scss支持条件语句，可以使用if{}else{},for{}循环等等。而Less不支持。**  
**5.引用外部css文件**  
Scss引用的外部文件命名必须以`_`开头，如下例所示：其中_test1.scss、_test2.scss、_test3.scss文件分别设置的h1 h2 h3。文件名如果以下划线_开头的话，Sass会认为该文件是一个引用文件，不会将其编译为css文件。  
```css
// 源代码：
@import "_test1.scss";
@import "_test2.scss";
@import "_test3.scss";

// 编译后：
h1 {
  font-size: 17px;
}
 
h2 {
  font-size: 17px;
}
 
h3 {
  font-size: 17px;
}
```
Less引用外部文件和css中的@import没什么区别。  
**6.混合(Mixin)写法不一样**  
Scss定义混合指令采用`@mixin`,引用混合样式则使用`@include`。Less定义混合样式采用 `.` ，应用混合样式直接使用混合样式。  
```css
/* Scss定义混合指令 */
/* 可传参数，可不传参数，也可传多个参数 */
@mixin middle($h) {
    height: $h;
    line-height: $h;
    vertical-align: middle;
}
.footer{
    @include middle(15px);
    color: red;
}
/* 编译后结果 */
.footer{
    height: 15px;
    line-height: 15px;
    vertical-align: middle;
    color: red;
}

/* Less定义混合样式 */
.bordered {
    border-top: dotted 1px black;
    border-bottom: solid 2px black;
}
#menu a {
    color: #111;
    .bordered();
}
.post a {
    color: red;
    .bordered();
}
/* 编译后的结果 */
#menu a {
    color: #111;
    border-top: dotted 1px black;
    border-bottom: solid 2px black;
}
.post a {
    color: red;
    border-top: dotted 1px black;
    border-bottom: solid 2px black;
}
```  
......

参考资料：  
[Less和Scss有什么区别?](http://www.tfan.org/less-vs-scss/)  
[Sass中文网](https://www.sass.hk/docs/)  
[Less中文网](https://less.bootcss.com/#%E6%A6%82%E8%A7%88)
