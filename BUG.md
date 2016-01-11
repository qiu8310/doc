
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
