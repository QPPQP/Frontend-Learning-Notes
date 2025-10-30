<img width="48" height="48" alt="006EEB82" src="https://github.com/user-attachments/assets/7d045f4a-0ad5-4abf-87e7-3cd83c94f8d2" /># Day1 HTML5 基础知识

## VS code 常用快捷键
代码格式化：Shift + Alt +F

快速复制某一行代码：Shift + Alt + Up/Down

## H5 文件声明
<!DOCTYPE html>

DOCTOPY:document type

该声明能够让浏览器识别其为H5文件，并且避免浏览器怪异模式（浏览器为了兼容早期不标准规范而产生的模式），进入标准模式

## H5 基本骨架
<html></html> ：html标签,限定了h5开始与结束
  
<head></head> : 头部定义了文件的各种属性和各种信息。如：

title(head必须包含):该标签内的文本信息会直接出现在浏览器地址栏中。同时，因为优先级高，会直接影响浏览器的SEO，通常是文件的主题。举例：搜索结果里面的蓝链文本内容

meta : 网页的基本信息，如：charset = "utf-8"，编码格式。其中较为常用的编码格式有：utf-8、gbk(中、英)

<body></body> : 文件正文，包含（文本、超链接、图像、图表、列表、表单）

## 标签
### 标题
定义：<h1>~<h6> 共6级标题
常用属性：<h1 align = "left/right/center">


### 段落、换行、水平线
#### 段落
标签：<p></p>,p:Paragraph
代码示例：
<p>
      贾宝玉在警幻仙姑引领下进入孽海情天，孽海情天是太虚幻境中的一个宫门，上有匾额和对联，对联内容为“厚地高天，堪叹古今情不尽；痴男怨女，可怜风月债难偿”。贾宝玉在此处思考了“古今之情”和“风月之债”的含义，随后跟随警幻仙姑进入孽海情天内的各个司（如痴情司、结怨司等），并查看了“薄命司”中金陵十二钗的判词
    </p>
    
#### 换行
标签：<br></br>,b:Break
本质是一个空的H5元素

#### 水平线
标签：<hr></hr>
简单来说就是一条分隔线
常用属性：color、width(单位：px)、size(水平线高度)、align(对齐方式)
代码示例：
 <hr color="Red" />


### 图片
标签：<img></img>
常用属性：
src:图片路径
alt:当图片损坏的情况下代替图片出现的文本，常见于当图片还未加载出来时出现的文本
width、height:图片规模
title:当鼠标悬停在图片上面时出现的文本
其他：
注意，一个<img>标签只能放一张图片
代码示例：
    <img
      src="image.png"
      alt="红楼梦第一集"
      title="红楼梦第一集"
      width="300px"
    />

路径相关知识复习：
相对路径
子级关系：/
举例来说，image/1.jpg,1.html与image文件夹同级，此时，src = "./image/1.jpg"
父级关系：../
举例来说，html/1.html,1.jpg与html文件夹同级，此时，src = "../1.jpg"
同级关系：./
一般来说，直接用文件名就行，但是当引用同级别文件夹下的子文件时就不能省略了，如src = "./image/1.jpg"中的"./image"

### 超文本链接
标签：<a></a>
其他：注意超文本链接可以是：一个字、一 个/组 词、也可以是一幅图，点击该图片可以跳转到其他文档
代码示例：
    <a href="https://skr.skr3.cc:666/">
      <img
        src="2.png"
        alt="櫻花動漫"
        title="即將跳轉到櫻花動漫網"
        width="300px"
      /> </a
    >
    <a href="https://skr.skr3.cc:666/">樱花动漫</a> <br />

  ### 文本
  代码示例：
      <em>em 定义着重文字</em><br />
    <b>b 定义粗体文字</b><br />
    <i>i 定义斜体文字</i><br />
    <strong> strong 定义加重语气</strong><br />
    <del>del 定义删除字</del><br />
    <span>span 无意义,为后面css做准备</span>
注意：em、strong 含有语义的层次，我猜测是为无障碍设计的，在视觉表现上与i,b基本相同，但是可以为搜索做强调，优化seo,加大关键词强度，在"强调"程度上：em只是语气加重，strong则是严重强调,比如：Attention！Error

### 列表标签之有序列表
标签：<ol><li></li></ol>,ol:order list,li:list item
常用属性：
type:<ol type>,类型有：1(数字)，a(小写字母)、A(大写字母)、i(小写罗马数字)、I(大写罗马数字)
注意：有序列表是可以嵌套的
表现：段落前面有序号
代码示例：<!-- 有序列表 -->
    <ol type="1">
      <li>贾宝玉</li>
      <li>林黛玉</li>
      <li>贾营村</li>
      <li>甄士隐</li>
      <li>薛宝钗</li>
      <li>薛蟠</li>
    </ol>
    <!-- ol:order list li:list item 
     type ：1、a、A、i、I-->
    <ol type="I">
      <li>
        S 组
        <ol>
          <li>战文欲 AG</li>
          <li>久哲 TTG</li>
          <li>刑天 JDG</li>
        </ol>
      </li>
    </ol>

  ### 列表标签之无序列表
  标签：<ul><li></li></ul>,ul:unorder list
  表现：此列项目使用粗体圆点（典型的小黑圆圈）进行标记
  常用属性：
  type:<ul type> </ul>,类型有：disc(经典实心圆)、circle(空心圆)、square(实心小方块)、none(不显示)
  代码示例：
  <ul type="square">
      <li>
        2025 KPL 年度总决赛赞助商(排名不分先后)
        <ul>
          <li>IQOO</li>
          <li>tt语音</li>
          <li>长安汽车</li>
          <li>快手</li>
          <li>JD</li>
        </ul>
      </li>
    </ul>
    无序列表常用于网页导航栏，新闻
    快捷键：ul>li*5 >就是子标签，同样可以嵌套
    
  ### 表格 
  表格组成：行、列、单元格
  标签：<table> 
   <tr>
     <td> </td>
   </tr></table>
   ,其中，tr:table row
   快捷键：table>tr*n>td*n{单元格}
   常用属性：border(表格的边框)、width、height
   示例代码：
   <table>
      <tr>
        <!-- 行 t row
         td: 代表每一行的单元格，一个单元格代表一列-->
        <td>单元格</td>
        <td>单元格</td>
        <td>单元格</td>
      </tr>
      <tr>
        <!-- 行 -->
        <td>单元格</td>
        <td>单元格</td>
        <td>单元格</td>
      </tr>
      <tr>
        <!-- 行 -->
        <td>单元格</td>
        <td>单元格</td>
        <td>单元格</td>
      </tr>
    </table>
    表格可以嵌套

  单元格合并：
  水平合并(n列合并)：colspan 
  垂直合并(n行合并)：rowspan
  注意：合并的时候仅会保留第一个格子：左、上,不然会破坏表格布局
  示例代码：
    <p>水平合并:colspan 合并 单元格5、6</p>
    <p>垂直合并:rowspan 合并 单元格8、13</p>
    <p>合并单元格9、10、12、13</p>
    <table border="1" width="400" height="300">
      <tr>
        <td>单元格1</td>
        <td>单元格2</td>
        <td>单元格3</td>
        <td>单元格4</td>
      </tr>
      <tr>
        <td colspan="2">单元格5</td>
        <td>单元格7</td>
        <td rowspan="2">单元格8</td>
      </tr>
      <tr>
        <td colspan="2" rowspan="2">单元格9</td>
        <td>单元格11</td>
      </tr>
      <tr>
        <td>单元格14</td>
        <td>单元格15</td>
      </tr>
    </table>

  ## Form 表单
  定义：     
     表单，实际上就是一个布局容器，容纳如输入框、按钮等空间，进行用户交互。
      其中method = get,意味着：
      表单数据会附加在 URL 后面，以 ? 分隔 URL 和参数，多个参数用 & 连接。
      例如：http://example.com/search?name=张三&age=20。
      数据可见，直接暴露在地址栏中,一般用于提交少量数据
      其中method = post,意味着：
      表单数据被包裹在 HTTP 请求的（Body） 中，不会显示在 URL 里。
      数据不可见，仅在请求数据包中传输，一般用于提交大量数据
      表单的组成：
      表单标签(form)、表单域（与用户产生交互的空间，搜集用户的交互信息）、表单按钮
  常用属性：
  action:服务器地址
  name:表单名
  medthod:get/post
  代码示例：
      <form>
      <!-- anction 服务器地址 -->
      <input />
      <!-- 输入框 -->
      <input type="submit" />
      <!-- 可以使用input提交 -->
      <button>提交</button>
      <!-- 也可以使用button ，但是推荐使用button -->
    </form>
    <br />
    <form>
      用户名：<input type="text" name="用户名" /> <br />
      <!-- type 定义输入框类型 -->
      密码：<input type="password" name="pwd" /><br />
      <!-- passport 密码输入框 输入的字符会变成圆点 -->
      单选按钮（只能选一个）: <input type="radio" /> <br />
      复选按钮（可以选多个）： <input type="checkbox" /><br />
      文件上传框：<input type="file" /><br />
      提交按钮：<input type="submit" /><br />
      登录按钮（也是submit）: <input type="submit" value="登录" />
    </form>

  ### 块级元素、内联元素、行内块元素
块级元素： 布局：竖向布局，由上到下布局 height、width:可以设置
可以包含行内元素和其他块级元素


内联元素（行内元素）： 布局：横向布局，由左到右布局，wrap
height、width:不可设置


行内块级元素元素： 布局：横向布局，由左到右布局，wrap
height、width:可以设置


常见块级元素：div/form/h1~h6/hr/table/ui/ol等
常见内联元素：a/b/em/i/em/span/strong等
常见行内块级元素：img/input/button等

### div标签
即容器标签，将控件放入到容器内实现内耦，减少外联

### H5 语义标签
<head></head>
<nav></nav>,导航栏
<section></section>,内容模块，包含一个主题相关的内容集合，且一般会搭配标题（<h1>-<h6>）使用。它不像 <div> 完全无意义，而是强调 “内容的独立性和主题性” ，类似于章节
<aside></aside>,边栏 用于定义 “与主要内容相关但非核心的辅助内容”，通常表现为侧边栏，也可用于页面内的 “补充说明”（如引用、注释、作者信息等），对信息的补充
<footer></footer>,脚部 定义页面或某个独立内容（如 <article>、<section>）的 “页脚区域”，通常包含版权信息、联系方式、导航链接、作者信息等。收尾内容 
<article></article>
用于定义 “完全独立、可单独存在的内容”，比如一篇博客文章、一条新闻、一个论坛帖子、一个产品详情页的描述等。它的核心是 “内容的独立性”—— 即使把这个标签里的内容单独拿出来，依然是完整、有意义的
