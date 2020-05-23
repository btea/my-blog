### CSS
**css写法**  
* 1.外部样式，在html文件内部用link标签导入css文件。  
* 2.在html文件头部创建style标签，样式写在style标签内部。  
* 3.内联样式，样式写在html标签内部的style属性里面。

**css的引用、开头**  
* 1.样式放头部，脚本放脚下。不内嵌，只外链。  
* 2.@charset "utf-8";注意，必须要定义在 CSS 文件所有字符的前面（包括编码注释），@charset 才会生效。  
* 3.慎用 * 通配符。所谓通配符，就是将 CSS 中的所有标签均初始化，不管用的不用的，过时的先进的，一视同仁，这样，大大的占用资源。要有选择的初始化标签。  

**css书写顺序**   
* 1.位置属性(position, top, right, z-index, display, float等)  
* 2.大小(width, height, padding, margin)  
* 3.文字系列(font, line-height, letter-spacing, color- text-align等)  
* 4.背景(background, border等)  
* 5.其他(animation, transition等)  

**css书写规范**  
css-written-order  
使用CSS缩写属性  
CSS有些属性是可以缩写的，比如padding,margin,font等等，这样精简代码同时又能提高用户的阅读体验。  

 
**CSS命名规范-BEM**  
css的样式应用是全局性的，没有作用可言。为了防止样式冲突，采用BEM命名规范。  
BEM的命名规范很容易记：block-name-element-name__modifier-name(模块名 + 元素名 + 修饰器名)。  
[element组件采用bem命名规范](https://github.com/ElemeFE/element/blob/dev/packages/alert/src/main.vue)  

参考资料：  
[bemCss命名规范](https://bemcss.com/)  
[推荐大家使用的CSS书写规范、顺序](https://www.cnblogs.com/liaohongwei/p/9698687.html)  
