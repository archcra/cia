我们可以使用鼠标来控制动画的播放与停止。

这次的代码相对与以前的修改来讲，有些多，下面是animate的修改：
```
 function animate(lastTime, myRectangle, runAnimation, canvas, context) {
     if (runAnimation.value) {
         // update
         var time = (new Date()).getTime();
         var timeDiff = time - lastTime;

         // pixels / second
         var linearSpeed = 100;
         var linearDistEachFrame = linearSpeed * timeDiff / 1000;
         var currentX = myRectangle.x;

         if (currentX < canvas.width - myRectangle.width - myRectangle.borderWidth / 2) {
             var newX = currentX + linearDistEachFrame;
             myRectangle.x = newX;
         }

         // clear
         context.clearRect(0, 0, canvas.width, canvas.height);

         // draw
         drawRectangle(myRectangle, context);

         // request new frame
         requestAnimFrame(function () {
             animate(time, myRectangle, runAnimation, canvas, context);
         });
     }
 }

```

在定义myRectangle的后面，代码变化如下：
``
var myRectangle = {
     x: 0,
     y: 75,
     width: 100,
     height: 50,
     borderWidth: 5
 };

 /*
  * define the runAnimation boolean as an obect
  * so that it can be modified by reference
  */
 var runAnimation = {
     value: false
 };

 // add click listener to canvas
 document.getElementById('myCanvas').addEventListener('click', function () {
     // flip flag
     runAnimation.value = !runAnimation.value;

     if (runAnimation.value) {
         var date = new Date();
         var time = date.getTime();
         animate(time, myRectangle, runAnimation, canvas, context);
     }
 });

```
实际效果可以看这里：
http://jsfiddle.net/archcra/cko20q88/14/

注意开始时是不动的。用鼠标点那个方框，它对动；再点它一次，它会停。

