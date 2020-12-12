# day04

- max-width和min-width:
  - 用来设置元素的最大宽度和最小宽度
- max-height和min-height:
  - 用来设置元素的最大高度和最小高度

### 圆角属性

+ ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
      <style>
          .box1 {
              width: 300px;
              height: 300px;
              background-color: red;
              /* 
                  圆角属性
               */
              /* border-radius: 30px; */
              /* border-radius: 10px 20px 30px 40px; */
              /* 
                  如果设置为50%，会变成一个圆形，椭圆还是正圆根据宽高来控制
               */
              border-radius: 50%;
          }
          /* 半圆 */
          .box2 {
              width: 400px;
              height: 200px;
              background-color: blue;
              border-radius: 200px 200px 0 0;
          }
          /* 四分之一圆 */
          .box3 {
              width: 300px;
              height: 300px;
              background-color: deeppink;
              border-radius: 300px 0 0 0;
          }
      </style>
  </head>
  <body>
      <div class="box1"></div>
      <div class="box2"></div>
      <div class="box3"></div>
  </body>
  </html>
  ```

+ 

### 背景属性

- ```css
   .box {
              width: 100%;
              height: 500px;
              /* 背景颜色 */
              background-color: red;
              /* 背景图片 */
              background-image: url(https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3547703274,3363083080&fm=11&gp=0.jpg);
              /* 
                  是否重复
                  默认是repeat重复，可以设置为no-repeat不重复
               */
              background-repeat: no-repeat;
              /* 设置背景图片的尺寸: 第一个值代表宽度 第二个值代表高度 */
              background-size: 200px 300px;
              /* 
                  背景图片定位
                      1.固定的像素值
                      2.百分比
                      3.方向的英文单词(center/left/right/top/bottom)
               */
              /* background-position: 100% 100%; */
              background-position: right bottom;
          }
  ```

- background-color : red 

- background-image: url(./img/bg.jpg)

- background-repeat: no-repeat

- background-size: 50% 50%

- background-position: 50% 50%

- background:red url(./img/bg.jpg) no-repeat top

### 选择器进阶

- 群组选择器

  - ```css
  /* 
                群组选择器
                    多个选择器组合到一起用逗号分隔
             */
            .box,h3,p,span {
                color: gold;
            }
  ```
    
  - 

- 交集选择器

  - ```css
    /* 
                交集选择器
                    用两个或者两个以上条件寻找
                    即有div又有.box1类名
             */
            div.box1 {
                color: deeppink;
            }
    ```

  - 

- 子代选择器

  - ```css
  /* 
                子代选择器
             */
            .wrap>.box {
                color: blue;
            }
  ```
    
  - 

- 后代选择器

  - ```css
  /* 后代选择器 */
            .wrap .box {
                color: gold;
            }
    ```
    
  - 

- 伪类链接选择器

  - :link 未访问状态
  - :visited 已访问状态
  - :hover 鼠标悬停状态
  - :active 鼠标点击那一刻

### css三大特性

+ 层叠性
  + 样式冲突就近原则，也就是后引入生效
  + 样式不冲突的代码不会受影响

+ 继承性
  
  + 子标签继承父标签的样式
    + 文本字体属性都会继承，text-, line- ,font-, color
  
+ 优先级

  + | 选择器类型           | 权值 |
    | -------------------- | ---- |
    | 通配符选择器         | 0    |
    | 标签选择器           | 1    |
    | 类选择器，伪类选择器 | 10   |
    | ID选择器             | 100  |

  + 复合选择器的权值计算方式：组成其所有单一选择器的权值之和  ul>li .red  1+1+10=12

  + 行内样式优先

    + 权值1000

  + ！important  无限权重
  
  + 继承样式的权值为最低，甚至比通配符选择器还低

### 标签显示模式特点与转换

- 标签的嵌套规则
  - h标签和p标签只能嵌套其他行内标签或者文字
  - h标签和p标签不能嵌套其他块级标签
  - a标签属于行内标签，但是比较特殊，可以嵌套任何标签，除了a标签
  - 其他行内标签只能嵌套文字，或者行内标签 
  - ul和ol子标签必须是li
- 块级标签
  - div h1-h6 p ul li ol li dl dt dd
  - 总是从新行开始
  - 高度、行高、外边距以及内边距都可以控制
  - 宽度默认是容器的100%
  - 可以容纳内联标签和其他块级标签
- 行内标签
  - strong b em i ins u del s span
  - 和相邻行内标签在一行上
  - 高、宽无效，但水平方向的padding和margin可以设置，垂直方向的无效
  - 默认宽度就是它本身内容的宽度
  - 行内标签只能容纳文本或者其他行内标签
- 行内块标签
  - img input td
  - 和相邻的行内标签在一行，但之间会有白色缝隙
  - 默认宽度就是它本身内容的宽度
  - 高度、行高、外边距以及内边距都可以控制
- 标签显示模式转换 display
  - 块转行内：display : inline;
  - 行内转块 ： display : block;
  - 块、行内转行内块 ： display : inline-block;

### 外边距传递和塌陷

- 给父级设置边框或内边距
- 给父标签添加overflow:hidden属性，触发BFC

### 盒子居中技巧

+ ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Document</title>
      <style>
          * {
              padding: 0;
              margin: 0;
          }
          .box {
              width: 300px;
              height: 300px;
              background-color: red;
              text-align: center;
              line-height: 300px;
          }
          .box span {
              background-color: blue;
          }
  
          .wrap {
              width: 400px;
              height: 400px;
              background-color: gold;
              overflow: hidden;
          }
          .box1 {
              width: 200px;
              height: 200px;
              background-color: green;
              margin: 100px auto;
          }
      </style>
  </head>
  <body>
      <div class="box">
          <span>hello world</span>
      </div>
      <div class="wrap">
          <div class="box1"></div>
      </div>
  </body>
  </html>
  ```

+ 

