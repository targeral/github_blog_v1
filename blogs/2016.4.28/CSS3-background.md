# CSS3之Background属性
## CSS3
### 2016.4.28

* **CSS3-Background属性简介**

background是一个使用频率很高的属性，也是十分有用的属性。能帮助设计师实现一些特殊的效果，使用起来也非常简单。

* **背景的基本属性**

背景主要包括五个属性:
    * background-color(背景颜色)
    * background-image(背景图片)
    * background-repeat(背景图片展示方式)
    * background-attachment(背景图片是固定还是滚动)
    * backgound-position(背景图片位置)

这些属性可以单独写，也可以串在一起用。

```css
background:<background-color>] [,<background-image>] [,<background-repeat>] [,<background-attachment>] [,<background-position>]
```

1. background-color属性

语法: ``background-color:transparent || <color>``

用来设置元素的背景颜色，其默认值为"transparent",不设置任何颜色情况下是透明颜色，``<color>``用来设计背景颜色，常用的
颜色格式如下:
    * 颜色名:如“red”;
    * rgb色:如rgb(255, 0, 0)或rgb(100%, 0%, 0%);
    * hls值:如hls(0, 100%, 50%);
    * 十六进制值:如#ff0000
    * rgba色,如rgba(255, 0, 0, 0.3),
    * 可以使用hsla值,如hsla(0, 100%, 50%, 0.5).

2. background-image属性

语法: ``background-image:none || <url>``

用来设置元素的背景图片，默认为none，``<url>``是指背景图片的地址，这个地址是可以是*相对地址*，也可以是*绝对地址*。

3. background-repeat属性

语法: ``background-repeat: repeat || repeat-x || repeat-y || no-repeat``

用来设置元素背景图片在元素的盒模型中的铺放方式，默认为"repeat",也就是背景图片沿元素的x，y轴同时平铺，"repeat-x"表示的是元素的背景图片沿元素的x轴平铺，y轴不进行任何铺放；"repeat-y"刚好相反。"no-repeat"和默认值"repeat"相反，表示背景图片不做任何铺放。

4. background-attachment属性

语法: ``background-attachment: scroll || fixed``

用来设置元素背景图片是否固定或者随页面的其余部分滚动，其默认值为"scroll",表示背景图片会随浏览器滚动条一起滚动，而取值
"fixed"时，背景图片固定不动。

**注意:**background-attachment取值为fixed时，一般运用在html或者body标签上，使用在其他标签上不能达到固定效果。

5. background-position属性

语法: ``background-position:<percentage> || <length> || [left | center | right] [,top | center | bottom]``

用来设置元素背景图片的位置，其默认值为(0,0) || (0%,0%) || (left top),其值可以是具体的百分数或者数值设置(可以是负值),也可以使用关键字left, center, right, top, bottom配合设置。

* **与背景相关的新增属性**

    * background-origin:指定绘制背景图片的起点
    * background-clip:指定背景图片的显示范围
    * background-size:指定背景图片的尺寸大小
    * background-break:指定内联元素的背景图片进行平铺时的循环方式

1. background-origin属性

background-origin属性主要是用来决定background-position属性的参考原点，即决定背景图片定位的起点。在默认情况下，背景图
的background-position属性总是以元素左上角为原点对背景图片进行定位。CSS3的background-origin属性将打破这一格局，可以根据
自己的需要来改变背景图片的background-position起始位置。

基本语法: ``background-origin:padding-box || border-box || content-box``

    * padding-box:默认值，决定background-position起始位置从padding的外边缘(border的内边缘)开始显示背景图片
    * border-box:决定background-position起始位置从border的外边缘开始显示背景图片。
    * content-box:决定background-position起始位置从content的外边缘(padding的内边缘)开始显示背景图片。

具体例子参考:[Example](http://www.w3school.com.cn/tiy/c.asp?f=css_background-origin)

*兼容性*

为了保证只要支持background-origin属性的浏览器都能正常运行，需要使用各浏览器各自的前缀:

   * 前缀   浏览器内核
   * -moz- (Mozilla Gecko)
   * -webkit- (Webkit)
   * -o- (Presto)
   * -ms- (Internet Explorer)

2. background-clip

background-clip属性用来定义背景图片的裁剪区域。

基本语法: ``background-clip:border-box || padding-box || content-box``

  * padding-box(背景延伸到padding的外边缘,但不会超过边框的范围)
  * border-box(背景图片在边框下，这个是background-clip的默认值)
  * content-box(背景仅在内容区域绘制，不会超过padding和边框的范围)

[Example](http://www.w3school.com.cn/tiy/t.asp?f=css3_background-clip)

3. background-size

background-size属性用来指定背景图片的尺寸，可以控制背景图片在水平和垂直两个方向的缩放。

基本语法: ``background-size:auto || <length> || <percentage> || cover || contain``

 * auto:默认值，将保持背景图片的原始高度和宽度
 * <length>:取具体的整数值(例如px值),将改变背景图片的大小
 * <percentage>:取值为百分比，可以是0%~100%。此时，同样能改变背景图片的大小。但此值相对于元素的宽度来进行计算，并不根据图片的宽度来进行计算。
 * cover:将背景图片放大，以适应铺满整个容器。但这种方法会导致背景图片失真。
 * contain:保持背景图片本身的宽高比，将背景图片缩放到宽度或者高度正好适应所定义背景容器的区域。

[Example](http://www.w3school.com.cn/tiy/t.asp?f=css3_background-size)