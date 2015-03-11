# AlloyRenderingEngine
Super fast HTML 5 2D rendering engine , supporting Canvas and WebGL rendering

* [api](http://alloyteam.github.io/AlloyRenderingEngine/doc/)
* [kmdjs](https://github.com/kmdjs/kmdjs)


# Demos
* [bitmap](http://alloyteam.github.io/AlloyRenderingEngine/example/bitmap.html) 
* [transform](http://alloyteam.github.io/AlloyRenderingEngine/example/transform.html) 
* [flip](http://alloyteam.github.io/AlloyRenderingEngine/example/flip.html) 
* [filter](http://alloyteam.github.io/AlloyRenderingEngine/example/filter.html) 
* [shape](http://alloyteam.github.io/AlloyRenderingEngine/example/shape.html) 
* [sprite](http://alloyteam.github.io/AlloyRenderingEngine/example/sprite.html) 
* [txt](http://alloyteam.github.io/AlloyRenderingEngine/example/txt.html) 
* [particle](http://alloyteam.github.io/AlloyRenderingEngine/example/particle.html) 
* [particle system](http://alloyteam.github.io/AlloyRenderingEngine/example/particlesystem.html) 
* [box2d](http://alloyteam.github.io/AlloyRenderingEngine/example/box2d.html) 
* [keyboard events](http://alloyteam.github.io/AlloyRenderingEngine/example/keyboardevents.html) 
* [collision](http://alloyteam.github.io/AlloyRenderingEngine/example/collision.html) 
* [loader](http://alloyteam.github.io/AlloyRenderingEngine/example/loader/loader.html) 
* [scalable](http://alloyteam.github.io/AlloyRenderingEngine/example/scalable.html)

# Tutorials
* [lesson1](http://www.cnblogs.com/iamzhanglei/p/4306146.html)

# Usage
To achieve this effect:

![usage](https://raw.githubusercontent.com/AlloyTeam/AlloyRenderingEngine/master/asset/img/usage2.gif)

You need to use the following code:

```javascript
var bmp, stage = new Stage("#ourCanvas");
bmp = new Bitmap("img/atLogo.png");
//（0.5,0.5）==〉The center is the point of rotation
bmp.originX = 0.5;
bmp.originY = 0.5;
//bind click event, the event monitor can be accurate to pixel
bmp.onClick(function () {
    //apply a random filter to the bmp
    bmp.setFilter(Math.random(), Math.random(), Math.random(), 1);
});
//add object to stage
stage.add(bmp);

var step = 0.01;
//loop
stage.onTick(function () {
    bmp.rotation += 0.5;
    if (bmp.scaleX > 1.5 || bmp.scaleX < 0.5) {
        step *= -1;
    }
    bmp.scaleX += step;
    bmp.scaleY += step;
});
```

This content is released under the (http://opensource.org/licenses/MIT) MIT License.
