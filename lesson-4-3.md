往返运行可以看作是一种振荡。振荡的一种直观现象，就象一个乒乓球飞入一个夹缝内，然后在两个面间快速振荡一样。在以往机械摆钟流行的时候，钟摆是一个常见的振荡现象；从物理学上来说，可以使用简谐振荡(simple harmonic oscillator)来模拟这种运行。
简谐振荡的公式是：
x(t) = amplitude * sin(t * 2PI / period) + x0

这里用到了sin函数；
sin是简写，全写是sine [saɪn] n. 正弦函数，三角函数之一
正弦函数用途很广，我们日常用的交流电的波形，就是正弦波。
它的定义如图：

![](Selection_002.png)

一个角，如上图中的 (读作alpha)的sin值，就是它的对边长度除以斜边长度。即a/h。


下面我们给出往返运运的示例，修改animate 函数即可：


代码如下：
```
 function animate(myRectangle, canvas, context, startTime) {
     // update
     var time = (new Date()).getTime() - startTime;
     var amplitude = 150;

     // in ms
     var period = 2000;
     var centerX = canvas.width / 2 - myRectangle.width / 2;
     var nextX = amplitude * Math.sin(time * 2 * Math.PI / period) + centerX;
     myRectangle.x = nextX;

     // clear
     context.clearRect(0, 0, canvas.width, canvas.height);

     // draw
     drawRectangle(myRectangle, context);

     // request new frame
     requestAnimFrame(function () {
         animate(myRectangle, canvas, context, startTime);
     });
 }
```


效果可参见：http://jsfiddle.net/archcra/cko20q88/12/





参考：https://en.wikipedia.org/wiki/Sine
