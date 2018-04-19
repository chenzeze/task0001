# task0001

baidu_ife2015 初级班task001

检错:

    1.header logo应该用a标签，包围img，方便logo的下载

    2.github图标应该用a标签,图片为背景图，另外a标签中有文字说明Mygithub，用css隐藏起来,有利于seo
    
    3.footer中的友情链接应当使用dl*m>dt+dd*n而不是ul，因为第一项和下边的内容有明显的定义关系。
    
    4.img标签用到的图片和css中用到的图片应当用两个文件夹来存放，前者可能会随着服务器的变动发生变化，后者可能被放在CDN上
    


task0001-8验证

doctype是什么，它是干啥用的

    DTD Doctype Defination 声明文档类型 告诉浏览器自己用的是xml/xhtml ,从而浏览器用对应的方法渲染和解析文档

ul、ol、dl都适合用在什么地方

    Ul 无序列表
    Ol 有序列表
    Dl 自定义列表
    Dl*m>dt+dd*n

能够娓娓道来你是怎么理解HTML语义化的

    HTML语义化，在没有css的情况下，也能使页面的结构清晰，便于SEO
    
CSS选择器都有哪些

    + 后面（其中一个）兄弟元素 
    ～ 后面（所有）兄弟元素 不包括自己
    
    Li:nth-child(2) 是父类（比如ul)下的第二个li
    Li:nth-last-child(2) 是父类（比如ul)下的倒数第二个li
    
    .parent > div:nth-of-type(2) 是parent类下第二个标签类型为div 的
    .parent > div:nth-last-of-type(2)  是parent类下倒数第二个标签类型为div 的
    
    Nav>a:not(:last-of-type) 除了导航栏最后一个a

position都有什么值，区别是什么

    Static：默认定位
    Relative:相对自己定位，relative的自适应高度的第一个子元素能撑起父元素，其他子元素就算高度确定也不能撑起
    Absolute：相对离自己最近的非static的元素定位，absolute的自适应高度的子元素不能撑起父元素

经典的清除浮动代码中每一行语句都是干什么用的，为什么少了它不行

    Clear:both 清除两边的浮动， 解决兄弟元素重叠问题
    Overflow:hidden 给浮动子元素的父元素添加，常用来解决浮动子元素父元素坍塌的问题。原理，给父元素创建BFC，不与浮动元素重叠，并且浮动子元素的高度也能加入到父元素的高度的计算。
    
    创建BFC：1.position除了relative static
            2.display flex,table
            3.Float 除了none,默认float:none
            4.Overflow除了visible

让一个HTML节点居中的各种实现方式

        1.左右居中：Margin: 0 auto;
        2.上下左右居中
        {
            position:absolute;
            Left:50%;
            margin-left:-一半本身宽度;
            top:50%;
            margin-top:-一半本身高度;
        }
        3.文字 text-align:center


神马圣杯布局、双飞翼布局都是些什么东西
        
        
        这两个布局都是在三栏布局，左右宽度固定，中间宽度自适应时用的。
        中间的最前面渲染，是因为中间的内容一般比较重要
        div.center+div.left+div.right
        
        1.圣杯布局  float,margin,relative
        .center {
            float: left;
            width: 100%;
            padding-left: 300px;
            padding-right: 200px;
        }
        .left {
            float: left;
            position:relative;
            left: -300px;
            width: 300px;
            margin-left: -100%;
        }
        .right {
            float: left;
            position:relative;
            left: -200px;
            width: 200px;
            margin-left: 200px;
         }



         2.双飞翼布局 float,margin, .center>div.innerContent
         .center {
             float: left;
             width: 100%;
         }
         .left {
             float: left;
             width: 300px;
             margin-left: -100%;
         }
         .right {
             float: left;
             width: 200px;
             margin-left: 200px;
         }
         .innerContent {
             margin-left: 300px;
             margin-right: 200px;
         }


强大的负外边距都能干嘛


         元素居中，三列布局
        

不小心提起文档流的时候还能接着解释到底啥是文档流

    文档流的定义如下： 
    1、从左至右，从上至上的布局。 
    2、符合html中标签本身含义的布局，比如某些标签独占一行。有些标签属于行内元素等。 

