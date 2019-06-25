# rust-lang/rustup.rs [![explain]][source] [![translate-svg]][translate-list]

<!-- [![size-img]][size] -->

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list
[size-img]: https://packagephobia.now.sh/badge?p=Name
[size]: https://packagephobia.now.sh/result?p=Name

「 rustup：Rust 工具链安装程序 」

[中文](./readme.md) | [english](https://github.com/rust-lang/rustup.rs)

---

## 校对 ✅

<!-- doc-templite START generated -->
<!-- repo = 'rust-lang/rustup.rs' -->
<!-- commit = '2ece700231f8a1778647981df94052e5b27cbedf' -->
<!-- time = '2019-06-24' -->

| 翻译的原文 | 与日期        | 最新更新 | 更多                       |
| ---------- | ------------- | -------- | -------------------------- |
| [commit]   | ⏰ 2019-06-24 | ![last]  | [中文翻译][translate-list] |

[last]: https://img.shields.io/github/last-commit/rust-lang/rustup.rs.svg
[commit]: https://github.com/rust-lang/rustup.rs/tree/2ece700231f8a1778647981df94052e5b27cbedf

<!-- doc-templite END generated -->

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[hIf help, **buy** me coffee —— 营养跟不上了，给我来瓶营养快线吧! 💰](https://github.com/chinanf-boy/live-need-money)

---

# rustup：Rust 工具链安装程序

| CI       | 构建状态                                                 |
| -------- | -------------------------------------------------------- |
| Travis   | [![Travis Build Status][travis-badge]][travis-url]       |
| AppVeyor | [![AppVeyor Build Status][appveyor-badge]][appveyor-url] |

*rustup*从官方发布版本安装[Rust 编程语言][rustlang]，您可以轻松地在稳定版，测试版和夜间编译器之间切换，并保持更新。它使跨平台编译更简单——使用标准库的，用于通用平台的二进制构建。它运行在 Rust 支持的所有平台上，包括 Windows。

[rustlang]: https://www.rust-lang.org

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [安装](#%E5%AE%89%E8%A3%85)
- [如何 Rust 起作用](#%E5%A6%82%E4%BD%95%E7%94%9F%E9%94%88%E8%B5%B7%E4%BD%9C%E7%94%A8)
- [保持 Rust 更新](#%E4%BF%9D%E6%8C%81rust%E6%9B%B4%E6%96%B0)
- [和夜间 Rust 一起工作](#%E5%92%8C%E5%A4%9C%E9%97%B4rust%E4%B8%80%E8%B5%B7%E5%B7%A5%E4%BD%9C)
- [工具链规范](#%E5%B7%A5%E5%85%B7%E9%93%BE%E8%A7%84%E8%8C%83)
- [工具链覆盖速记](#%E5%B7%A5%E5%85%B7%E9%93%BE%E8%A6%86%E7%9B%96%E9%80%9F%E8%AE%B0)
- [目录覆盖](#%E7%9B%AE%E5%BD%95%E8%A6%86%E7%9B%96)
- [工具链文件](#%E5%B7%A5%E5%85%B7%E9%93%BE%E6%96%87%E4%BB%B6)
- [覆盖优先级](#%E8%A6%86%E7%9B%96%E4%BC%98%E5%85%88%E7%BA%A7)
- [跨平台汇编](#%E4%BA%A4%E5%8F%89%E6%B1%87%E7%BC%96)
- [处理 Windows 上的锈迹](#%E5%A4%84%E7%90%86%E7%AA%97%E6%88%B7%E4%B8%8A%E7%9A%84%E9%94%88%E8%BF%B9)
- [使用分配防锈包](#%E4%BD%BF%E7%94%A8%E5%88%86%E9%85%8D%E9%98%B2%E9%94%88%E5%8C%85)
- [使用自定义工具链和本地生成](#%E4%BD%BF%E7%94%A8%E8%87%AA%E5%AE%9A%E4%B9%89%E5%B7%A5%E5%85%B7%E9%93%BE%E5%92%8C%E6%9C%AC%E5%9C%B0%E7%94%9F%E6%88%90)
- [使用网络代理](#%E4%BD%BF%E7%94%A8%E7%BD%91%E7%BB%9C%E4%BB%A3%E7%90%86)
- [示例](#%E7%A4%BA%E4%BE%8B)
- [环境变量](#%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F)
- [其他安装方法](#%E5%85%B6%E4%BB%96%E5%AE%89%E8%A3%85%E6%96%B9%E6%B3%95)
- [安全](#%E5%AE%89%E5%85%A8)
- [常见问题解答](#%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94)
- [许可证](#%E8%AE%B8%E5%8F%AF%E8%AF%81)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 安装

按照<https://rustup.rs>说明进行操作。如果这对你不起作用的话，请看[其他安装方式](#%E5%85%B6%E4%BB%96%E5%AE%89%E8%A3%85%E6%96%B9%E6%B3%95)

`rustup`会安装`rustc`，`cargo`，`rustup`和 Cargo 的其他标准工具到`bin`目录。在 Unix 上，它位于`$HOME/.cargo/bin`；在 Windows 上则是`%USERPROFILE%\.cargo\bin`。这是`cargo install`将安装 Rust 程序和 Cargo 插件到同一个目录。

这个目录包含在你的`$PATH`环境变量，这意味着您无需进一步配置，即可从 shell 运行它们。打开一个*新*shell，并输入以下内容：

```
rustc --version
```

如果你看到类似`rustc 1.19.0 (0ade33941 2017-07-17)`的东西，那你就准备好 Rust。如果您认为 Rust 不是您的选择，您可以通过运行`rustup self uninstall`将其从系统中完全删除。

#### 为 Bash，Fish，Zsh 或 PowerShell 启用 tab 补全

`rustup`现在支持 Bash，Fish，Zsh 和 PowerShell 的 tab 补全脚本。看`rustup help completions`有关详细信息，但关键点，就像使用以下其中一项一样简单：

```console
# Bash
$ rustup completions bash > ~/.local/share/bash-completion/completions/rustup

# Bash (macOS/Homebrew)
$ rustup completions bash > $(brew --prefix)/etc/bash_completion.d/rustup.bash-completion

# Fish
$ mkdir -p ~/.config/fish/completions
$ rustup completions fish > ~/.config/fish/completions/rustup.fish

# Zsh
$ rustup completions zsh > ~/.zfunc/_rustup

# PowerShell v5.0+
$ rustup completions powershell >> $PROFILE.CurrentUserCurrentHost
# or
$ rustup completions powershell | Out-String | Invoke-Expression
```

*注意：*您可能需要重新启动 shell，才能使更改生效。

对于`zsh`，然后你必须在你的`~/.zshrc`中，在`compinit`之前添加以下行：

```zsh
fpath+=~/.zfunc
```

#### 选择安装位置

`rustup`允许您在运行`rustup-init`可执行文件之前，通过设置环境变量`CARGO_HOME`和`rUSTUP_HOME`，自定义安装。正如在[环境变量][environment variables]章节提到的，`rUSTUP_HOME`设置 rustup 根文件夹，(该目录)用于存储已安装的工具链和配置选项。`CARGO_HOME`包含[Cargo]使用的缓存文件。

请注意，您需要确保始终设置这些环境变量，还有使用工具链时，`CARGO_HOME/bin`在`$PATH`环境变量里面。

[environment variables]: #环境变量
[cargo]: https://github.com/rust-lang/cargo

## rustup 怎样工作

`rustup`是一个*工具链多路复用器*。它安装和管理许多 Rust 工具链，并通过安装在`~/.cargo/bin`的一组工具，将它们全部呈现出来。安装到`~/.cargo/bin`的`rustc`和`cargo`是*代理*，委托给真正的工具链。`rustup`然后通过重新配置代理的行为，提供轻松更改活动工具链的机制。

所以当`rustup`是第一次安装后，运行`rustc`，就会运行`$HOME/.cargo/bin/rustc`的代理，背后将运行稳定的编译器。如果你以后*更改默认工具链*到了 nightly —— `rustup default nightly`，将运行相同的代理，但换成了`nightly`编译器。

这与 Ruby 的[rbenv]，Python 的[pyenv]或者 Node 的[nvm]类似。

[rbenv]: https://github.com/rbenv/rbenv
[pyenv]: https://github.com/yyuu/pyenv
[nvm]: https://github.com/creationix/nvm

## 保持 Rust 最新

Rust 分布在三个不同的[发布版本][release channels]：稳定，测试版和夜间版。`rustup`默认配置使用稳定通道，这代表最新版本的 Rust，每六周发布一次。

[release channels]: https://github.com/rust-lang/rfcs/blob/master/text/0507-release-channels.md

当发布新版本的 Rust 时，您可以键入`rustup update`更新它：

```console
$ rustup update
info: syncing channel updates for 'stable'
info: downloading component 'rustc'
info: downloading component 'rust-std'
info: downloading component 'rust-docs'
info: downloading component 'cargo'
info: installing component 'rustc'
info: installing component 'rust-std'
info: installing component 'rust-docs'
info: installing component 'cargo'
info: checking for self-updates
info: downloading self-updates

  stable updated: rustc 1.7.0 (a5d1e7a59 2016-02-29)
```

这就是`rustup`的本质工作。

### 保持最新的 rustup

运行`rustup update`还会检查`rustup`的更新，并自动安装最新版本。手动检查更新，并安装最新版本`rustup`，不去更新已安装的工具链，键入`rustup self update`：

```console
$ rustup self update
info: checking for self-updates
info: downloading self-updates
```

**注意**：`rustup`在任何工具链安装结束时，也会自动更新。您可以通过传递`--no-self-update`来阻止此自动行为，可用在一般命令`rustup update`要么`rustup toolchain install`。

## 和夜间 Rust 一起工作

rustup 使您可以轻松访问夜间编译器，及其编译器[实验性功能][experimental features]。要添加它只要运行`rustup toolchain install nightly`：

[experimental features]: https://doc.rust-lang.org/unstable-book/

```console
$ rustup toolchain install nightly
info: syncing channel updates for 'nightly'
info: downloading toolchain manifest
info: downloading component 'rustc'
info: downloading component 'rust-std'
info: downloading component 'rust-docs'
info: downloading component 'cargo'
info: installing component 'rustc'
info: installing component 'rust-std'
info: installing component 'rust-docs'
info: installing component 'cargo'

  nightly installed: rustc 1.9.0-nightly (02310fd31 2016-03-19)
```

现在 Rust nightly 已安装，但未激活。要测试它，你可以从夜间工具链中运行命令

```console
$ rustup run nightly rustc --version
rustc 1.9.0-nightly (02310fd31 2016-03-19)
```

但更有可能你想暂时使用它。要全局切换到夜间，请使用更改默认值`rustup default nightly`：

```console
$ rustup default nightly
info: using existing install for 'nightly'
info: default toolchain set to 'nightly'

  nightly unchanged: rustc 1.9.0-nightly (02310fd31 2016-03-19)
```

现在任何你运行`cargo`或`rustc`的时候，都将运行夜间编译器。

有了夜间后，每次运行`rustup update`时，除了稳定版之外，夜间版本也会更新：

```console
$ rustup update
info: syncing channel updates for 'stable'
info: syncing channel updates for 'nightly'
info: checking for self-updates
info: downloading self-updates

   stable unchanged: rustc 1.7.0 (a5d1e7a59 2016-02-29)
  nightly unchanged: rustc 1.9.0-nightly (02310fd31 2016-03-19)
```

## 工具链规范

又许多`rustup`处理*工具链*的命令，Rust 编译器的单个安装。`rustup`支持多种类型的工具链。官方发布版本最基本的轨道：_稳定_，*测试*和*夜间*；但`rustup`还可以从官方存档，备用主机平台和本地构建中，安装工具链。

标准发布版本的工具链名称，具有以下形式：

```
<channel>[-<date>][-<host>]

<channel>       = stable|beta|nightly|<version>
<date>          = YYYY-MM-DD
<host>          = <target-triple>
```

'channel'是指定的发布通道或明确版本号，例如'1.8.0'。通道名称可以选择附加存档日期，如'nightly-2014-12-18'，在这种情况下，工具链将从该日期的存档中下载。

最后，可以将主机指定为目标三元组。这应用在 64 位平台上，安装 32 位编译器或在 Windows 上安装[基于 MSVC 的工具链][msvc-toolchain]。例如：

```console
$ rustup toolchain install stable-x86_64-pc-windows-msvc
```

为方便起见，将推断出省略的目标三元组元素，因此可以写出以下内容：

```console
$ rustup toolchain install stable-msvc
```

可以使用未命名通道的工具链名称，来命名[自定义工具链][custom toolchains]。

[msvc-toolchain]: https://www.rust-lang.org/tools/install?platform_override=win
[custom toolchains]: #working-with-custom-toolchains-and-local-builds

## 工具链覆盖速记

该`rustup`可以直接指示工具链代理，使用特定的工具链，这对于经常测试不同工具链的开发人员来说非常方便。如果`cargo`，`rustc`或工具链中的其他工具的第一个参数，是从`+`开始，它将被解释为一个 Rust 的工具链名称，并且该工具链将是首选，如

```console
cargo +beta test
```

## 目录覆盖

`rustup override`可以把目录，分配(覆盖)成自己的 Rust 工具链。当目录有覆盖时，`rustc`要么`cargo`如果在该目录或其子目录中运行的任何时候，则将调用覆盖上的工具链。

要在一个目录中，使用特定的夜间版本：

```console
rustup override set nightly-2014-12-18
```

或特定的稳定版本：

```console
rustup override set 1.0.0
```

要查看活动的工具链，请使用`rustup show`. 要删除覆盖，要再次使用默认的工具链，`rustup override unset`.

## 工具链文件

`rustup`目录的覆盖(信息)是本地配置，存储在`$rUSTUP_HOME`。不过，有些项目发现自己“固定”在一个特定的 Rust 版本上，并希望这些信息反映在它们的源存储库中。这种情况最常见，也仅限于夜间使用的软件，该软件可固定在版本档案的修订版上。

在这些情况下工具链，可以在项目目录中，整入名为`rust-toolchain`文件，其内容是单个`rustup`工具链的名称，适用于签入到源代码管理。

此文件中命名的工具链的形式，一般比 Rust 的工具链更受限制，并且可能只包含三个发布版本的名称：“stable”、“beta”、“nightly”、“Rust 版本号”，如“1.0.0”，以及可选的存档日期，如“nightly-2017-01-01”。它们不能命名自定义工具链，也不能命名特定宿主的工具链。

## 覆盖优先级

有几种方法可以指定`rustup`，应执行哪个工具链：

- 一个明确的工具链，例如`cargo +beta`，
- `rUSTUP_TOOLCHAIN`环境变量，
- 目录覆盖，又名`rustup override set beta`，
- `rust-toolchain`文件，
- 默认的工具链，

而 rustup 优先选择它们，其中明确的工具链具有最高优先级，默认工具链具有最低优先级。但有一个例外：目录覆盖和`rust-toolchain`文件也是由靠近当前目录的代理选择的。也就是说，这两个覆盖方法是通过在文件系统根目录树找寻发现的，并且较近当前目录的`rust-toolchain`文件，将优先于较远的目录覆盖。

要验证哪个工具链处于活动状态，请使用`rustup show`。

## 跨平台汇编

Rust[支持大量平台][p]。对于这些平台中的许多，rust 项目发布标准库的二进制版本，对于一些完整的编译器。`rustup`让所有人都能轻松用到它们。

[p]: https://forge.rust-lang.org/platform-support.html

第一次安装工具链时，`rustup`仅为您的*主机*平台——即您当前运行的体系结构和操作系统安装标准库。要编译到其他平台，必须安装其他平台，你必须安装*目标*平台。这是通过`rustup target add`命令完成。例如，要添加 Android 目标：

```console
$ rustup target add arm-linux-androideabi
info: downloading component 'rust-std' for 'arm-linux-androideabi'
info: installing component 'rust-std' for 'arm-linux-androideabi'
```

与`arm-linux-androideabi`目标安装后，您可以通过 Cargo 的`--target`标记，如`cargo build --target=arm-linux-androideabi`，构建安卓版本。

注意`rustup target add`仅为给定目标安装 Rust 标准库。通常还有其他跨平台编译所必需的工具，特别是链接器(linker)。例如，要跨平台编译到 Android，[安卓 NDK][android ndk]必须安装。未来，`rustup`也将提供安装 NDK 组件的帮助。

[android ndk]: https://developer.android.com/tools/sdk/ndk/index.html

要让不是默认工具链的工具链，安装目标，`rustup target add`请使用`--toolchain`的参数，就像这样：

```console
$ rustup target add --toolchain <toolchain> <target>...
```

要查看可用目标的列表，`rustup target list`。 要删除先前添加的目标，`rustup target remove`。

## 在 Windows 上，与 Rust 协手合作

`rustup`在 Windows 上的工作方式与在 Unix 上的工作方式相同，但对于 Windows 上的 Rust 开发人员来说，有一些特殊的考虑。正如[在 Rust 下载页面上提到][msvc-toolchain]，有两个[ABIs]在 Windows 上使用：由[Visual Studio]使用的原始（MSVC）ABI 和[GCC 工具链][gcc toolchain]使用的 GNU ABI。您需要哪种版本的 Rust 很大程度上取决于您想与之交互的 C/C++库：对于使用 VisualStudio 产生的软件的交互操作，用 MISC 构建的 Rust；对于使用 GNU 软件构建的交互操作，用 GNU 构建的[Mingw/MSys2 工具链][mingw/msys2 toolchain]。

针对 MSVC ABI 时，Rust 还需要[VisualStudio 2013（或更高版本）或 VisualC++生成工具 2019 的安装][vs]，这样 rustc 就可以使用它的链接器。对于 VisualStudio，请确保选中“C++工具”选项。对于 GNU 构建的基本使用，不需要额外的软件安装。

默认情况下，windows 的 rustup 将 rust 配置为针对 msvc abi，即目标三元为`i686-pc-windows-msvc`或`x86_64-pc-windows-msvc`取决于主机 Windows OS 的 CPU 架构。rustup 选择安装的工具链，除非通过[工具链规范][toolchain specification]选择，不然就在该目标三元主机上编译，并在默认情况下以该三元主机为目标。

你可以用`rustup set default-host`或在安装过程中改变这些行为。

例如，要明确选择 32 位 MSVC 主机：

```console
$ rustup set default-host i686-pc-windows-msvc
```

或者选择 64 位 GNU 工具链：

```console
$ rustup set default-host x86_64-pc-windows-gnu
```

[toolchain specification]: #工具链规范

由于 MSVC ABI 提供了与其他 Windows 软件的最佳的交互操作，因此建议在大多数情况下使用它。即使在默认情况下不使用 GNU 工具链，它始终可用。只需`rustup toolchain install`就能安装：

```console
$ rustup toolchain install stable-gnu
```

但是，您不需要切换工具链来支持所有 Windows 目标；单个工具链支持所有四个 x86 Windows 目标：

```console
$ rustup target add x86_64-pc-windows-msvc
$ rustup target add x86_64-pc-windows-gnu
$ rustup target add i686-pc-windows-msvc
$ rustup target add i686-pc-windows-gnu
```

[abis]: https://en.wikipedia.org/wiki/Application_binary_interface
[visual studio]: https://visualstudio.microsoft.com/downloads/
[gcc toolchain]: https://gcc.gnu.org/
[mingw/msys2 toolchain]: https://msys2.github.io/

## 与 发行商的 Rust 软件包共存

一些 Linux 发行商，会打包 Rust，您可能希望使用打包的工具链，例如用于发行商软件包开发。您可能还希望使用 rustup 管理的工具链，如 Nightly 或 Beta。通常，rustup 会抱怨，你已经在 /usr 中安装了 Rust，并拒绝安装。但是，您可以通过 rustup 安装 Rust，并使它与您的 发行商的 Rust 软件包共存。

当你最初安装 Rust 时，传递`-y`选项，使其忽略打包的 Rust 工具链，并将 rustup 管理的工具链安装到`~/.cargo/bin`. 将该目录添加到`\$PATH`（或者让 rustup 为你做这件事，通过不传递`--no-modify-path`参数）然后，要告诉 rustup 有关系统工具链的信息，请运行：

```console
rustup toolchain link system /usr
```

然后，您就可以使用`+system` 作为 Rust 的工具链，就像 ·+nightly`一样；例如，您可以`cargo +system build`，使用系统工具链构建，或者`cargo +nightly build`使用 nightly 构建。

如果您确实要，发行商软件包的开发，您应该使`+system`成为您的默认工具链：

```console
rustup default system
```

## 使用自定义工具链和本地构建(版本)

为了方便开发人员处理 Rust 本身，`rustup`能够管理本地构建的 Rust 工具链。告诉`rustup`，关于您的构建版本吧，请运行：

```console
$ rustup toolchain link my-toolchain path/to/my/toolchain/sysroot
```

例如，在 Ubuntu 上，您可以 clone `rust-lang/rust`，到`~/rust`，构建它，然后运行：

```console
$ rustup toolchain link myrust ~/rust/build/x86_64-unknown-linux-gnu/stage2/
$ rustup default myrust
```

现在，你可以说出`my-toolchain`，就像其他的`rustup`工具链一样。为你的每个工作区，创建一个`rustup`工具链，并简单使用`rustup run my-toolchain rustc`测试它们。

因为`rust-lang/rust`(项目)树不包括 Cargo，_当自定义工具链调用`cargo`，那它是不可用，`rustup`将尝试从一个发布版本使用`cargo`_，首选“nightly”，然后选择“beta”或“stable”。

## 使用网络代理

企业网络通常不具有直接的外部 HTTP 访问，但强制使用代理。如果您在这样的网络上，您可以通过在环境中，设置其 URL 来请求使用代理。在大多数情况下，设置`https_proxy`应该足够了。在类似 Unix 的系统上，像**bash**或**zsh**，您可以使用：

```bash
export https_proxy=socks5://proxy.example.com:1080 # or http://proxy.example.com:8080
```

在 Windows 上，命令为：

```cmd
set https_proxy=socks5://proxy.example.com:1080
```

如果需要更复杂的设置，rustup 支持**curl**程序，文档在[其手册][curlman]的环境章节。

`curl`的使用目前**已弃用**，但是，它仍然可以通过提供`rUSTUP_USE_CURL`环境变量，来使用，例如：

```bash
rUSTUP_USE_CURL=1 rustup update
```

注意有些版本的`libcurl`，会明确要求你放弃`http://`或`https://`环境变量中的前缀。例如，`export http_proxy=proxy.example.com:1080`（同样适用于 HTTPS）。如果您得到一个 SSL`unknown protocol`错误，来自`rustup`的`libcurl`，但是命令行`curl`命令工作正常，这可能是问题所在。

[curlman]: https://curl.haxx.se/docs/manpage.html

## 示例

| 命令                                                       | 说明                                             |
| ---------------------------------------------------------- | ------------------------------------------------ |
| `rustup default nightly`                                   | 将默认的工具链设置为最新的夜间                   |
| `rustup target list`                                       | 列出活动工具链的所有可用目标                     |
| `rustup target add arm-linux-androideabi`                  | 安装 Android 目标                                |
| `rustup target remove arm-linux-androideabi`               | 移除 Android 目标                                |
| `rustup run nightly rustc foo.rs`                          | 不考虑活动的工具链，夜间运行                     |
| `rustc +nightly foo.rs`                                    | 运行夜间编译器的简写方法                         |
| `rustup run nightly bash`                                  | 运行为夜间编译器配置的 shell                     |
| `rustup default stable-msvc`                               | 在 Windows 上，使用 MSVC 工具链而不是 GNU        |
| `rustup override set nightly-2015-04-01`                   | 对于当前目录，使用特定日期的夜间版               |
| `rustup toolchain link my-toolchain "C:\RustInstallation"` | 通过符号链接现有安装，来安装自定义工具链         |
| `rustup show`                                              | 显示将在当前目录中使用的工具链                   |
| `rustup toolchain uninstall nightly`                       | 卸载给定的工具链                                 |
| `rustup toolchain help`                                    | 显示`help`子命令的页面（如`toolchain`）          |
| `rustup man cargo`                                         | （_仅限于 Unix_）查看给定命令的手册（如`cargo`） |

## 环境变量

- `rUSTUP_HOME`（默认：`~/.rustup`或`%USERPROFILE%/.rustup`）设置 Rust 根文件夹，用于存储已安装的工具链和配置选项。

- `rUSTUP_TOOLCHAIN`（默认：无）如果设置，将覆盖用于所有 Rust 工具调用的工具链。应安装具有此名称的工具链，否则调用将失败。

- `rUSTUP_DIST_SERVER`（默认：`https://static.rust-lang.org`）设置用于下载与 rust 相关的静态资源的根 URL。您可以将其更改为使用本地镜像，或者从临时目录测试二进制文件。

- `rUSTUP_DIST_ROOT`（默认：`https://static.rust-lang.org/dist`）已弃用。使用`rUSTUP_DIST_SERVER`替代。

- `rUSTUP_UPDATE_ROOT`（默认`https://static.rust-lang.org/rustup`）设置下载自我更新的根 URL。

- `rUSTUP_IO_THREADS` _不稳定的_（默认为报告的 CPU 计数）。设置执行关闭 IO 的线程数。设置为`disabled`强制单线程 IO，进行故障排除，或强制为任意数字，覆盖自动检测。

- `rUSTUP_TRACE_DIR` _不稳定的_（默认：无跟踪）启用跟踪并确定目录是跟踪可以写入的。跟踪的形式为 PID.trace。跟踪可以被[跟踪查看器][tv]读取。

[tv]: （<https://github.com/catapult-project/catapult/blob/master/tracing/README.md>）

- `rUSTUP_UNPACK_RAM` _不稳定的_（默认为 400M，最小为 100M）限制了 rustup 在解包时，用于 IO 任务的 RAM 量。

## 其他安装方法

主要安装方法，如<https://rustup.rs>中所述，因平台而异：

- 在 Windows 上，下载并运行[为`i686-pc-windows-gnu`目标生成的 rustup-init.exe][setup]。 一般来说，这是一个，应该安装在 Windows 上 的 rustup 构建版本。尽管是针对 GNU 工具链构建的，_如果检测到安装了 msvc，则由 rustup 生成的 Windows 构建版本将为 msvc 工具链安装 rust。_ 如果您喜欢安装 GNU 工具链或 x86_64 工具链，默认情况下，可以在安装时，以交互方式或使用`--default-host`标志，或安装后通过`rustup set default-host`修改。
- 在 Unix 上，运行`curl https://sh.rustup.rs -sSf | sh`在你的 shell 里。此下载和运行[`rustup-init.sh`]，从而为你平台，下载并运行正确版本的`rustup-init`可执行文件。

[setup]: https://static.rust-lang.org/rustup/dist/i686-pc-windows-gnu/rustup-init.exe
[`rustup-init.sh`]: https://static.rust-lang.org/rustup/rustup-init.sh

`rustup-init`接受可以传递 shell 脚本传递的参数。一些例子：

```console
$ curl https://sh.rustup.rs -sSf | sh -s -- --help
$ curl https://sh.rustup.rs -sSf | sh -s -- --no-modify-path
$ curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain nightly
$ curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain none
```

如果您愿意，可以直接下载`rustup-init`，请您选择的平台：

- [aarch64-linux-android](https://static.rust-lang.org/rustup/dist/aarch64-linux-android/rustup-init)
- [aarch64-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/aarch64-unknown-linux-gnu/rustup-init)
- [arm-linux-androideabi](https://static.rust-lang.org/rustup/dist/arm-linux-androideabi/rustup-init)
- [arm-unknown-linux-gnueabi](https://static.rust-lang.org/rustup/dist/arm-unknown-linux-gnueabi/rustup-init)
- [arm-unknown-linux-gnueabihf](https://static.rust-lang.org/rustup/dist/arm-unknown-linux-gnueabihf/rustup-init)
- [armv7-linux-androideabi](https://static.rust-lang.org/rustup/dist/armv7-linux-androideabi/rustup-init)
- [armv7-unknown-linux-gnueabihf](https://static.rust-lang.org/rustup/dist/armv7-unknown-linux-gnueabihf/rustup-init)
- [i686-apple-darwin](https://static.rust-lang.org/rustup/dist/i686-apple-darwin/rustup-init)
- [i686-linux-android](https://static.rust-lang.org/rustup/dist/i686-linux-android/rustup-init)
- [i686-pc-windows-gnu](https://static.rust-lang.org/rustup/dist/i686-pc-windows-gnu/rustup-init.exe)
- [i686-pc-windows-msvc](https://static.rust-lang.org/rustup/dist/i686-pc-windows-msvc/rustup-init.exe)<sup>[†](#vs2019)</sup>
- [i686-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/i686-unknown-linux-gnu/rustup-init)
- [mips-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/mips-unknown-linux-gnu/rustup-init)
- [mips64-unknown-linux-gnuabi64](https://static.rust-lang.org/rustup/dist/mips64-unknown-linux-gnuabi64/rustup-init)
- [mips64el-unknown-linux-gnuabi64](https://static.rust-lang.org/rustup/dist/mips64el-unknown-linux-gnuabi64/rustup-init)
- [mipsel-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/mipsel-unknown-linux-gnu/rustup-init)
- [powerpc-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/powerpc-unknown-linux-gnu/rustup-init)
- [powerpc64-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/powerpc64-unknown-linux-gnu/rustup-init)
- [powerpc64le-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/powerpc64le-unknown-linux-gnu/rustup-init)
- [s390x-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/s390x-unknown-linux-gnu/rustup-init)
- [x86_64-apple-darwin](https://static.rust-lang.org/rustup/dist/x86_64-apple-darwin/rustup-init)
- [x86_64-linux-android](https://static.rust-lang.org/rustup/dist/x86_64-linux-android/rustup-init)
- [x86_64-pc-windows-gnu](https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-gnu/rustup-init.exe)
- [x86_64-pc-windows-msvc](https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe)<sup>[†](#vs2019)</sup>
- [x86_64-unknown-freebsd](https://static.rust-lang.org/rustup/dist/x86_64-unknown-freebsd/rustup-init)
- [x86_64-unknown-linux-gnu](https://static.rust-lang.org/rustup/dist/x86_64-unknown-linux-gnu/rustup-init)
- [x86_64-unknown-linux-musl](https://static.rust-lang.org/rustup/dist/x86_64-unknown-linux-musl/rustup-init)
- [x86_64-unknown-netbsd](https://static.rust-lang.org/rustup/dist/x86_64-unknown-netbsd/rustup-init)

<a name="vs2019">γ</a>`rustup`的 MSVC 构建，另外需要[VisualStudio 2019 或 VisualC++生成工具 2019 的安装][vs]. 对于 VisualStudio，请确保选中“C++工具”选项。对于 GNU 构建的基本使用，不需要额外的软件安装。

[vs]: https://visualstudio.microsoft.com/downloads/

您可以从`https://static.rust-lang.org/rustup/archive/{rustup-version}/{target-triple}/rustup-init[.exe]`中获取旧版本

要从源代码安装，只需运行`cargo run --release`。请注意，目前 rustup 仅在夜间 Rust 的基础上构建，安装 rustup 工具链后，它通过`PATH`环境变量的`~/.cargo/bin`，取代任何现有的工具链。

## 安全

`rustup`对非偏执狂来说足够安全，但是[仍需努力][s]。`rustup`通过 HTTPS 执行所有下载，但尚未验证下载的签名。

[s]: https://github.com/rust-lang/rustup.rs/issues?q=is%3Aopen+is%3Aissue+label%3Asecurity

从 1.18.4 开始， 安装 带有 honor umask 文件模式，如果需要非常严格的控制，请使用 umask。

## 常见问题解答

### 这是官方的 Rust 项目吗？

对。rustup 是一项官方的 Rust 工程。是<https://www.rust-lang.org>建议的下载方式。

### 这与 multirust 有什么关系？

rustup 是[multirust]的成功案例。rustup 从 multirst-rs 开始，它是 multirst 重写， 从 shell 脚本到 rust 的覆盖。现在由[Diggory Blake]和 Rust 项目维护。

### rustup 可以下载 Rust 源代码吗？

可通过运行`rustup component add rust-src`获得 Rust 源。它将被下载到当前工具链的`<toolchain root>/lib/rustlib/src/rust`目录。

### rustup 失败，出现 Windows 错误 32

如果 rustup 因 Windows 错误 32 而失败，则可能是后台防病毒扫描造成的。禁用防病毒扫描程序，然后重试。

[multirust]: https://github.com/brson/multirust
[diggory blake]: https://github.com/Diggsey

### 我得到"error: could not remove 'rustup-bin' file: 'C:\Users\USER\\.cargo\bin\rustup.exe'"

如果 rustup 不能以这种方式自我更新，通常是因为 RLS 正在运行（您的编辑器打开并运行 RLS）。解决方案是停止 RLS（关闭编辑器），然后重试。

## 许可证

版权所有 Diggory Blake，Mozilla 公司和 rustup 贡献者。

根据以下任何一项获得许可

- Apache 许可证，2.0 版，（[LICENSE-APACHE](LICENSE-APACHE)或<http://www.apache.org/licenses/LICENSE-2.0>）
- MIT 许可证（[LICENSE-MIT](LICENSE-MIT)或<http://opensource.org/licenses/MIT>）

由您选择。

<!-- Badges -->

[travis-url]: https://travis-ci.com/rust-lang/rustup.rs
[travis-badge]: https://travis-ci.com/rust-lang/rustup.rs.svg
[appveyor-url]: https://ci.appveyor.com/project/rust-lang-libs/rustup-rs
[appveyor-badge]: https://ci.appveyor.com/api/projects/status/github/rust-lang/rustup.rs?svg=true
