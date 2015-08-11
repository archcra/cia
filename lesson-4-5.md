动画的原理，就是利用人的视觉暂留效应。以一定的频率（指定时间内重复的次数）来绘制不同的图，就可能产生动画效果。这里有一点要注意，画新的画时，要擦掉旧的画。我们来看看画是怎么擦的。


我们先来画一个矩形：

HTML:
```
<!-- 定义一块256*256像素大小的画布 -->
<canvas id="myCanvas" width="256" height="256"></canvas>
```

Javascript:
```
// 准备一块二维世界的画布
var canvas = document.getElementById("myCanvas");
var context = canvas.getContext("2d");

// 开始向画布上画
context.fillRect(50, 50, 100, 100);
```

这样便画出了一个矩形：

![](Selection_003.png)
让我们在最后加上一句： 
```
context.clearRect(0, 0, canvas.width, canvas.height);
```
然后看效果：
http://jsfiddle.net/archcra/qaaox7yL/9/

这里就给出示例图了，因为什么也没有。什么也没有是因为擦得太多了：把整个画布都擦干净了，所以什么也没有了。

我们修改一下最后一行：
```
context.clearRect(50, 50, 50, 50);
```
可以通过这里看效果：http://jsfiddle.net/archcra/qaaox7yL/10/
我们会看到矩形被擦掉了1/4，如下图所示：

![](Selection_004.png)


如果不断地重复擦与画的过程，就可能产生动画。



