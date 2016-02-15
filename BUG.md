
## Resource

* [QuirksMode—for all your browser quirks](http://www.quirksmode.org/)
* [The Modernizr issue tracker on GitHub](https://github.com/Modernizr/Modernizr/issues?q=is%3Aopen)
* [LukeW Ideation + Design | Digital Product Strategy & Design](http://www.lukew.com/)

## Mobile

* iOS 9.2 大部分浏览器

不支持 `new Date('2012-02-28 03:22:18')` 这种写法（PC 端是支持的，Android 没有测试）

需要写成 `new Date(2012, 1, 28, 3, 22, 18)`， **注意月分需要减 1**

* Android UC浏览器（版本 20151231）
  
  ```
  <div style="display: -webkit-box;">
    <div style="display:inline-block;">A</div>
    <div style="display:inline-block;">B</div>
    <div style="display:inline-block;">C</div>
  </div>
  ```

  用上面的 HTML 结构，无论最外层的 DIV 有多宽，C DIV 都会显示在第二行，像下面这样

  ```
  A  B
  C
  ```

  另外，如果子元素要用 `-webkit-box-flex: 1` ， 则其 display 最好都设置成 block

  **总结** `display: flex` 下的子元素不要设置成 `display: inline-blox`

* 老版本安卓 UC浏览器

  将 img 设置成圆形，同时加上边框，得不到预期的圆形边框的效果

  ```
  img {
    display: block;
    border-radius: 50%;
    border: 2px solid red;
  }
  ```

  解决方案：在 img 下面再放一个稍微大点的 div，将它的背景设置成边框的颜色，再将图片上下左右居中的放在此 div 上


## IE

* IE7 float元素的子元素无法获取父元素被撑开的真实宽度

  如果父元素是 float 定位，其中一个子元素 A 将其撑开，另一个子元素 B 的宽度如果设置成 100%，则它其实无法达到 A 的宽度

  ```
  <style type="text/css">
    .test {
      float: left;
    }
    .a {
      width: 200px;
      background: yellow;
    }
    .b {
      width: 100%;
      background: red;
    }
  </style>
  <div class="test">
    <div class="a">a</div>
    <div class="b">b</div>
  </div>
  ```
  
  ![效果图](./res/ie7-float-percent.jpg)

* IE7/8 无法使用 rgba 的颜色值

  所以在创建 mask 时，需要将 mask 单独创建一个图层，然后通过 ie 的滤镜来设置此图片的整体透明度

  ```
  background-color: black;
  filter: alpha(opacity=50);
  opacity: 0.5;
  ```

* IE7 a 标签不会继承父类标签的 color 值
* IE7 scroll 事件不能绑定在 document 上，需要绑定在 window 上


