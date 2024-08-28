<!-- Copyright © SixtyFPS GmbH <info@slint.dev> ; SPDX-License-Identifier: MIT -->

# 记忆图块

在程序框架代码就位后，本步骤将关注游戏的第一个元素——记忆图块。它是由一个填充的矩形背景和图标图像组成的视觉构建块。后续步骤会添加一个覆盖矩形作为遮罩。

你将背景矩形声明为 64 个逻辑像素宽和高，并填充上舒缓的蓝色调。

Slint 中的长度有单位，这里使用了 `px` 后缀。
这使得代码更易读，并且编译器可以检测到你是否不小心混合了不同单位的值。

将以下代码复制到 `ui/appwindow.slint` 文件，替换当前内容：

:::{literalinclude} memory_tile.slint
:language: slint,no-preview
:lines: 5-19
:::

这将导出 <span class="hljs-title">MainWindow</span> 组件，以便游戏逻辑代码可以在后续访问它。

在 <span class="hljs-built_in">Rectangle</span> 内部放置一个 <span class="hljs-built_in">Image</span> 元素，该元素使用 <span class="hljs-built_in">@image-url()</span> 宏加载图标。路径是相对于 `ui/appwindow.slint` 文件的位置。

你需要先安装这个图标以及后续使用的其他图标。你可以将预先准备好的
[Zip 文件](https://slint.dev/blog/memory-game-tutorial/icons.zip) 下载到 `ui` 文件夹中，

如果你使用的是 Linux 或 macOS，可以使用以下命令下载并解压缩：

```sh
cd ui
curl -O https://slint.dev/blog/memory-game-tutorial/icons.zip
unzip icons.zip
cd ..
```

如果你使用的是 Windows，使用以下命令：

```sh
cd ui
powershell curl -Uri https://slint.dev/blog/memory-game-tutorial/icons.zip -Outfile icons.zip
powershell Expand-Archive -Path icons.zip -DestinationPath .
cd ..
```

这将解压出一个包含多个图标的 `icons` 目录。

::::{tab-set}
:::{tab-item} C++
:sync: cpp

使用 `cmake --build build` 编译程序，并使用 `./build/my_application` 运行程序，将打开一个窗口，显示在蓝色背景上的公交车图标。

:::

:::{tab-item} NodeJS
:sync: nodejs

使用 `npm start` 运行程序，将打开一个窗口，显示在蓝色背景上的公交车图标。

:::

:::{tab-item} Rust
:sync: rust
:selected: true

使用 `cargo run` 运行程序，将打开一个窗口，显示在蓝色背景上的公交车图标。

:::

::::

![Screenshot of the first tile](https://slint.dev/blog/memory-game-tutorial/memory-tile.png "Memory Tile Screenshot")
