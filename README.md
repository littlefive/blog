CSS权威指南读书笔记
====

CSS权威指南：
    第一章 css和文档
1.	元素：
            替换元素，是指用来替换元素内容的部分并非直接用文档内容直接表示；
            非替换元素，显示元素本身生成框中显示；
            块级元素：生成一个元素框，默认的填充起父元素的内容区，旁边不能有其他的元素，有p div ul ol li body 
            行内元素：文本行内生成元素框，块级元素是不能嵌套在行内元素里的，a  strong em span  b  i ,要想让他们成为块级元素，
                                需要加display：block
    2.   样式表的引入：link  @import指令   内嵌样式 
                                 @import 与link的差别1：老祖宗的差别。link属于XHTML标签，而@import完全是CSS提供的一种方式。link除了可以加载CSS外，还可以做很多其它的事情，比如定义RSS，定义rel属性等，@import就只能加载CSS了。
差别2：加载顺序的差别。当一个页面被加载的时候（就是被浏览者浏览的时候），link引用的 CSS会同时被加载，而@import引用的CSS会等到页面全部被下载完再被加载。所以有时候浏览@import加载CSS的页面时开始会没有样式（就 是闪烁），网速慢的时候还挺明显（梦之都加载CSS的方式就是使用@import，我一边下载一边浏览梦之都网页时，就会出现上述问题）。
差别3：兼容性的差别。由于@import是vss2.1提出的所以老的浏览器不支持，@import只有在IE5以上的才能识别，而link标签无此问题。差别4：使用dom控制样式时的差别。当使用javascript控制dom去改变样式的时候，只能使用link标签，因为@import不是dom可以控制的。
    第二章  选择器
        元素选择器：p{ color:red }
           类选择器：.wrap{ font:14px}
           ID选择器：#wrap{ background-color:#eee; }
      选择器分组：
           通配选择器：*｛color：red｝
            属性选择器：*[title]｛color：red｝选择带有title属性的全部元素改变他们的字体为红色
                                p[class= warning]{ color:red }选择class=warning的P元素
                                 p[class~= warning]{ color:red }选择class属性值中出现warning的P元素
            子串匹配属性选择器：[foo ^="bar"] 选择foo属性值以“bar”开头的所有元素
                                                [foo $="bar"] 选择foo属性值以“bar”结尾的所有元素
                                                [foo *="bar"] 选择foo属性值中包含“bar”的所有元素
文档结构：后代选择器： div  p｛｝
			选择子元素：div>p｛｝
			选择相邻兄弟元素：div+p｛｝改变div元素之后出现的p元素样式（有共同的父类）
伪类和伪元素：
静态伪类：link  未访问
：visited 访问后
动态伪类：hover   鼠标悬浮
		：active 元素被激活
		：focus 获取到光标  （ie7不支持表单：focus） 
	容易记下：LAHV
：first-child  选择第一个子元素
：first-letter  设置首字母样式
：first-line 选择第一行
第三章  结构，层叠
	权重排列：id>类>元素
		内联样式的特殊性
		！Important
层叠样式表，基于的方法就是让样式层叠在一起，结合继承和特殊性规则：
1.	找到相关规则，给定元素匹配的选择器
2.	找到带有！important的选择器，带有的胜出
3.	根据权重排列顺序，权重大的胜出
4.	根据出现的顺序排列
第四章  值和单位
	1.绝对长度单位：in cm mm pt 
	相对长度但单位：em：父元素设定了大小，em的值相对于父元素的大小而改变
					ex：用的少
	px：像素
第五章  字体
字体排列顺序：Font-style  font-variant  font-weight  font-size  line-height  font-family
第六章   文本属性
Text-indent 文本缩进
Text-align 文本对齐，应用于块级元素
Line-height 行高，减掉字体大小，再除以2，得到行高距
			Inherit属性：使用父元素的值，应用于行内元素，块级元素


