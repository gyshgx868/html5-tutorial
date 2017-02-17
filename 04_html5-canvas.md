# HTML5 Canvas

--------

&lt;canvas&gt; 标签定义图形，比如图表和其他图像，您必须使用脚本来绘制图形。

在画布上（Canvas）画一个红色矩形，渐变矩形，彩色矩形，和一些彩色的文字。

<canvas id="myCanvas" width="270" height="160" style="border:1px solid #c3c3c3;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
	var ctx=c.getContext("2d");
	ctx.fillStyle="#FF0000";
	ctx.fillRect(20,20,100,50);
	
	var grd=ctx.createLinearGradient(140,20,240,70);
    grd.addColorStop(0,"black");
    grd.addColorStop(1,"white");
    ctx.fillStyle=grd;
    ctx.fillRect(140,20,100,50);
    
    var grd2=ctx.createLinearGradient(20,90,120,90);
    grd2.addColorStop(0,"black");
    grd2.addColorStop("0.3","magenta");
    grd2.addColorStop("0.5","blue");
    grd2.addColorStop("0.6","green");
    grd2.addColorStop("0.8","yellow");
    grd2.addColorStop(1,"red");
    ctx.fillStyle=grd2;
    ctx.fillRect(20,90,100,50);
    
    ctx.font="30px Verdana";
    var grd3=ctx.createLinearGradient(140,20,240,90);
    grd3.addColorStop(0,"black");
    grd3.addColorStop("0.3","magenta");
    grd3.addColorStop("0.6","blue");
    grd3.addColorStop("0.8","green");
    grd3.addColorStop(1,"red");
    ctx.strokeStyle=grd3;
    ctx.strokeText("Smile!",140,120); 
	}
</script>

--------

## 什么是 Canvas?

HTML5 &lt;canvas&gt; 元素用于图形的绘制，通过脚本 (通常是JavaScript)来完成.

&lt;canvas&gt; 标签只是图形容器，您必须使用脚本来绘制图形。

你可以通过多种方法使用Canva绘制路径,盒、圆、字符以及添加图像。

--------

## 浏览器支持

表格中的数字表示支持 &lt;canvas&gt; 元素的第一个浏览器版本号。

| 元素 | ![Chrome](images/compatible_chrome.gif) | ![IE](images/compatible_ie.gif) | ![Firefox](images/compatible_firefox.gif) | ![Safari](images/compatible_safari.gif) | ![Opera](images/compatible_opera.gif) |
| ---- | ---- | ---- | ---- | ---- | ---- |
| &lt;canvas&gt; | 4.0 | 9.0 | 2.0 | 3.1 | 9.0 |

--------

## 创建一个画布（Canvas）

一个画布在网页中是一个矩形框，通过 &lt;canvas&gt; 元素来绘制.

**注意:**  默认情况下 &lt;canvas&gt; 元素没有边框和内容。

&lt;canvas&gt;简单实例如下:

```HTML
<canvas id="myCanvas" width="200" height="100"></canvas>
```

**注意:**  标签通常需要指定一个id属性 (脚本中经常引用), width 和 height 属性定义的画布的大小.

**提示:** 你可以在HTML页面中使用多个 &lt;canvas&gt; 元素.

使用 style 属性来添加边框:

## 实例

```HTML
<canvas id="myCanvas" width="200" height="100"
style="border:1px solid #000000;">
</canvas>
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_empty)

--------

## 使用 JavaScript 来绘制图像

canvas 元素本身是没有绘图能力的。所有的绘制工作必须在 JavaScript 内部完成：

## 实例

```JavaScript
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
ctx.fillStyle="#FF0000";
ctx.fillRect(0,0,150,75);
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_first)

**实例解析:**

首先，找到 &lt;canvas&gt; 元素:

```JavaScript
var c=document.getElementById("myCanvas");
```

然后，创建 context 对象：

```JavaScript
var ctx=c.getContext("2d");
```

getContext("2d") 对象是内建的 HTML5 对象，拥有多种绘制路径、矩形、圆形、字符以及添加图像的方法。

下面的两行代码绘制一个红色的矩形：

```JavaScript
ctx.fillStyle="#FF0000";
ctx.fillRect(0,0,150,75);
```

设置fillStyle属性可以是CSS颜色，渐变，或图案。fillStyle 默认设置是#000000（黑色）。

fillRect( _x,y,width,height_ ) 方法定义了矩形当前的填充方式。

--------

## Canvas 坐标

canvas 是一个二维网格。

canvas 的左上角坐标为 (0,0)

上面的 fillRect 方法拥有参数 (0,0,150,75)。

意思是：在画布上绘制 150x75 的矩形，从左上角开始 (0,0)。

**坐标实例**

如下图所示，画布的 X 和 Y 坐标用于在画布上对绘画进行定位。鼠标移动的矩形框上，显示定位坐标。

<div style="width:230px;height:20px;text-align:center;clear:both">X</div>
<div style="width:20px;padding-top:40px;float:left">Y</div>
<div style="width:402px;float:left">
<iframe src="/try/demo_source/tryhtml5_canvas_coordinates.htm" frameborder="0" style="border:0;overflow:hidden;width:400px;height:120px;"></iframe>
</div>

--------

## Canvas - 路径

在Canvas上画线，我们将使用以下两种方法：

 * moveTo( _x,y_ ) 定义线条开始坐标
 * lineTo( _x,y_ ) 定义线条结束坐标绘制线条我们必须使用到 "ink" 的方法，就像stroke().

## 实例

定义开始坐标(0,0), 和结束坐标 (200,100)。然后使用 stroke() 方法来绘制线条:

<canvas id="myCanvas2" width="200" height="100" style="border:1px solid #d3d3d3;background:#ffffff;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas2");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
	var ctx=c.getContext("2d");
	ctx.moveTo(0,0);
	ctx.lineTo(200,100);
	ctx.stroke();
	}
</script> 

JavaScript:

```JavaScript
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
ctx.moveTo(0,0);
ctx.lineTo(200,100);
ctx.stroke();
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_tut_path)

在canvas中绘制圆形, 我们将使用以下方法:

 * arc(x,y,r,start,stop)实际上我们在绘制圆形时使用了 "ink" 的方法, 比如 stroke() 或者 fill().

## 实例

使用 arc() 方法 绘制一个圆:

<canvas id="myCanvas3" width="200" height="100" style="border:1px solid #d3d3d3;background:#ffffff;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas3");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
	var ctx=c.getContext("2d");
	ctx.beginPath();
	ctx.arc(95,50,40,0,2*Math.PI);
	ctx.stroke();
	}
</script>

JavaScript:

```JavaScript
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
ctx.beginPath();
ctx.arc(95,50,40,0,2*Math.PI);
ctx.stroke();
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_tut_path2)

--------

## Canvas - 文本

使用 canvas 绘制文本，重要的属性和方法如下：

 * font - 定义字体
 * fillText( _text,x,y_ ) - 在 canvas 上绘制实心的文本
 * strokeText( _text,x,y_ ) - 在 canvas 上绘制空心的文本使用 fillText():

## 实例

使用 "Arial" 字体在画布上绘制一个高 30px 的文字（实心）：

<canvas id="myCanvas4" width="200" height="100" style="border:1px solid #d3d3d3;background:#ffffff;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas4");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
    var ctx=c.getContext("2d");
    ctx.font="30px Arial";
    ctx.fillText("Hello World",10,50);
	}
</script>

JavaScript:

```JavaScript
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
ctx.font="30px Arial";
ctx.fillText("Hello World",10,50);
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_tut_text)

使用 strokeText():

## 实例

使用 "Arial" 字体在画布上绘制一个高 30px 的文字（空心）：

<canvas id="myCanvas5" width="200" height="100" style="border:1px solid #d3d3d3;background:#ffffff;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas5");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
    var ctx=c.getContext("2d");
    ctx.font="30px Arial";
    ctx.strokeText("Hello World",10,50);
	}
</script>

JavaScript:

```HTML
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
ctx.font="30px Arial";
ctx.strokeText("Hello World",10,50);
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_tut_text2)

--------

## Canvas - 渐变

渐变可以填充在矩形, 圆形, 线条, 文本等等, 各种形状可以自己定义不同的颜色。

以下有两种不同的方式来设置Canvas渐变：

 * createLinearGradient( _x,y,x1,y1_ ) - 创建线条渐变
 * createRadialGradient( _x,y,r,x1,y1,r1_ ) - 创建一个径向/圆渐变当我们使用渐变对象，必须使用两种或两种以上的停止颜色。

addColorStop()方法指定颜色停止，参数使用坐标来描述，可以是0至1.

使用渐变，设置fillStyle或strokeStyle的值为 渐变，然后绘制形状，如矩形，文本，或一条线。

使用 createLinearGradient():

## 实例

创建一个线性渐变。使用渐变填充矩形:

<canvas id="myCanvas6" width="200" height="100" style="border:1px solid #d3d3d3;background:#ffffff;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas6");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
    var ctx=c.getContext("2d");
    var grd=ctx.createLinearGradient(0,0,200,0);
    grd.addColorStop(0,"red");
    grd.addColorStop(1,"white");
    ctx.fillStyle=grd;
    ctx.fillRect(10,10,150,80);
	}
</script>

JavaScript:

```JavaScript
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
// 创建渐变
var grd=ctx.createLinearGradient(0,0,200,0);
grd.addColorStop(0,"red");
grd.addColorStop(1,"white");
// 填充渐变
ctx.fillStyle=grd;
ctx.fillRect(10,10,150,80);
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_tut_grad)

使用 createRadialGradient():

## 实例

创建一个径向/圆渐变。使用渐变填充矩形：

<canvas id="myCanvas7" width="200" height="100" style="border:1px solid #d3d3d3;background:#ffffff;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas7");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
    var ctx=c.getContext("2d");
    // Create gradient
    var grd=ctx.createRadialGradient(75,50,5,90,60,100);
    grd.addColorStop(0,"red");
    grd.addColorStop(1,"white");
    // Fill with gradient
    ctx.fillStyle=grd;
    ctx.fillRect(10,10,150,80);
	}
</script>

JavaScript:

```JavaScript
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
// 创建渐变
var grd=ctx.createRadialGradient(75,50,5,90,60,100);
grd.addColorStop(0,"red");
grd.addColorStop(1,"white");
// 填充渐变
ctx.fillStyle=grd;
ctx.fillRect(10,10,150,80);
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_tut_grad2)

--------

## Canvas - 图像

把一幅图像放置到画布上, 使用以下方法:

 * drawImage( _image,x,y_ )## 使用图像:

<img id="scream" src="/images/img_the_scream.jpg" alt="The Scream">

## 实例

把一幅图像放置到画布上:

<canvas id="myCanvas8" width="250" height="300" style="border:1px solid #d3d3d3;background:#ffffff;">
你的浏览器不支持 HTML5 的 &lt;canvas&gt; 元素.
</canvas>
<script>
var c=document.getElementById("myCanvas8");
var canvOK=1;
try {c.getContext("2d");}
catch (er) {canvOK=0;}
if (canvOK==1)
	{
    var ctx=c.getContext("2d");
    var img=document.getElementById("scream");
    ctx.drawImage(img,10,10);
	}
</script>

JavaScript:

```JavaScript
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
var img=document.getElementById("scream");
ctx.drawImage(img,10,10);
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_canvas_tut_img)

--------

## HTML Canvas 参考手册

标签的完整属性可以参考[Canvas 参考手册.](http://www.runoob.com/tags/ref-canvas.html)

## HTML &lt;canvas&gt; 标签

| Tag | 描述 |
| ---- | ---- |
| [&lt;canvas&gt;](http://www.runoob.com/tags/tag-canvas.html) | HTML5 的 canvas 元素使用 JavaScript 在网页上绘制图像。 |
