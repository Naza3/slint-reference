<!-- Copyright © SixtyFPS GmbH <info@slint.dev> ; SPDX-License-Identifier: MIT -->

# 支持的平台

Slint 可以运行在许多桌面和嵌入式平台以及微控制器上。

在下面描述的平台中，已经在部署环境中测试过。 对于开发环境，我们推荐使用最新的桌面操作系统和编译器。

如果你需要获取特定旧版本的支持，请与 [SixtyFPS GmbH](https://slint.dev/contact) 联系。

## 桌面平台

一般来说，Slint 可以在 Windows、macOS 和流行的 Linux 发行版上运行。 以下表格中，列出了我们专门测试过的版本。总体目标是支持在 Slint 版本发布时，供应商仍在支持的操作系统。

### Windows

| 操作系统 | 架构 |
| ---------------- | ------------ |
| Windows 10       | x86-64       |
| Windows 11       | x86-64       |

### macOS

| 操作系统  | 架构    |
| ----------------- | --------------- |
| macOS 12 Monterey | x86-64, aarch64 |
| macOS 13 Ventura  | x86-64, aarch64 |
| macOS 14 Sonoma   | x86-64, aarch64 |

### Linux

Linux 桌面发行版种类繁多，只要使用 Wayland 或 X-Windows、glibc 和 d-bus，Slint 应该可以在任何发行版上运行。如果某个 Linux 发行版提供长期支持 (LTS)，那么在 Slint 版本发布时，Slint 应该可以运行在最新的 LTS 或更新的版本上。

## 嵌入式平台

Slint 可以运行在多种嵌入式平台上。一般来说，Slint 需要一个现代的 Linux 用户空间，并具备可用的 OpenGL ES 2.0（或更新版本）或 Vulkan 驱动程序。我们已经成功地在以下平台上运行了 Slint：

-   基于 Yocto 的发行版。对于 C++ 应用程序，请参阅 [meta-slint](https://github.com/slint-ui/meta-slint)。Rust 应用程序可以直接使用 Yocto 的 Rust 支持运行。
-   基于 BuildRoot 的发行版。
-   [TorizonCore](https://www.torizon.io/torizoncore-os).

### 微处理器

Slint 的平台抽象层允许集成到任何基于 Rust 或 C++ 的微控制器开发环境中。开发人员需要实现相关功能，以传递触摸或键盘等输入事件，并将 Slint 渲染的像素显示到帧缓冲区或行缓冲区中。