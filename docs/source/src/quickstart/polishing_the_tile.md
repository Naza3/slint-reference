<!-- Copyright © SixtyFPS GmbH <info@slint.dev> ; SPDX-License-Identifier: MIT -->

# 打磨图块

在此步骤中，你将添加一个帘幕状的覆盖层，点击时会打开。你可以通过在 <span class="hljs-built_in">Image</span> 元素下方声明两个矩形来实现这一点，这样 Slint 就会在绘制图像之后绘制这些矩形，从而使它们显示在图像的顶部。

<span class="hljs-built_in">TouchArea</span> 元素声明了一个透明的矩形区域， 用于响应用户输入，例如鼠标点击或轻触。该元素将回调函数传递给 <em>MainWindow</em> ，以指示用户点击了图块。

<em>MainWindow</em> 通过切换自定义的 <em>open_curtain</em> 属性来做出响应。
动画的 width 和 x属性的绑定也使用了这个自定义的 <em>open_curtain</em> 属性。

下表详细说明了这两个状态：

| _open_curtain_ value:   | false                                                                        | true                                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| 左侧帘幕矩形  | 通过将宽度 _width_ 设置为父级宽度的一半来填充左半部分   | 将 _width_ 设为零会使矩形不可见。                                                                  |
| 右侧帘幕矩形 |通过将 _x_ 和 _width_ 设置为父级宽度的一半来填充右半部分。 | 将 _width_ 设为零会使矩形不可见。 _x_ 向右移动， 动画时滑动帘幕打开。

为了使图块具有扩展性，将硬编码的图标名称替换为一个 _icon_ 属性
，该属性可以在实例化元素时设置。

最后一步，添加一个
_solved_ 属性，用于在玩家找到配对时将颜色动画过渡到绿色的阴影。

用以下内容替代 `ui/appwindow.slint` 文件:

:::{literalinclude} main_polishing_the_tile.rs
:language: slint,no-preview
:lines: 10-61
:::

代码中使用的 `root` 和 `self`. `root` 指的是组件中的最外层元素，当前情况下是指 <span class="hljs-title">MemoryTile</span> 。`self` 指的是当前元素。

代码导出了 <span class="hljs-title">MainWindow</span> 组件。为了可以在后续的应用程序业务逻辑中访问它，这一步是必要的。

运行代码将打开一个窗口，点击矩形会展开，显示公交车图标。后续的点击会再次关闭和打开帘幕。

<video autoplay loop muted playsinline src="https://slint.dev/blog/memory-game-tutorial/polishing-the-tile.mp4"></video>
