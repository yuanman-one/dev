# HTML

[toc]

## 一、html(HyperText Markup Language）

### THML 是超文本标记语言，用来进行网页制作

注意：指的是不仅仅包含文本，还包含颜色，字体，图片，音频视频等
标记也称为标签，标签由尖括号包围的关键字，并且标签通常是成对出现，
第一个标签是开始标签，第二个是结束标签

### 注释

`<!--注释内容-->`

注意：注释不可以嵌套

### 常用标签

1. 文本标签
   - 标题
     `<h1></h1>……<h6></h6>`
   - 段落
     `<p></p>`
   - 水平线
     `<hr />`
2. 列表标签
   - 定义列表
     dl：define list 定义列表
     dt：define title 定义标题
     dd：define date 定义数据
   - 无序列表
     ul：unordered list 无序列表
     li：list item 列表项
     注意：ul 中有个 type 可以用来控制显示样式，其取值如下
     none：没有样式
     disc：默认实心圆
     circle：空心圆
     square：实心正方形
   - 有序列表
     ol：order list 定义有序列表
     li：list item 列表项
     注意：ol 中有个 type 可以用来控制显示顺序的样式，数字，小写字母，大写字母等
   - 列表嵌套
3. 分区标签
   - 用来装显示内容的，元素本身没有显示效果，使用分区标签将页面内容划分为几块，
     好处是便于对内容批量管理
   - 常用标签
     div：独占一行
     spen：一行多个
     header：头
     article：正文
     footer：尾部
4. 标签元素分类
   - 块级元素：独占一行 如：`div ，p，h1……h6，hr`
   - 行内元素：可以和其他行内元素共占一行，
     如 spen ,`<i></i>`和`<em></em>`斜体
     `<b></b>`和`<strong></strong>`字体加粗
     `<u></u>`下划线
     `<del></del>`和`<s></s>`删除线
   - 注意：
     1. 行内元素中文本内容多个空格会合并成一个空格，
        如果需要显示多个空格，使用`&nbsp`
        常见特殊字符
        `<:&lt`
        `>:&gt`
        `<br>`换行
5. 图像标签
   - `<img />`
   - 属性
     - src：图片的路径
     - 注意：相对路径是相对当前页面文件，如果是同级文件直接写文件名，
       如果是上级文件，则../文件名，如果是下级，文件夹名/文件名。
     - 绝对路径是完整路径，如果访问的图片时站外资源，必须使用绝对路径，
       这种称为盗链，好处是不占自己资源，坏处是别人换地址，自己就不显示了.
     - width/height：控制图片宽高
     - title：当鼠标在图片上悬停时显示文本
     - alt：当图片不能正常显示的时候显示文本
     - 注意：支持的图片格式 .jpg .png .gif
6. 图像地图

   - 可以将图片的某个区域作为可以点击的连接
   - 使用

   ```html
   <img usermap="#name" />
   <map id="" name="">
     <area shape="" coords="" href="" />
   </map>
   ```

   - 注意：usermap 取值为 map 中的 id（火狐生效，谷歌无效），取值为 map 中 name 的值都可以生效
     id 和 name 属性表示地图的唯一标识，把地图给到图片的时候使用
     shape 表示形状，取值为 circle 和 rect
     coords 表示坐标，若 shape 取值为 circle，其取值为圆心坐标
     若 shape 取值为 rect，其取值为矩形两个对角线点的坐标
     href 表示连接地址

7. 超链接
   - `<a></a>`
   - 常用属性
   - href：连接地址
   - target：取值有以下几种
     \_blank 表示跳转到新的页面
     \_top 表示在整个窗口中打开被连接的文档
     \_self 表示在相同的框架中打开被连接的文档，默认的
     \_parent 表示在父框架集中打开被连接的文档
   - 锚点
     先通过 a 标签创建一个锚点
     `<a id="id名称"></a>`
   - 通过另一个 a 标签跳转到锚点所在的位置
     `<a href="#锚点的id名称"></a>`

## 二、表格

1. 定义表格`<table></table>`
2. 创建行`<tr></tr>`
3. 创建列`<td></td>`
4. 属性
   - border：表示外边距的粗细，默认为 0
   - cellspacing：单元格间距和单元格距离外边框的距离
   - cellpadding：内容与单元格边框的距离
   - width/height：设置表格宽高
   - rowspen：合并行
   - colspen：合并列
5. 表格分组
   - thead：头分组
   - tbody：体分组
   - tfoot：脚分组
   - th：可以让表头字体加粗
   - caption：表格标题，内容会自动居中并且显示在表格上面

## 三、表单

通常在浏览器中获取用户输入的内容传递给服务器

### 定义表单

`<form></form>`

1. 属性

   - action：表单提交的 url
   - method：表单提交的方式
   - enctype：表单数据进行编码的方式，取值有
   - appplicaton/x-www-form-urlencoded：在发送前编码所有字符（默认）
   - multipart/form-data：不对字符编码，在使用包含文件上传控件的表单时，必须使用该值
   - text/plain：空格转换为`+`号，但不对特殊字符编码

### 控件

- 文本框
  `<input type="text">`
- 属性
  name：数据提交到服务器时，告诉服务器文本框值的含义
  placeholder：占位文本
  value：默认值
  maxlenght：最大字符长度
  readonly:只能读不能改
- 密码框
  `<input type="password"/>`
- 单选框
  `<input type="radio"/>`
- 复选框
  `<input type="checkbox"/>`
- 属性：checked，默认选中
- 文件选择控件
  `<input type="file"/>`
- 日期
  `<input type="date"/>`
- 隐藏域
- 当需要提交一些用户看不见的信息时，使用此控件
  `<input type="hidden"/>`
- 下拉选

  ```html
  <select>
    <option>选项1</option>
    <option>选项2</option>
    <option>选项3</option>
    …………
  </select>
  ```

- 文本域
  `<txetarea rows="" cols""></txetarea>`
- 按钮
  `<input type="button">`//需要绑定事件提交
  `<input type="submit">`//可以直接提交
  `<input type="reset">`//重置

## 四、页面框架frameset/frame

1. 实现多窗口布局
2. frameset/frame
3. 属性

   - cols：垂直切割，值可以是整数，百分比，和"\*"代表占用剩余空间
     值的个数表示被切割成多个页面
   - rows：横向切割，和 cols 用法一样
   - border：设置框架的边框宽度
   - bordercolor：设置边框颜色
   - frameborder:设置框架的边框，其值有 0 和 1，0 表示不显示边框，1 表示显示边框
   - noresize：禁止随意改变框架的大小，默认可以改变，取值是 noresize，此属性加在 frame 上
   - name：用来区分框架，此属性加在 frame 上
   - src：用来引入外界页面。此属性加在 frame 上

   - 注意：frameset 不能和 body 共存
   - frame 不能脱离 frameset 单独使用
   - 若浏览器不支持框架，为了兼容，使用`<noframes>`标签，
   - 当浏览器不支持框架时，显示`<noframes>`标签中的内容

4. iframe

   - 页面复用
   - 属性
   - src：引入页面地址
   - name：框架表识名
   - width：插入页面宽度
   - height：插入页面的高度
   - scrolling：是否显示滚动条，取值有 auto，yes，no，默认是 auto
   - frameborder：边框大小

5. iframe 和 frame 区别

   - frame 需要使用多个文件，目录结构复杂
   - iframe 内嵌灵活，可以在网页的任何位置使用
   - iframe 可以作为模板，在本网站的多个页面复用
