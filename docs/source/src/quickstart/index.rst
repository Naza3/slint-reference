.. Copyright © SixtyFPS GmbH <info@slint.dev>
.. SPDX-License-Identifier: MIT

快速开始
==========

本教程以一种有趣的方式介绍了 Slint UI 框架，通过实现一个记忆游戏来展示。它将用于图形的 Slint 语言与用 C++、Rust 或 NodeJS 实现的游戏规则相结合。

游戏由一个包含 16 个矩形图块的网格组成。点击一个图块会揭示其下面的图标。总共有 8 种不同的图标，因此每个图块在网格中都有一个具有相同图标的配对。
目标是找到所有图标配对。玩家可以同时揭示两个图块。如果它们不相同，游戏会再次遮住这些图标。

这是游戏运行时的样子：

.. raw:: html
   
   <video autoplay loop muted playsinline src="https://slint.dev/blog/memory-game-tutorial/memory_clip.mp4" class="img-fluid img-thumbnail rounded"></video>

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Quickstart

   getting_started.md
   memory_tile.md   
   polishing_the_tile.md   
   from_one_to_multiple_tiles.md   
   creating_the_tiles.md   
   game_logic.md   
   running_in_a_browser.md
   ideas_for_the_reader.md   
   conclusion.md   
