# HTML5 Video(视频)

--------

很多站点都会使用到视频. HTML5 提供了展示视频的标准。

## 检测您的浏览器是否支持 HTML5 视频：

<script>
function checkVideo()
{
if(!!document.createElement('video').canPlayType)
  {
  var vidTest=document.createElement("video");
  oggTest=vidTest.canPlayType('video/ogg; codecs="theora, vorbis"');
  if (!oggTest)
    {
    h264Test=vidTest.canPlayType('video/mp4; codecs="avc1.42E01E, mp4a.40.2"');
    if (!h264Test)
      {
      document.getElementById("checkVideoResult").innerHTML="抱歉你的浏览器不支持HTML5 video标签！."
      }
    else
      {
      if (h264Test=="probably")
        {
        document.getElementById("checkVideoResult").innerHTML="非常棒！你的浏览器支持HTML5 video标签！";
        }
      else
        {
        document.getElementById("checkVideoResult").innerHTML="Meh. Some support.";
        }
      }
    }
  else
    {
    if (oggTest=="probably")
      {
      document.getElementById("checkVideoResult").innerHTML="非常棒！你的浏览器支持HTML5 video标签！";
      }
    else
      {
      document.getElementById("checkVideoResult").innerHTML="Meh. Some support.";
      }
    }
  }
else
  {
  document.getElementById("checkVideoResult").innerHTML="Sorry. No video support."
  }
}
</script>
<div id="checkVideoResult"><button onclick="checkVideo()">检测</button></div>

--------

## Web站点上的视频

直到现在，仍然不存在一项旨在网页上显示视频的标准。

今天，大多数视频是通过插件（比如 Flash）来显示的。然而，并非所有浏览器都拥有同样的插件。

HTML5 规定了一种通过 video 元素来包含视频的标准方法。

--------

## 浏览器支持

![Internet Explorer](images/compatible_ie.gif)![Firefox](images/compatible_firefox.gif)![Opera](images/compatible_opera.gif)![Google Chrome](images/compatible_chrome.gif)![Safari](images/compatible_safari.gif)

Internet Explorer 9+, Firefox, Opera, Chrome, 和 Safari 支持 &lt;video&gt; 元素.

**注意:**  Internet Explorer 8 或者更早的IE版本不支持 &lt;video&gt; 元素。

--------

## HTML5 (视频)- 如何工作

如需在 HTML5 中显示视频，您所有需要的是：

## 实例

```HTML
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
您的浏览器不支持Video标签。
</video>
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_video_all)

&lt;video&gt; 元素提供了 播放、暂停和音量控件来控制视频。

同时&lt;video&gt; 元素元素也提供了 width 和 height 属性控制视频的尺寸.如果设置的高度和宽度，所需的视频空间会在页面加载时保留。。如果没有设置这些属性，浏览器不知道大小的视频，浏览器就不能再加载时保留特定的空间，页面就会根据原始视频的大小而改变。

&lt;video&gt; 与&lt;/video&gt; 标签之间插入的内容是提供给不支持 video 元素的浏览器显示的。

&lt;video&gt; 元素支持多个 &lt;source&gt; 元素. &lt;source&gt; 元素可以链接不同的视频文件。浏览器将使用第一个可识别的格式：

--------

## 视频格式与浏览器的支持

当前， &lt;video&gt; 元素支持三种视频格式： MP4, WebM, 和 Ogg:

| 浏览器 | MP4 | WebM | Ogg |
| ---- | ---- | ---- | ---- |
| Internet Explorer | YES | NO | NO |
| Chrome | YES | YES | YES |
| Firefox | YES | YES | YES |
| Safari | YES | NO | NO |
| Opera | YES (从 Opera 25 起) | YES | YES |

 * MP4 = 带有 H.264 视频编码和 AAC 音频编码的 MPEG 4 文件
 * WebM = 带有 VP8 视频编码和 Vorbis 音频编码的 WebM 文件
 * Ogg = 带有 Theora 视频编码和 Vorbis 音频编码的 Ogg 文件

--------

## 视频格式

| 格式 | MIME-type |
| ---- | ---- |
| MP4 | video/mp4 |
| WebM | video/webm |
| Ogg | video/ogg |

--------

## HTML5 &lt;video&gt; - 使用 DOM 进行控制

HTML5 &lt;video&gt; 和 &lt;audio&gt; 元素同样拥有方法、属性和事件。

&lt;video&gt; 和 &lt;audio&gt;元素的方法、属性和事件可以使用JavaScript进行控制.

其中的方法有用于播放、暂停以及加载等。其中的属性（比如时长、音量等）可以被读取或设置。其中的 DOM 事件能够通知您，比方说，&lt;video&gt; 元素开始播放、已暂停，已停止，等等。

例中简单的方法，向我们演示了如何使用 &lt;video&gt; 元素，读取并设置属性，以及如何调用方法。

## 实例 1

为视频创建简单的播放/暂停以及调整尺寸控件：

<div style="text-align:center"> 
  <button onclick="playPause()">播放/暂停</button> 
  <button onclick="makeBig()">放大</button>
  <button onclick="makeSmall()">缩小</button>
  <button onclick="makeNormal()">普通</button>
  <br><br> 
  <video id="video1" width="480">
    <source src="/images/mov_bbb.mp4" type="video/mp4"><source src="/images/mov_bbb.ogg" type="video/ogg">你的浏览器不支持 HTML5 video.
  </video>
</div> 

<script> 
var myVideo=document.getElementById("video1"); 
function playPause()
{ 
if (myVideo.paused) 
  myVideo.play(); 
else 
  myVideo.pause(); 
} 
function makeBig()
{ 
myVideo.width=600; 
} 
function makeSmall()
{ 
myVideo.width=320; 
} 
function makeNormal()
{ 
myVideo.width=480; 
} 
</script> 

上面的例子调用了两个方法：play() 和 pause()。它同时使用了两个属性：paused 和 width。

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_video_js_prop)

更多参考请查看 [HTML5 Audio/Video DOM 参考手册](http://www.runoob.com/tags/html-audiovideo.html).

--------

## HTML5 Video 标签

| 标签 | 描述 |
| ---- | ---- |
| [&lt;video&gt;](http://www.runoob.com/tags/tag-video.html) | 定义一个视频 |
| [&lt;source&gt;](http://www.runoob.com/tags/tag-source.html) | 定义多种媒体资源,比如 &lt;video&gt; 和&lt;audio&gt; |
| [&lt;track&gt;](http://www.runoob.com/tags/tag-track.html) | 定义在媒体播放器文本轨迹 |
