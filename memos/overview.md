
### 文件结构
资料来源： [这里](http://liuyiqi123.github.io/2017/12/14/BootStrap4%E6%A0%B8%E5%BF%83%E6%BA%90%E7%A0%81%E5%AD%A6%E4%B9%A0%E4%B9%8BCSS%E9%83%A8%E5%88%86/)

```
bootstrap/scss
├── mixins/ // @mixin方法
├── utilities/ // 全局样式
├── _alert.scss // 警告-组件
├── _badge.scss // 徽章-组件
├── _breadcrumb.scss //面 包屑-组件
├── _buttons-group.scss // 按钮组-组件
├── _buttons.scss // 按钮-组件
├── _card.scss // 卡片-组件
├── _carousel.scss // 滚屏-组件
├── _close.scss // 关闭-全局样式
├── _code.scss // 代码-内容
├── _custom-forms.scss // 表单_自定义表单-组件
├── _dropdown.scss // 下拉菜单
├── _forms.scss // 表单-组件
├── _functions.scss // 公共方法
├── _grid.scss // 栅格-布局
├── _images.scss // 图片、图解-内容
├── _input-group.scss // 输入类-组件
├── _jumbotron.scss // 超大屏-组件
├── _list-group.scss // 列表类-组件
├── _media.scss // 媒体-布局
├── _mixins.scss // 总的@mixin方法，，引用mixins目录下文件
├── _modal.scss // 模态框-组件
├── _nav.scss // 导航-组件
├── _navbar.scss // 导航条-组件
├── _pagination.scss // 分页-组件
├── _popover.scss // 弹出框-组件
├── _print.scss // 打印样式
├── _progress.scss // 进度条-组件
├── _reboot.scss // 初始化样式
├── _root.scss // 基本颜色、屏幕断点
├── _tables.scss // 表格-内容
├── _tooltip.scss // 工具提示-组件
├── _transitions.scss // 过渡效果：折叠，显示隐藏
├── _type.scss // 排版-内容
├── _utilities.scss // 总的全局样式，引用utilities目录下文件
├── _variables.scss // 变量集合
├── bootstrap-grid.scss //栅格CSS
├── bootstrap-reboot.scss //启动CSS
└── bootstrap.scss //完整css
```

最下面的三个文件夹是三种使用方式，具体使用情况详见上述资料参考链接。


### 关于sass

1. `_partial.scss`  
  下划线是告诉sass，这个文件的内容是一个partial，是通过`@import`使用的，不用编译成css。**由此可见，最终会编译为css的只有三个文件，其他所有的皆为partial。**