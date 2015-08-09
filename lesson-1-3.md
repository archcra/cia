我们的文字还没有颜色，我们给上用一下蓝色试试：


```
ctx.fillStyle = 'blue'
```

完整的Javascript象下面这样：
```
var canvas = document.getElementById("myCanvas");
var context = canvas.getContext("2d");
context.font = '32pt Arial';
context.fillStyle = 'blue';
context.fillText('Hello World!', 10, 64);
```

我们会看到下面的效果：

![](Screen Shot 2015-08-09 at 9.49.58 AM.png)


都有哪些颜色可以用呢？这里有一个列表：

