# JavaWeb
## Web标准
**HTML**：负责网页的结构（页面元素和内容）--超文本标记语言
**CSS**：负责网页的表现（页面元素的外观、位置等页面样式，如颜色大小等）--层叠样式表
**JavaScript**：负责网页的行为（交互效果）
## HTML
### 图片标签
* src：指定图像的url（绝对路径、相对路径）
* width：指定图像的宽度（像素、相对于父元素的百分比）
* height：图像的高度（像素、相对于父元素的百分比）
### 路径书写方式
* 绝对路径
1.绝对磁盘路径
2.绝对网络路径
* 相对路径
### CSS引入方式
* 行内样式：写在标签的style属性中
* 内嵌样式：写在style标签中
* 外联样式：写在一个单独的.css文件中
* 颜色表示形式：
1.关键字
2.rgb表示法
3.十六进制表示法
### CSS选择器：用来选取需要设置样式的元素（标签）
* 元素选择器
* id选择器
* 类选择器
* 优先级：id>类>元素
### 视频标签
* src：规定视频的url
* controls：显示播放控件
* width：播放器的宽度
* height：播放器的高度
### 音频标签
* src：规定音频的url
* controls：显示播放控件
### div标签
* 一行只显示一个（独占一行）
* 宽度默认是父元素的宽度，高度默认由内容撑开
* 可以设置宽高（width、height）
### span标签
* 一行可显示多个
* 宽度和高度默认由内容撑开
* 不可以设置宽高（width、height）
### CSS盒子模型
组成：<font color="red">内容（content）、内边距（padding）、边框（border）、外边距（margin）</font>
### 表格标签
场景：在网页中以表格（行、列）形式整齐展示数据
### 表单标签
* 场景：在网页中主要负责数据采集功能
* 属性：
1.action:规定当提交表单时向何处发送表单数据，URL
2.method：规定用于发送表单数据的方式。GET(在URL后拼接表单数据，URL长度有限制)、POST（在消息体/请求体中传递的，参数大小无限制）
## JavaScript
### JavaScript的引入方式
* 内部脚本：将JS代码定义在HTML页面中
* 外部脚本：将JS代码定义在外部JS文件中，然后引入到HTML页面中
### 变量
* JS中用<font color="red">var</font>关键字来声明变量
* JS是一门弱类型语言，变量<font color="red">可以存放不同类型的值</font>
### Array
JS中的数组相当于Java中集合，数组的长度是可变的，而JS是弱类型，所以可以存储任意的类型的数据。
### JSON
* JavaScript Object Notation--JS对象标记法
* JSON是通过JS对象标记法书写的文本
* 由于其语法简单，层次结构鲜明，先多用于作为<font color="red">数据载体</font>，在网络中进行数据传输
### BOM
* Browser Object Model--浏览器对象模型
* 组成：
1.Window：浏览器窗口对象
2.Navigator：浏览器对象
3.Screen：屏幕对象
4.History：历史记录对象
5.Location：地址栏对象
### DOM
* Document Object Model--文档对象模型
* 将标记语言的各个组成部分封装为对应的对象
1.Document：整个文档对象
2.Element：元素对象
3.Attribute：属性对象
4.Text：文本对象
5.Comment：注释对象
### 事件监听
JS可以在事件被侦测到时<font color="red">执行代码</font>
### 事件绑定
* 通过HTML标签中的事件属性进行绑定
* 通过DOM元素属性绑定
## Vue
* Vue是一套<font color="red">前端框架</font>，免除原生JS的DOM操作，简化书写
* 实现数据的<font color="red">双向绑定</font>，将变成的关注点放在数据上