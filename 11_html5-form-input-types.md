## HTML5 新的 Input 类型

HTML5 拥有多个新的表单输入类型。这些新特性提供了更好的输入控制和验证。

本章全面介绍这些新的输入类型：

 * color
 * date
 * datetime
 * datetime-local
 * email
 * month
 * number
 * range
 * search
 * tel
 * time
 * url
 * week

**注意:** 并不是所有的主流浏览器都支持新的input类型，不过您已经可以在所有主流的浏览器中使用它们了。即使不被支持，仍然可以显示为常规的文本域。

--------

## Input 类型: color

color 类型用在input字段主要用于选取颜色，如下所示：

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/incompatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

从拾色器中选择一个颜色:

```HTML
选择你喜欢的颜色: <input type="color" name="favcolor">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_color)

--------

## Input 类型: date

date 类型允许你从一个日期选择器选择一个日期。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义一个时间控制器:

```HTML
生日: <input type="date" name="bday">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_date)

--------

## Input 类型: datetime

datetime 类型允许你选择一个日期（UTC 时间）。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/incompatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义一个日期和时间控制器（本地时间）:

```HTML
生日 (日期和时间): <input type="datetime" name="bdaytime">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_datetime)

--------

## Input 类型: datetime-local

datetime-local 类型允许你选择一个日期和时间 (无时区).

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义一个日期和时间 (无时区):

```HTML
生日 (日期和时间): <input type="datetime-local" name="bdaytime">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_datetime-local)

--------

## Input 类型: email

email 类型用于应该包含 e-mail 地址的输入域。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/incompatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/compatible_firefox2020.gif)![Internet Explorer](images/compatible_ie2020.gif)

在提交表单时，会自动验证 email 域的值是否合法有效:

```HTML
E-mail: <input type="email" name="email">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_email)

**提示:**  iPhone 中的 Safari 浏览器支持 email 输入类型，并通过改变触摸屏键盘来配合它（添加 @ 和 .com 选项）。

--------

## Input 类型: month

month 类型允许你选择一个月份。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义月与年 (无时区):

```HTML
生日 (月和年): <input type="month" name="bdaymonth">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_month)

--------

## Input 类型: number

number 类型用于应该包含数值的输入域。

您还能够设定对所接受的数字的限定：

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/compatible_ie2020.gif)

定义一个数值输入域(限定):

```HTML
数量 ( 1 到 5 之间 ): <input type="number" name="quantity" min="1" max="5">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_number)

使用下面的属性来规定对数字类型的限定：

| 属性 | 描述 |
| ---- | ---- |
| disabled | 规定输入字段是禁用的 |
| max | 规定允许的最大值 |
| maxlength | 规定输入字段的最大字符长度 |
| min | 规定允许的最小值 |
| pattern | 规定用于验证输入字段的模式 |
| readonly | 规定输入字段的值无法修改 |
| required | 规定输入字段的值是必需的 |
| size | 规定输入字段中的可见字符数 |
| step | 规定输入字段的的合法数字间隔 |
| value | 规定输入字段的默认值 |

尝试一下带有所有限定属性的例子 [尝试一下 ](http://www.runoob.com/try/try.php?filename=tryhtml5_form_number_adv)

--------

## Input 类型: range

range 类型用于应该包含一定范围内数字值的输入域。

range 类型显示为滑动条。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/compatible_ie2020.gif)

定义一个不需要非常精确的数值（类似于滑块控制）:

```HTML
<input type="range" name="points" min="1" max="10">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_range)

请使用下面的属性来规定对数字类型的限定：

 * max - 规定允许的最大值
 * min - 规定允许的最小值
 * step - 规定合法的数字间隔
 * value - 规定默认值

--------

## Input 类型: search

search 类型用于搜索域，比如站点搜索或 Google 搜索。

## 实例

![Opera](images/incompatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义一个搜索字段 (类似站点搜索或者Google搜索):

```HTML
Search Google: <input type="search" name="googlesearch">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_search)

--------

## Input 类型: tel

## 实例

![Opera](images/incompatible_opera2020.gif)![Safari](images/incompatible_safari2020.gif)![Chrome](images/incompatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义输入电话号码字段:

```HTML
电话号码: <input type="tel" name="usrtel">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_tel)

--------

## Input 类型: time

time 类型允许你选择一个时间。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义可输入时间控制器（无时区）：

```HTML
选择时间: <input type="time" name="usr_time">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_time)

--------

## Input 类型: url

url 类型用于应该包含 URL 地址的输入域。

在提交表单时，会自动验证 url 域的值。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/incompatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/compatible_firefox2020.gif)![Internet Explorer](images/compatible_ie2020.gif)

定义输入URL字段:

```HTML
添加您的主页: <input type="url" name="homepage">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_url)

**提示:**  iPhone 中的 Safari 浏览器支持 url 输入类型，并通过改变触摸屏键盘来配合它（添加 .com 选项）。

--------

## Input 类型: week

week 类型允许你选择周和年。

## 实例

![Opera](images/compatible_opera2020.gif)![Safari](images/compatible_safari2020.gif)![Chrome](images/compatible_chrome2020.gif)![Firefox](images/incompatible_firefox2020.gif)![Internet Explorer](images/incompatible_ie2020.gif)

定义周和年 (无时区):

```HTML
选择周: <input type="week" name="week_year">
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_input_type_week)

--------

## HTML5 &lt;input&gt; 标签

| 标签 | 描述 |
| ---- | ---- |
| [&lt;input&gt;](http://www.runoob.com/tags/tag-input.html) | 描述input输入器 |
