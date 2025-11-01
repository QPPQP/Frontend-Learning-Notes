# Day 2 Note

## CSS 基础

**目的**：用于装饰 HTML 控件和页面元素。

---

## 一、CSS 语法结构

CSS 主要由两个部分构成：**选择器** 和 **声明**。  
声明由一个或多个属性与值的键值对组成，属性与值之间用冒号分隔，多个声明之间用分号分隔。

```html
<style>
  h1 {
    color: blue;
    font-size: 12px;
  }
</style>
```

---

## 二、CSS 引入方式

### 1. 内联样式（行内样式）不常用

直接在标签内使用 `style` 属性定义样式。

```html
<p style="background: orange; font-size: 24px;">CSS 示例</p>
```

---

### 2. 内部样式（内嵌样式）✅ 较常用

在 `<head>` 标签内使用 `<style>` 标签编写样式，仅对当前页面生效。

```html
<head>
  <style>
    h1 {
      background: red;
    }
  </style>
</head>
```

---

### 3. 外部样式  推荐方式

在单独的 `.css` 文件中定义样式，在 HTML 文件中使用 `<link>` 标签引入。

```html
<link rel="stylesheet" type="text/css" href="style.css">
```

- `rel="stylesheet"`：表示为样式表（固定写法）  
- `type="text/css"`：可省略，默认即为 CSS 类型  
- `href="style.css"`：外部样式文件路径

---

## 三、选择器

### 1. 全局选择器 `*`

匹配所有元素，通常用于页面初始化。

```css
* {
  margin: 0;
  padding: 0;
}
```

---

### 2. 元素选择器

根据 HTML 标签名选择元素。

```css
p {
  font-size: 14px;
}
```

---

### 3. 类选择器（class） 常用

以 `.` 开头，可用于多个元素。

```css
.oneclass {
  width: 800px;
}
```

```html
<h2 class="oneclass">你好</h2>
```

多个类可叠加使用，后定义的样式会覆盖前者：

```css
.classone { color: red; }
.classtwo { color: blue; }
```

```html
<h3 class="classone classtwo">我是一个 h3</h3>
```

> 注意：类名不能以数字开头，多个类名之间用空格分隔。

---

### 4. ID 选择器（id） 常用

以 `#` 开头，只能用于页面中唯一的元素。

```css
#mytitle {
  border: 3px dashed green;
}
```

```html
<h2 id="mytitle">你好</h2>
```

> 注意：ID 唯一，不可重复使用，且不能以数字开头。

---

### 5. 合并选择器

多个选择器共享相同样式时可用逗号分隔。

```css
.header, .footer {
  height: 300px;
}
```

---

### 6. 选择器优先级

| 类型 | 权重值 |
|------|--------|
| 元素选择器 | 1 |
| 类选择器（class） | 10 |
| ID 选择器（id） | 100 |
| 内联样式 | 1000 |

**优先级规则：**  
内联 > ID > Class > 元素  
同级时后定义的样式覆盖前面的样式。

---

## 四、字体属性（Font）

### 1. color（字体颜色）

```css
p { color: red; }
div { color: #ff0000; }
div { color: rgb(255, 0, 0); }
div { color: rgba(255, 0, 0, 0.5); } /* a 表示透明度 [0~1] */
```

---

### 2. font-size（字体大小）

```css
h1 { font-size: 40px; }
h2 { font-size: 30px; }
p  { font-size: 14px; }
```

---

### 3. font-weight（字体粗细）

```css
h1 { font-weight: normal; }
div { font-weight: bold; }
p { font-weight: 900; }
```

| 值 | 含义 |
|----|------|
| normal | 默认 |
| bold | 粗体 |
| bolder | 更粗 |
| lighter | 更细 |
| 100~900 | 数值范围，400 为 normal，700 为 bold |

---

### 4. font-style（字体样式）

```css
p { font-style: italic; }
```

| 值 | 含义 |
|----|------|
| normal | 默认 |
| italic | 斜体 |

> `<i>` 标签默认是斜体。

---

### 5. font-family（字体族）

```css
font-family: "Microsoft YaHei", "Simsun", "SimHei", sans-serif;
```

> 字体名可以使用中文，如 `"楷体"`。

---

## 五、背景属性（Background）

| 属性 | 含义 |
|------|------|
| background-color | 背景颜色 |
| background-image | 背景图片 |
| background-position | 背景位置 |
| background-repeat | 背景平铺方式 |
| background-size | 背景尺寸 |

---

### 1. background-color

```css
.box {
  width: 300px;
  height: 300px;
  background-color: palevioletred;
}
```

---

### 2. background-image

```css
.box {
  width: 600px;
  height: 600px;
  background-image: url("images/img1.jpg");
}
```

> 默认从左上角开始平铺。

---

### 3. background-repeat

```css
.box {
  background-image: url("images/img1.jpg");
  background-repeat: no-repeat;
}
```

| 值 | 含义 |
|----|------|
| repeat | 默认，水平垂直平铺 |
| repeat-x | 水平平铺 |
| repeat-y | 垂直平铺 |
| no-repeat | 不平铺 |

---

### 4. background-size

```css
.box {
  background-size: 100% 100%;
}
```

| 值 | 含义 |
|----|------|
| length | 宽高值（如 100px 50px） |
| percentage | 相对于元素大小的百分比 |
| cover | 按比例放大覆盖整个容器（可能裁剪） |
| contain | 按比例缩放以完整显示（可能留白） |

> 常用：`cover` 保持比例并铺满容器。

---

### 5. background-position

```css
.box {
  background-position: center;
}
```

| 水平 | 垂直 |
|------|------|
| left / center / right | top / center / bottom |

默认值：`0% 0%`（左上角）。

---

## 六、文本属性（Text）

### 1. text-align

```css
h1 { text-align: center; }
h2 { text-align: left; }
h3 { text-align: right; }
```

---

### 2. text-decoration

```css
h1 { text-decoration: overline; }
h2 { text-decoration: line-through; }
h3 { text-decoration: underline; }
```

| 值 | 含义 |
|----|------|
| underline | 下划线 |
| overline | 上划线 |
| line-through | 删除线 |

---

### 3. text-transform

```css
p {
  text-transform: capitalize;
}
```

| 值 | 含义 |
|----|------|
| capitalize | 每个单词首字母大写 |
| uppercase | 全部大写 |
| lowercase | 全部小写 |

---

### 4. text-indent（首行缩进）

```css
p {
  text-indent: 2em;
}
```

> 可使用负值，表示左缩进。

---

 **总结**：  
掌握选择器优先级、字体与背景属性、文本装饰是 CSS 基础的核心。灵活使用类选择器与外部样式可提高代码复用与维护性。
