加速度按字面来理解，就是速度会变得越来越快。如果不考虑阻力，那么东西从天上落下来，就会处于加速度状态。由于这个加速度是由重力引起的，所以叫重力加速度。实际上，速度变得越来越慢也是一种加速度，只不过叫负加速度。


加速度的公式是这样的：
distance = velocity * time + 1/2 * acceleration * time ^2

距离 = 初始速度 * 时间  + 加速度乘以时间的平方再除以2

我们修改一下animate函数：
```
 function animate(myRectangle, canvas, context, startTime) {
     // update
     var time = (new Date()).getTime() - startTime;

     var linearSpeed = 80;
     var acceleration = 500;
     // pixels / second
     time = time / 1000; // convert to seconds
     var newX = linearSpeed * time + acceleration * Math.pow(time, 2) / 2;
     myRectangle.x = newX;

     // clear
     context.clearRect(0, 0, canvas.width, canvas.height);

     drawRectangle(myRectangle, context);

     // request new frame
     requestAnimFrame(function () {
         animate(myRectangle, canvas, context, startTime);
     });
 }
 ```
大家可以修改这两个变量的值：
```
var linearSpeed = 80;
var acceleration = 500;
```
以观察一下效果。

水平移动效果不直观，我们来看看重力加速度。
下面是代码是没有重力加速度的情况：

```
 function animate(myRectangle, canvas, context, startTime) {
     // update
     var time = (new Date()).getTime() - startTime;

     var linearSpeed = 100;
     var acceleration = 0;
     // pixels / second
     time = time / 1000; // convert to seconds
     var newY = linearSpeed * time + acceleration * Math.pow(time, 2) / 2;
     myRectangle.y = newY;

     // clear
     context.clearRect(0, 0, canvas.width, canvas.height);

     drawRectangle(myRectangle, context);

     // request new frame
     requestAnimFrame(function () {
         animate(myRectangle, canvas, context, startTime);
     });
 }
 ```
 这里，我们把有加速度和无加速度的代码写成一样了。区别就是将acceleration的值设置为0，就是匀速运行；不是0，就是加速运行。
 使用上面代码，或访问：http://jsfiddle.net/archcra/cko20q88/10/ 来观察效果。
 
 然后修改acceleration的值，以观察有加速度时的效果。可以将它改为200或更大。当然，改成负数也可以。
 
 
 


http://www.html5canvastutorials.com/advanced/html5-canvas-transform-translate-tutorial/


