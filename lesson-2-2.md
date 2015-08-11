下面的语句，就可以画一个正方形：

```
context.strokeRect(50, 50, 100, 100);
```
![](Screen Shot 2015-08-11 at 2.43.38 PM.png)


我们把strokeRect换成fillRect，可以画一个实心的矩形：

```
context.fillRect(50, 50, 100, 100);
```

样子如下：
![](Screen Shot 2015-08-11 at 2.36.51 PM.png)

当然这一点也不好看，我们可以给它点颜色：

加上这一句：
```
context.fillStyle = 'blue';
```
完整的代码是：
```
// 准备一块二维世界的画布
var canvas = document.getElementById("myCanvas");
var context = canvas.getContext("2d");

// 开始向画布上画
context.fillStyle = 'blue';
context.fillRect(50, 50, 100, 100);
```
我们就会看到颜色变了：

![](Screen Shot 2015-08-11 at 2.41.32 PM.png)




