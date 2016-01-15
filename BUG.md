
* 安桌 UC浏览器（版本 20151231）
  
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

* 安卓老浏览器

  将 img 设置成圆形，同时加上边框，得不到预期的圆形边框的效果

  ```
  img {
    display: block;
    border-radius: 50%;
    border: 2px solid red;
  }
  ```

  解决方案：在 img 下面再放一个稍微大点的 div，将它的背景设置成边框的颜色，再将图片上下左右居中的放在此 div 上
