# HTML5 Audio(音频)

--------

HTML5 提供了播放音频文件的标准。

--------

## 互联网上的音频

直到现在，仍然不存在一项旨在网页上播放音频的标准。

今天，大多数音频是通过插件（比如 Flash）来播放的。然而，并非所有浏览器都拥有同样的插件。

HTML5 规定了在网页上嵌入音频元素的标准，即使用 &lt;audio&gt; 元素。

--------

## 浏览器支持

![Internet Explorer](images/compatible_ie.gif)![Firefox](images/compatible_firefox.gif)![Opera](images/compatible_opera.gif)![Google Chrome](images/compatible_chrome.gif)![Safari](images/compatible_safari.gif)

Internet Explorer 9+, Firefox, Opera, Chrome, 和 Safari 都支持 &lt;audio&gt; 元素.

**注意:**  Internet Explorer 8 及更早IE版本不支持 &lt;audio&gt; 元素.

--------

## HTML5 Audio - 如何工作

如需在 HTML5 中播放音频，你需要使用以下代码：

## 实例

```HTML
<audio controls>
    <source src="horse.ogg" type="audio/ogg">
    <source src="horse.mp3" type="audio/mpeg">
您的浏览器不支持 audio 元素。
</audio>
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_audio_all)

control 属性供添加播放、暂停和音量控件。

在&lt;audio&gt; 与 &lt;/audio&gt; 之间你需要插入浏览器不支持的&lt;audio&gt;元素的提示文本 。

&lt;audio&gt; 元素允许使用多个 &lt;source&gt; 元素. &lt;source&gt; 元素可以链接不同的音频文件，浏览器将使用第一个支持的音频文件

--------

## 音频格式及浏览器支持

目前, &lt;audio&gt;元素支持三种音频格式文件: MP3, Wav, 和 Ogg:

| 浏览器 | MP3 | Wav | Ogg |
| ---- | ---- | ---- | ---- |
| Internet Explorer 9+ | YES | NO | NO |
| Chrome 6+ | YES | YES | YES |
| Firefox 3.6+ | YES | YES | YES |
| Safari 5+ | YES | YES | NO |
| Opera 10+ | YES | YES | YES |

--------

## 音频格式的MIME类型

| Format | MIME-type |
| ---- | ---- |
| MP3 | audio/mpeg |
| Ogg | audio/ogg |
| Wav | audio/wav |

--------

## HTML5 Audio 标签

| 标签 | 描述 |
| ---- | ---- |
| [&lt;audio&gt;](http://www.runoob.com/tags/tag-audio.html) | 定义了声音内容 |
| [&lt;source&gt;](http://www.runoob.com/tags/tag-source.html) | 规定了多媒体资源, 可以是多个，在 &lt;video&gt; 与 &lt;audio&gt;标签中使用 |
