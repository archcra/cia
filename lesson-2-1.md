直线是很简单的形状
关于context的代码，使用下面的内容：
```
context.beginPath();
context.moveTo(0, 0);
context.lineTo(256, 256);
context.stroke();
```

我们会看到这样的效果：

![](Screen Shot 2015-08-09 at 11.39.32 AM.png)

这条线太细了，我们让它粗一点。在最后一句前，加上这句话：
```
context.lineWidth = 16;
```
结果就是这样：

![](Screen Shot 2015-08-09 at 12.20.29 PM.png)


线的颜色和我们说过的文字的颜色道理是一样的。在最后一句前加上：

