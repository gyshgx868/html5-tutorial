# HTML5 MathML

HTML5 可以在文档中使用 MathML 元素，对应的标签是 &lt;math&gt;...&lt;/math&gt; 。

MathML 是数学标记语言，是一种基于XML（标准通用标记语言的子集）的标准，用来在互联网上书写数学符号和公式的置标语言。

> **注意：** 大部分浏览器都支持 MathML 标签，如果你的浏览器不支持该标签，可以使用最新版的 Firefox 或 Safari 浏览器查看。

--------

## MathML 实例

以下是一个简单的 MathML 实例：

```HTML
<!DOCTYPE html>
<html>
   <head>
      <meta charset="UTF-8">
      <title>菜鸟教程(runoob.com)</title>
   </head>
	
   <body>
	
      <math xmlns="http://www.w3.org/1998/Math/MathML">
		
         <mrow>
            <msup><mi>a</mi><mn>2</mn></msup>
            <mo>+</mo>
				
            <msup><mi>b</mi><mn>2</mn></msup>
            <mo>=</mo>
				
            <msup><mi>c</mi><mn>2</mn></msup>
         </mrow>
			
      </math>
		
   </body>
</html> 
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_mathml)

运行结果图，如下所示：

![](images/mathml1.jpg)

以下实例添加了一些运算符：

```HTML
<!DOCTYPE html>
<html>
   <head>
      <meta charset="UTF-8">
      <title>菜鸟教程(runoob.com)</title>
   </head>
	
   <body>
	
      <math xmlns="http://www.w3.org/1998/Math/MathML">
		
         <mrow>			
            <mrow>
				
               <msup>
                  <mi>x</mi>
                  <mn>2</mn>
               </msup>
					
               <mo>+</mo>
					
               <mrow>
                  <mn>4</mn>
                  <mo>⁢</mo>
                  <mi>x</mi>
               </mrow>
					
               <mo>+</mo>
               <mn>4</mn>
					
            </mrow>
				
            <mo>=</mo>
            <mn>0</mn>
				 
         </mrow>
      </math>
		
   </body>
</html> 
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_mathml1)

运行结果图，如下所示：

![](images/mathml2-1.jpg)

以下实例是一个 2×2 矩阵，可以在 Firefox 3.5 以上版本查看到效果：

```HTML
<!DOCTYPE html>
<html>
   <head>
      <meta charset="UTF-8">
      <title>菜鸟教程(runoob.com)</title>
   </head>
	
   <body>
      <math xmlns="http://www.w3.org/1998/Math/MathML">
		
         <mrow>
            <mi>A</mi>
            <mo>=</mo>
			
            <mfenced open="[" close="]">
			
               <mtable>
                  <mtr>
                     <mtd><mi>x</mi></mtd>
                     <mtd><mi>y</mi></mtd>
                  </mtr>
					
                  <mtr>
                     <mtd><mi>z</mi></mtd>
                     <mtd><mi>w</mi></mtd>
                  </mtr>
               </mtable>
               
            </mfenced>
         </mrow>
      </math>
      
   </body>
</html> 
```

[尝试一下 »](http://www.runoob.com/try/try.php?filename=tryhtml5_mathml2)

运行结果图，如下所示：

![](images/mathml3.jpg)
