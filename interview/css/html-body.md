`html` 和 `body` 的区别

----


根据标准定义，`<html>` 是文档的根元素，`<head>`、`<body>` 是 `<html>` 唯一的两个子元素，`<head>` 才是和 `<body>` 相对照、需要加以区别的元素

因此，`<html>` 和 `<body>` 是父子关系，在 HTML 文档中，`:root` 选择符对应 `<html>` 元素

> `:root` 选择符（伪类）的优先级大于 `html` 选择符

两个常见问题

## background-color

将 `background-color` 应用到 `<body>` 以后，即便 `<body>` 里的元素没有占满视口，背景颜色也会蔓延到整个视口

这时给 `html` 设置 `background-color` 可以解决这个问题

## height: 100%

一般比较常见的是设置 `html, body {height: 100%}`

这样做是为了兼容各个浏览器

* 处于混杂模式时，`body` 以窗口为高度参照，`body` 设置为 `100%` 就可以使得页面和窗口一样高，`body` 里面的嵌套 `div` 也可以扩展到窗口高度，这样的话可以使布局适应浏览器窗口大小

* 当处于标准模式时，`body` 以 `html` 标签为高度参照，`html` 标签才以窗口为参照，所以仅仅 `body 100%`，并不能使它的子 `div` 也为 `100%` 来占据整个屏幕，还要设置 `html 100%` 使得 `html` 获得窗口大小才行