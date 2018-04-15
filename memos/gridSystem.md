### 栅格系统（bootstrap-grid.scss）

- 格栅系统的三部分

  格栅系统是基于container、row、column三部分构建起来的。

  **container**: 最外层的容器，作用是居中并根据屏幕宽度来确定宽度  
  **row**: flex容器，允许flex-item换行  
  **column**： 主要定义了flex-item的flex-basis，显示顺序，缩进距离等


- 整体

  - 栅格系统文件构成
    ```
    @import "functions";//没有感觉这个文件在这里有什么卵用。。。也许没看到。。。
    @import "variables";//包含了所有的变量，grid用到的已列在下边

    @import "mixins/breakpoints";//根据breakpoints进行不同的创建工作
    @import "mixins/grid-framework";//仅包含了make-grid-container的具体代码
    @import "mixins/grid";//make-container,make-row的具体代码

    @import "grid";//组合其他部分，创建container，row，column
    @import "utilities/display";//设置了各种尺寸下的display，放在了全局样式下
    @import "utilities/flex";//设置了各种尺寸下的flex的具体属性，放在了全局样式下

    ```
- variables文件
  1. `$enable-grid-classes`：控制是否开启栅格系统的container，row，column
  2. `$grid-gutter-width:           30px !default;`：栅格沟槽（边儿？）宽度
  3. 定义了不同屏幕下的breakpoint
  ```
  $grid-breakpoints: (
    xs: 0,
    sm: 576px,
    md: 768px,
    lg: 992px,
    xl: 1200px
  ) !default;
  ```
  4. 定义了不同屏幕下container的最大宽度
  ```
  $container-max-widths: (
    sm: 540px,
    md: 720px,
    lg: 960px,
    xl: 1140px
  ) !default;
  ```
  5. 定义了格栅系统的列数以及列间距
  ```
  $grid-columns:                12 !default;
  $grid-gutter-width:           30px !default;
  ```

### css查漏补缺
1. `flex-basis: 0;`
  当设值为0时，这个flex-item就会按它的内容来控制宽度，如果同时设置了overflow为hidden，那么宽度就会为0。*（注：这个在stack overflow上能搜到）*
2. `flex-basis`的优先级高于`width`，如果两个都设值为auto，那么宽度由内容来决定。
3. `flex-basis`会受制于`max-width`以及`min-width`  
*[注：参考](https://www.jianshu.com/p/17b1b445ecd4)*

### 问题
  1. 不明白为啥要单独将`make-grid-container`提出来放进mixin文件夹里。。。因为它的复杂程度？
  2. 开头的这个不知道干嘛使的。
      ```
      @at-root {
        @-ms-viewport { width: device-width; } // stylelint-disable-line at-rule-no-vendor-prefix
      }
      ```
      **解决一个！！！这个是sass的一个语法，用来将`@at-root`包裹的规则置于文件的最顶层，不会被其他选择器包裹**里面那个还是不知道咋回事。