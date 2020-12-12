# day03

# 盒模型

### 基础选择器

- 通配符选择器

  - ```html
    * {
    	 width: 200px;
         height: 200px;
         background-color: yellow;
    }
    ```

  - 

- 标签选择器

  - ```html
    div {
    	 width: 200px;
         height: 200px;
         background-color: yellow;
    }
    ```

  - 

- class选择器

  - ```html
    .box {
    	background-color: red;
    }
    ```

  - 可以包含多个类选择器，用空格分开

- id选择器

  - ```html
    #div1 {
    	font-size:20px;
    }
    ```

  - 同一个文本唯一

- 优先级

  - id选择器>class选择器>标签选择器>通配符选择器*

### 文本字体属性

- #### css字体属性

  - font-size

    - 设置字体的大小，浏览器默认是16px, 最小设置不能小于12px (1px-11px跟12px的大小是一样的)

  - font-family

    - 设置文本的字体系列，如果属性值包含中文或者空格，要加引号，回退系统（备用字体），假如浏览器不支持第一个字体，第二个字体可以生效。
    - serif -- 衬线字体
      - 宋体（SimSun）
        - Windows 下大部分浏览器的默认中文字体，是为适应印刷术而出现的一种汉字字体。笔画有粗细变化，是一种衬线字体，宋体在小字号下的显示效果还可以接受，但是字号一大体验就很差了，所以使用的时候要注意，不建议做标题字体使用。
      - Times New Roman
        - Mac 平台 Safari 下默认的英文字体，是最常见且广为人知的西文衬线字体之一，众多网页浏览器和文字处理软件都是用它作为默认字体。
    - sans-serif -- 无衬线字体
      - 微软雅黑（Microsoft Yahei）
        - 大名鼎鼎的微软雅黑相信都不陌生，从 windows Vista 开始，微软提供了这款新的字体，一款无衬线的黑体类字体，显著提高了字体的显示效果。现在这款字体已经成为 windows 浏览器最值得使用的中文字体。
      - 华文黑体（STHeiti）、华文细黑（STXihei）
        - 属于同一字体家族系列，MAC OS X 10.6 之前的简体中文系统界面的默认中文字体，正常粗细就是华文细黑，粗体下则是华文黑体。
      - 黑体-简（Heiti SC）
        - 从 MAC OS X 10.6 开始，黑体-简代替华文黑体用作简体中文系统界面默认字体，苹果生态最常用的字体之一，包括 iPhone、iPad 等设备用的也是这款字体。
      - 冬青黑体（Hiragino Sans GB）
        - 又叫苹果丽黑，Hiragino 是字游工房设计的系列字体名称。是一款清新的专业印刷字体，小字号时足够清晰，Mac OS X 10.6 开始自带有 W3 和 W6 。
      - Helvetica
        - 被广泛用于全世界使用拉丁字母和西里尔字母的国家。Helvetica 是苹果电脑的默认字体，微软常用的Arial 字体也来自于它。
      - Arial
        - Windows 平台上默认的无衬线西文字体，有多种变体，比例及字重（weight）和 Helvetica 极为相近。
      - Verdana
        - 无衬线字体，优点在于它在小字上仍结构清晰端整、阅读辨识容易。
      - Tahoma
        - 十分常见的无衬线字体，字体结构和 Verdana 很相似，其字元间距较小，而且对 Unicode 字集的支持范围较大。许多不喜欢 Arial 字体的人常常会改用 Tahoma 来代替，除了是因为 Tahoma 很容易取得之外，也是因为 Tahoma 没有一些 Arial 为人诟病的缺点，例如大写“i”与小写“L”难以分辨等。（这里故意反过来写）。
    - monospace -- 等宽字体
      - Consolas
    - fantasy(梦幻)
    - cursive(草体)

  - font-style

    - 设置文字字体样式
      - normal 正常显示
      - italic 斜体显示

  - font-weight

    - 设置字体的粗细
      - lighter 细体 100
      - normal 默认，标准的字体 400
      - bold 粗体 700
      - bolder 粗体 900
      - 100-900

  - line-height

    - 设置行高

      - normal 默认，合理的行高
      - length 设置固定的行间距
      - number 设置数字，此数字与当前字体尺寸相乘的结果

    - 单行文本垂直居中

      - ```css
        .box {
                    width: 300px;
                    height: 200px;
                    background-color: red;
                    font-size: 30px;
                    /* 设置文本水平居中 */
                    text-align: center;
                    /* 设置行高和盒子高度一致，单行文本垂直居中 */
                    line-height: 200px;
                }
        ```

      - 

  - font: font-style font-weight font-size/line-height font-family

    - 注意：只有同时具有font-size和font-family的值时，简写才生效

- #### css文本属性

  - color
    - 设置文本的字体颜色
  - text-align
    - 设置文本的水平对齐方式，默认都是左对齐，相对于标签本身的宽度来对齐的
      - left 默认 多对齐
      - center 居中对齐
      - right 右对齐
      - justify 设置文本两端自动对齐
  - text-decoration
    - 设置文本的装饰
      - none 默认，没有装饰
      - underline  定义文本下的一条线
      - overline 定义文本上的一条线
      - line-through 定义贯穿文本的一条线
  - text-indent
    - 设置文本的首行缩进

### css长度单位和颜色表示

- #### css长度单位：	

  - px
    - 像素值，绝对长度单位
  - em
    - 相对长度单位，相对于当前元素本身的font-size
    - 如果作用于font-size, 那就相对于父标签的font-size
  - %
    - 百分比，相对于父标签
  - rem
    - 相对于根元素（html）的font-size, 一般作用于移动端

- #### css颜色表示 :  

  - 英文单词 (red blue green) 
  - 六位的十六进制数   #RRGGBB
    - 如果 #aabbcc  可以简写为 #abc
      - 可以设置为8位，最后两位代表透明度 (00 - ff)
  - rgb(r,g,b)
    - 三种整数 0 - 255
    - 三个百分比
    - rgba(r,g,b,alpha)
      - alpha 可是设置 0 到 1的小数 ，代表透明度



### 盒模型的概念

- 概念：css盒模型本质是一个盒子，封装周围的html标签，它包括：外边距，边框，填充（内边距）和实际内容
- 内容 content  :  
  - width:  设置宽度
  - height: 设置高度 
- 内边距（填充区域）padding ：
  - 单边内边距：padding-top  padding-bottom  padding-left padding-right
  - 简写 : 
    - 一个值：表示四个方向的内边距值。
    - 两个值：分别表示上下，左右的内边距值
    - 三个值：分别表示上，左右，下的内边距值
    - 四个值：分别表示上，右，下，左的内边距值
- 边框 border : 
  - border-width
  - border-style : 
    - none  定义无边框
    - dotted  定义点状边框
    - dashed  定义虚线边框
    - solid 定义实现边框
    - double 定义双线。双线的高度等于border-width的值
  - border-color
- border: 1px solid red;
- 外边距 margin : 
  - 单边外边距 ： margin-top margin-bottom margin-left margin-right
  - 简写：
    - 一个值：表示四个方向的外边距值。
    - 两个值：分别表示上下，左右的外边距值
    - 三个值：分别表示上，左右，下的外边距值
    - 四个值：分别表示上，右，下，左的外边距值
- 外边距传递和**塌陷**
  - 父子
    - 给父级设置边框或内边距
    - 给父级设置溢出隐藏 overflow:hidden,实际上是触发BFC
  - 兄弟
    - 给其中一个套一个父标签，设置overflow：hidden

### 实用小技巧

```html
	<style>
        .div1 {
            width: 100px;
            height: 100px;
            border-width: 50px;
            border-style: solid;
            border-color: red yellow green blue;
        }
        .div2 {
            width: 0;
            height: 0;
            border-width: 100px;
            border-style: solid;
            border-color: red yellow green blue;
        }
        .div3 {
            width: 0;
            height: 0;
            border-width: 200px 200px 0 0;
            border-style: solid;
            border-color: red yellow green;
        }
        .div4 {
            width: 0;
            height: 0;
            border-width: 100px;
            border-style: solid;
            border-color: red transparent transparent transparent;
        }
    </style>
	<div class="div1"></div>
    <div class="div2"></div>
    <div class="div3"></div>
    <div class="div4"></div>
```

- 

