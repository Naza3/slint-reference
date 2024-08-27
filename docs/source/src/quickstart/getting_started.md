<!-- Copyright © SixtyFPS GmbH <info@slint.dev> ; SPDX-License-Identifier: MIT -->

# 开始

本教程展示了如何使用 Slint 支持的语言作为主编程语言。

我们建议使用 [我们为 Slint 提供的编辑器集成](https://github.com/slint-ui/slint/tree/master/editors) 来按照本教程进行操作。

Slint 提供了应用模板，你可以使用这些模板创建一个项目，项目中已经配置好依赖项，并遵循推荐的最佳实践。

## 前提条件

:::::{tab-set}

::::{tab-item} C++
:sync: cpp

在使用模板之前，你需要一个支持 C++ 20 的 C++ 编译器，并安装 [CMake](https://cmake.org/download/) 3.21 或更高版本。

克隆或下载模板仓库：

```sh
git clone https://github.com/slint-ui/slint-cpp-template memory
cd memory
```

### 配置项目

`CMakeLists.txt` 使用 `add_executable(my_application src/main.cpp)` 这一行将 `src/main.cpp` 设置为主 C++ 代码文件。

将 `src/main.cpp` 的内容替换为以下内容：

:::{literalinclude} main_initial.cpp
:lines: 9-13
:::

在 `CMakeLists.txt` 中
`slint_target_sources(my_application ui/appwindow.slint)` 这一行是一个 Slint 函数，用于将 `appwindow.slint` 文件添加到目标中。

将 `ui/appwindow.slint` 的内容替换为以下内容：

:::{literalinclude} appwindow.slint
:language: slint,no-preview
:lines: 6-11
:::

使用 CMake 配置：

```sh
cmake -B build
```

:::{tip}
在使用 CMake 配置时，FetchContent 模块通过 git 获取 Slint 的源代码。第一次构建时可能需要一些时间，因为这个过程需要构建 Slint 运行时和编译器。
:::

使用 CMake 构建：

```sh
cmake --build build
```

### 运行应用程序

在 Linux 或 macOS 上运行应用程序二进制文件：

```sh
./build/my_application
```

在 Windows 上:

```sh
build\my_application.exe
```

这将打开一个窗口，显示绿色的“Hello World”问候语。

如果你在 Windows 机器上跟随本教程的每一步，可以使用以下命令运行应用程序：

```sh
my_application
```

::::

::::{tab-item} NodeJS
:sync: nodejs

克隆或下载模板仓库：

```sh
git clone https://github.com/slint-ui/slint-nodejs-template memory
cd memory
```

使用 npm 安装依赖项：

```sh
npm install
```

### 配置项目

`package.json` 文件指定 `src/main.js` 作为应用程序的入口点， 而 `src/main.js` 指定  `memory.slint` 作为 UI 文件。

将 `src/main.js` 的内容替换为以下内容：

:::{literalinclude} main_initial.js
:lines: 6-10
:::

The `slint.loadFile` 方法从进程的当前工作目录中解析文件，即从 `package.json` 文件所在的位置。

将 `ui/appwindow.slint` 的内容替换为以下内容：

:::{literalinclude} memory.slint
:language: slint,no-preview
:lines: 6-11
:::

### 运行应用程序

使用 `npm start` 运行示例，窗口将出现绿色的“Hello World”问候语。

::::

::::{tab-item} Rust
:sync: rust
:selected: true

我们建议使用 [rust-analyzer](https://rust-analyzer.github.io) 和 [我们为 Slint 提供的编辑器集成](https://github.com/slint-ui/slint/tree/master/editors) 来按照本教程进行操作。

使用以下命令安装 [模板](https://github.com/slint-ui/slint-rust-template) ：

```sh
cargo install cargo-generate
cargo generate --git https://github.com/slint-ui/slint-rust-template --name memory
cd memory
```

### 配置项目

将 `src/main.rs` 的内容替换为以下内容：

```rust
slint::include_modules!();

fn main() -> Result<(), slint::PlatformError> {
    let main_window = MainWindow::new()?;

    main_window.run()
}
```

将 `ui/appwindow.slint` 的内容替换为以下内容：

:::{literalinclude} memory.slint
:language: slint,no-preview
:lines: 6-11
:::

### 运行应用程序

使用 `cargo run` 运行示例，窗口将出现绿色的“Hello World”问候语。

::::

:::::

![Screenshot of initial tutorial app showing Hello World](https://slint.dev/blog/memory-game-tutorial/getting-started.png "Hello World")
