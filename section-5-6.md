sprite在碰撞后，才会被销毁；如果我们将碰撞函数永远返回假(false)，就会告诉程序-一直也没有碰撞上，这是不是就无敌了？

我们修改一下代码：
```
// Collisions
function collides(x, y, r, b, x2, y2, r2, b2) {
    return false;
    //return !(r <= x2 || x > r2 ||
      //       b <= y2 || y > b2);
}
```
上面将collides函数的原来的判断给注释掉了，即它们不会被执行。而直接加了一个return false;

collide [kəˈlaɪd] vi.碰撞
false [fɔ:ls] a. 假的

我们试一下效果：
http://jsfiddle.net/archcra/Lvkqj4up/5/

确实无敌了！
不过也不好-敌人也无敌了。这样做把子弹和敌人的碰撞也给忽略掉了，子弹不再有效果，这不是我们想要的。

我们玩一玩这个游戏就会知道，当sprite和敌舰碰撞时，游戏会结束。那我们修改这里，不让游戏结束，就应该可以了：

在checkCollisions函数中，我们找到如下代码：
```
        if (boxCollides(pos, size, player.pos, player.sprite.size)) {
            //gameOver();
        }
```

将gameOver()这句话前面加上注释，如上面所示（原来是没有注释的），那么，就会得到我们期望的无敌了，试试吧：http://jsfiddle.net/archcra/Lvkqj4up/6/


