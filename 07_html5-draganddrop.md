# HTML5 拖放（Drag 和 Drop）

--------

拖放（Drag 和 drop）是 HTML5 标准的组成部分。

--------

<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)">
<img src="/images/img_w3slogo.gif" draggable="true" ondragstart="drag(event)" width="100" height="35" id="drag1"></div>
<div id="div2" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

将w3cschool图标拖动到矩形框中。

--------

## 拖放

拖放是一种常见的特性，即抓取对象以后拖到另一个位置。

在 HTML5 中，拖放是标准的一部分，任何元素都能够拖放。

--------

## 浏览器支持

![Internet Explorer](images/compatible_ie.gif)![Firefox](images/compatible_firefox.gif)![Opera](images/compatible_opera.gif)![Google Chrome](images/compatible_chrome.gif)![Safari](images/compatible_safari.gif)

Internet Explorer 9+, Firefox, Opera, Chrome, 和 Safari 支持拖动。

**注意:** Safari 5.1.2不支持拖动.

--------

## HTML5 拖放实例

下面的例子是一个简单的拖放实例：

## 实例

```HTML
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title>
<style type="text/css">
#div1 {width:350px;height:70px;padding:10px;border:1px solid #aaaaaa;}
</style>
<script>
function allowDrop(ev)
{
    ev.preventDefault();
}

function drag(ev)
{
    ev.dataTransfer.setData("Text",ev.target.id);
}

function drop(ev)
{
    ev.preventDefault();
    var data=ev.dataTransfer.getData("Text");
    ev.target.appendChild(document.getElementById(data));
}
</script>
</head>
<body>

<p>拖动 W3CSchool.cc 图片到矩形框中:</p>

<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>
<br>
<img id="drag1" src="/images/logo.png" draggable="true" ondragstart="drag(event)" width="336" height="69">

</body>
</html>
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_draganddrop)

它看上去也许有些复杂，不过我们可以分别研究拖放事件的不同部分。

--------

## 设置元素为可拖放

首先，为了使元素可拖动，把 draggable 属性设置为 true ：

```HTML
<img draggable="true">
```

--------

## 拖动什么 - ondragstart 和 setData()

然后，规定当元素被拖动时，会发生什么。

在上面的例子中，ondragstart 属性调用了一个函数，drag(event)，它规定了被拖动的数据。

dataTransfer.setData() 方法设置被拖数据的数据类型和值：

```JavaScript
function drag(ev)
{
    ev.dataTransfer.setData("Text",ev.target.id);
}
```

在这个例子中，数据类型是 "Text"，值是可拖动元素的 id ("drag1")。

--------

## 放到何处 - ondragover

ondragover 事件规定在何处放置被拖动的数据。

默认地，无法将数据/元素放置到其他元素中。如果需要设置允许放置，我们必须阻止对元素的默认处理方式。

这要通过调用 ondragover 事件的 event.preventDefault() 方法：

```HTML
event.preventDefault()
```

--------

## 进行放置 - ondrop

当放置被拖数据时，会发生 drop 事件。

在上面的例子中，ondrop 属性调用了一个函数，drop(event)：

```JavaScript
function drop(ev)
{
    ev.preventDefault();
    var data=ev.dataTransfer.getData("Text");
    ev.target.appendChild(document.getElementById(data));
}
```

代码解释：

 * 调用 preventDefault() 来避免浏览器对数据的默认处理（drop 事件的默认行为是以链接形式打开）
 * 通过 dataTransfer.getData("Text") 方法获得被拖的数据。该方法将返回在 setData() 方法中设置为相同类型的任何数据。
 * 被拖数据是被拖元素的 id ("drag1")
 * 把被拖元素追加到放置元素（目标元素）中

--------

## ![Examples](images/tryitimg.gif) 更多实例

[来回拖放图片](http://www.runoob.com/try/try.php?filename=tryhtml5_draganddrop2)

 如何在两个 &lt;div&gt; 元素之间拖放图像。
