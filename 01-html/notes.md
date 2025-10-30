#  HTML5 基础笔记（Day 1）

## 🗂 目录
1. [VS Code 常用快捷键](#vs-code-常用快捷键)  
2. [HTML5 文件声明](#html5-文件声明)  
3. [HTML5 基本骨架](#html5-基本骨架)  
4. [常用标签](#常用标签)  
   - [标题标签](#标题标签)
   - [段落、换行、水平线](#段落换行水平线)
   - [图片标签](#图片标签)
   - [超文本链接](#超文本链接)
   - [文本标签](#文本标签)
   - [有序列表](#有序列表)
   - [无序列表](#无序列表)
   - [表格标签](#表格标签)
5. [表单 Form](#form-表单)
6. [块级、内联、行内块元素](#块级元素内联元素行内块元素)
7. [div 容器](#div标签)
8. [HTML5 语义化标签](#html5-语义标签)

---

## VS Code 常用快捷键

| 功能 | 快捷键 |
|------|---------|
| 代码格式化 | `Shift + Alt + F` |
| 复制当前行 | `Shift + Alt + ↑/↓` |

---

## HTML5 文件声明

```html
<!DOCTYPE html>
```

- `DOCTYPE` 表示当前文档类型，告诉浏览器这是一个 HTML5 文件。
- 可以避免浏览器进入“怪异模式”（兼容旧标准的渲染方式），确保使用标准模式。

---

## HTML5 基本骨架

```html
<html>
  <head>
    <title>页面标题</title>
    <meta charset="utf-8" />
  </head>
  <body>
    页面内容
  </body>
</html>
```

### 各部分说明：
- `<html>`：HTML 文件的根标签。
- `<head>`：包含文件元信息（如标题、编码、SEO 关键字等）。
- `<title>`：网页标题，会显示在浏览器标签栏。
- `<meta>`：元信息，`charset="utf-8"` 设置编码方式。
- `<body>`：网页主要内容。

---

## 常用标签

### 标题标签

```html
<h1 align="center">一级标题</h1>
```

- 共 6 级标题 `<h1>`～`<h6>`，字体依次变小。  
- `align` 属性控制对齐方式：`left`、`center`、`right`。

---

### 段落、换行、水平线

#### 段落 `<p>`

```html
<p>这是一个段落。</p>
```

#### 换行 `<br />`

```html
换行前<br />换行后
```

#### 水平线 `<hr />`

```html
<hr color="red" width="300px" size="2" align="center" />
```

---

### 图片标签 `<img>`

```html
<img
  src="image.png"
  alt="红楼梦第一集"
  title="红楼梦第一集"
  width="300px"
/>
```

| 属性 | 含义 |
|------|------|
| `src` | 图片路径 |
| `alt` | 图片加载失败时显示的文字 |
| `title` | 鼠标悬停时的提示文本 |
| `width` / `height` | 控制尺寸 |

**路径规则：**
- 同级：`./image.png`
- 子级：`./image/1.jpg`
- 父级：`../1.jpg`

---

### 超文本链接 `<a>`

```html
<a href="https://skr.skr3.cc:666/">
  <img src="2.png" alt="櫻花動漫" width="300px" />
</a>
<a href="https://skr.skr3.cc:666/">樱花动漫</a>
```

- 链接内容可以是文字、图片或任意元素。  
- `href` 为跳转地址。

---

### 文本标签

```html
<em>em：着重文字</em><br />
<b>b：粗体</b><br />
<i>i：斜体</i><br />
<strong>strong：强调语气</strong><br />
<del>del：删除线</del><br />
<span>span：无语义，用于 CSS 布局</span>
```

> 💡 `em` 和 `strong` 具有语义层次，有助于 SEO 优化。  
> `em` 表示轻度强调，`strong` 表示强烈强调。

---

### 有序列表 `<ol>`

```html
<ol type="1">
  <li>贾宝玉</li>
  <li>林黛玉</li>
  <li>薛宝钗</li>
</ol>

<ol type="I">
  <li>S 组
    <ol>
      <li>战文欲 AG</li>
      <li>久哲 TTG</li>
      <li>刑天 JDG</li>
    </ol>
  </li>
</ol>
```

| 属性 | 说明 |
|------|------|
| `type` | `1`, `a`, `A`, `i`, `I`（编号样式） |

---

### 无序列表 `<ul>`

```html
<ul type="square">
  <li>
    2025 KPL 年度总决赛赞助商
    <ul>
      <li>IQOO</li>
      <li>TT语音</li>
      <li>长安汽车</li>
      <li>快手</li>
      <li>JD</li>
    </ul>
  </li>
</ul>
```

| 属性 | 类型 |
|------|------|
| `disc` | 实心圆 |
| `circle` | 空心圆 |
| `square` | 实心方块 |
| `none` | 无标记 |

---

### 表格标签 `<table>`

```html
<table border="1" width="400" height="300">
  <tr>
    <td>单元格1</td>
    <td>单元格2</td>
    <td>单元格3</td>
  </tr>
  <tr>
    <td colspan="2">水平合并</td>
    <td rowspan="2">垂直合并</td>
  </tr>
  <tr>
    <td>单元格</td>
    <td>单元格</td>
  </tr>
</table>
```

| 属性 | 功能 |
|------|------|
| `border` | 边框 |
| `width` / `height` | 表格尺寸 |
| `colspan` | 横向合并单元格 |
| `rowspan` | 纵向合并单元格 |

---

## Form 表单

```html
<form action="server.php" method="post">
  用户名：<input type="text" name="username" /><br />
  密码：<input type="password" name="pwd" /><br />
  性别：
  <input type="radio" name="gender" value="男" />男
  <input type="radio" name="gender" value="女" />女<br />
  爱好：
  <input type="checkbox" name="hobby" value="唱歌" />唱歌
  <input type="checkbox" name="hobby" value="跳舞" />跳舞<br />
  上传文件：<input type="file" /><br />
  <button type="submit">提交</button>
</form>
```

| 属性 | 含义 |
|------|------|
| `action` | 提交地址 |
| `method` | 提交方式：`get` 或 `post` |

---

## 块级元素、内联元素、行内块元素

| 类型 | 布局方式 | 可设置宽高 | 常见标签 |
|------|-----------|-------------|-----------|
| 块级元素 | 垂直排列 | √ | `div`, `form`, `h1~h6`, `table` |
| 内联元素 | 水平排列 | × | `a`, `b`, `span`, `strong` |
| 行内块元素 | 水平排列 | √ | `img`, `input`, `button` |

---

## div标签

- 容器标签，无语义，用于布局与分区。
- 常与 CSS 配合使用，形成模块化结构。

---

## HTML5 语义标签

| 标签 | 功能 |
|------|------|
| `<header>` | 页眉、顶部信息 |
| `<nav>` | 导航栏 |
| `<section>` | 内容区块（具有主题） |
| `<aside>` | 侧边栏或补充内容 |
| `<footer>` | 页脚信息 |
| `<article>` | 独立的内容单元，如新闻或博客文章 |
