# My Awesome WebAssembly [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
该仓库会持续更新，追踪最新活动与生态动态，后续增加英文版本
> 不只是记录社区动态，在其他文件中也会更新个人的一些总结和笔记

* [Other Awesome Webassebmly Repos](#other-awesome)
* [WASM 规范](#wasm)
    * [语言规范](#语言规范)
    * [Component Model](#component-model)
    * [WASI](#wasiwebassembly-system-interface)
    * [CNCF WASM Working Group](#cncf-wasm-working-group)
* [WASM Runtimes](#Runtime)
* [社区/厂商](#社区厂商)
* [优秀项目](#优秀项目与工具)
    * [Containerd&WASM](#containerd--wasm)
    * [WASM 应用框架](#wasm-应用框架)
    * [WASM 平台](#wasm-平台)
* [工具](#工具库)
    * [WebAssembly 社区](webassebmly-社区)
    * [字节码联盟](字节码联盟)
    * [其它](#其它)
* [Demo](#Demo)
* [活动/会议]()

## Other Awesome
WASM 处于快速发展的阶段，这里只包含活跃的 Awesome 仓库
* [Awesome Wasm](https://github.com/mbasso/awesome-wasm)
* [WebAssembly资料精选 - 中文版](https://github.com/chai2010/awesome-wasm-zh#%E6%8A%80%E6%9C%AF%E6%96%87%E7%AB%A0)
* [Awesome WebAssembly Runtimes](https://github.com/appcypher/awesome-wasm-runtimes)
* [Awesome WebAssembly Languages](https://github.com/appcypher/awesome-wasm-langs)
* [Awesome Rust and Webassembly](https://github.com/rustwasm/awesome-rust-and-webassembly)
* [Awesome-WebAssembly-Applications](https://github.com/mcuking/Awesome-WebAssembly-Applications)

## WASM 规范

新增提案流程：<https://github.com/WebAssembly/meetings/blob/main/process/proposal.md>

提案标准化流程：<https://github.com/WebAssembly/meetings/blob/main/process/phases.md>

### [语言规范](https://github.com/WebAssembly/spec)

<https://webassembly.github.io/spec/core/>

**`WASM`** 二进制格式： <https://webassembly.github.io/spec/core/binary/index.html>

**`WAT`** 文本格式：<https://webassembly.github.io/spec/core/text/index.html>

高级目标：<https://github.com/WebAssembly/design/blob/main/HighLevelGoals.md>

常见问题：<https://github.com/WebAssembly/design/blob/main/FAQ.md>

在 [WebAssembly/design](https://github.com/WebAssembly/design) 仓库 Issue 中记录新的规范提案，在 [WebAssebmly/proposals](https://github.com/WebAssembly/proposals) 仓库中跟踪提案的进度

### [Component Model](https://github.com/WebAssembly/component-model)

高级设计：<https://github.com/WebAssembly/component-model/tree/main/design/high-level>

`WITX` 格式（请使用 `WIT`）：<https://github.com/WebAssembly/WASI/blob/main/legacy/tools/witx-docs.md>

**`WIT`** 格式: <https://github.com/WebAssembly/component-model/blob/main/design/mvp/WIT.md>

格式进化：`WITX` -> `WAI` -> `WIT`
*   [\[wit-bindgen #101\] Rename "witx" to "wai"](https://github.com/bytecodealliance/wit-bindgen/pull/101)&#x20;
*   [\[wit-bindgen #107\] Rename \*.wai to \*.wit](https://github.com/bytecodealliance/wit-bindgen/pull/107)
*   [\[WASI #452\] Why the WAI? Please amend](https://github.com/WebAssembly/WASI/issues/452)


WIT 中的 World 是什么，WASI 的最新 API 需要定义 WIT world：<https://blog.sunfishcode.online/what-is-a-world/>
视频：
*   <https://www.youtube.com/watch?v=phodPLY8zNE>

## [WASI(WebAssembly System Interface)](https://github.com/WebAssembly/WASI)
高级目标：<https://github.com/WebAssembly/WASI/tree/main#wasi-high-level-goals>

提案列表：<https://github.com/WebAssembly/WASI/blob/main/Proposals.md>

字节码联盟文档：<https://github.com/bytecodealliance/wasmtime/blob/main/docs/WASI-documents.md>

---

WASI 将 Preview2 的 API 定义由 WITX 迁移到 WIT 格式：<https://github.com/WebAssembly/WASI/blob/main/docs/WitInWasi.md>

使用 `WIT` 格式后， [WASI](https://github.com/Iceber/awesome-webassembly) 仓库的意义更多是跟踪 WASI API 提案的标准化

旧版(Preview1) WASI 文档： <https://github.com/WebAssembly/WASI/tree/27faa3a87f0ef9e48cbbf5aaafb9a0eacd297ea1/phases>

可以通过 [bytecodealliance/preview2-prototyping](https://github.com/bytecodealliance/preview2-prototyping) 来以 preview1 的方式调用 preview2 函数
> preview1 的模块名称为 *wasi_snapshot_preview1*

### CNCF WASM Working Group
**Google Doc**: https://docs.google.com/document/d/1bcMK0layzDCiKmpdIB7gShMv7nuqw3TkxUeLcxx91VU/edit#heading=h.g4ksaonfmtzr

**Slack**: [#wg-wasm](https://cloud-native.slack.com/archives/C056EDRH4PJ)

## Runtime
| Name                                                           | Language  | Compiler Framework                 | Compilation/ Execution Modes | 亮点                                                 |
| :------------------------------------------------------------- | :-------- | :--------------------------------- | :--------------------------- | :------------------------------------------------- |
| [Wasmtime](https://github.com/CraneStation/wasmtime)           | Rust      | Cranelift                          | JIT                          | bytecode alliance 主导，新功能增加比较块                      |
| [WAMR](https://github.com/bytecodealliance/wasm-micro-runtime) | C         | Custom                             | Interpreted, AOT, JIT        | bytecode alliance 主导，主打微型运行时，占用资源更少                |
| [WasmEdge](https://github.com/WasmEdge/WasmEdge)               | C++       | LLVM                               | Interpreted, AOT             | 在 host function 支持更加丰富                             |
| [Wasmer](https://github.com/wasmerio/wasmer)                   | Rust, C++ | Singlepass,Cranelift(Default),LLVM | JIT, AOT                     | 使用 singlepass 时可以无依赖运行 wasm                        |
| [wasm3](https://github.com/wasm3/wasm3)                        | C         | Custom                             | Interpreted                  | 6k repo，支持更多的架构平台                                  |
| [Wasmi](https://github.com/paritytech/wasmi)                   | Rust      | Custom                             | Interpreted                  | <https://github.com/paritytech> 开源的运行时，基本只在自己项目中使用 |
| [wazero](https://wazero.io/)                                   | Go        | Custom                             | Interpreted, JIT             | golang 实现                                          |

> [wasmo](https://github.com/appcypher/wasmo) 一个 Rust 实现的，基于 LLVM 的运行时，功能较少可以学习参考

**2023 主流运行时的压测报告**：https://00f.net/2023/01/04/webassembly-benchmark-2023/

## 社区/厂商

|   社区/厂商                                      |  核心产品                              |
| :----------------------------------------------- | :------------------------------------- |
｜[CNCF TAG-Runtime Wasm Group](https://github.com/cncf/tag-runtime/issues/58) | https://docs.google.com/document/d/1bcMK0layzDCiKmpdIB7gShMv7nuqw3TkxUeLcxx91VU/edit#
| [wasmCloud](https://wasmcloud.com/)              | wasm 平台                              |
| [Second State](https://www.secondstate.io/)      | wasmedge                               |
| [Deis Labs](https://deislabs.io/)                | spiderlightning, containerd-wasm-shims |
| [Fermyon](https://fermyon.com/)                  | spin                                   |
| [cosmonic](https://cosmonic.com/)                |                                        |
| [contentful](https://www.contentful.com/)        |                                        |
| [taubyte](https://taubyte.com/)                  | wasm 平台                              |
| [Loophole Labs](https://github.com/loopholelabs) | scale                                  |
| [Suborbital](https://github.com/suborbital)      | <https://github.com/suborbital/e2core> |
| [Wasm Labs](https://wasmlabs.dev/)               | <https://wasmlabs.dev/projects/>       |


## 优秀项目与工具

*   [cisco-open/wasm-kernel-module](https://github.com/cisco-open/wasm-kernel-module) **将 wasm 运行在内核中** 

    <https://github.com/cisco-open/wasm-kernel-module-cli>

*   [KWasm/kwasm-operator](https://github.com/KWasm/kwasm-operator) **kubernetes wasm operator**

    将 wasm 相关依赖安装在节点中，方便用户部署 WASM 应用

    <https://github.com/KWasm/kwasm-node-installer>

*   [extism/extism](https://github.com/extism/extism) **基于 WASM 的插件系统**

### Containerd & WASM

*   [containerd/runwasi](https://github.com/containerd/runwasi) containerd 官方 shim，提供 wasm shim 框架以及 wasmtime\&wasmedge shim 二进制
*   [deislabs/containerd-wasm-shims](https://github.com/deislabs/containerd-wasm-shims) deislabs 提供的 shim，支持 `slight`, `spin`
*   [Mossaka/containerd-wasm-shims](https://github.com/Mossaka/containerd-wasm-shims)mossaka 实现的 shim，支持 `spin`, `cloudevents host`, asp.net，已经不太活跃了
*   [second-state/runwasi](https://github.com/second-state/runwasi) 针对 WasmEdge 扩展后的 runwasi，docker 实际使用该版本

### WASM 应用框架

*   [rustwasm/gloo](https://github.com/rustwasm/gloo) 主要用于 web 端的框架

    文档：<https://github.com/rustwasm/book>

*   [loopholelabs/scale-cli](https://github.com/loopholelabs/scale-cli) 高级 wasm 应用框架与运行时，Serverless 服务框架

    文档：<https://scale.sh/docs/getting-started/overview>

*   [deislabs/spiderlightning](https://github.com/deislabs/spiderlightning) 包含一组 WIT 定义和相关实现，可以更快的实现 wasm 应用，而且对环境依赖更少

    Demo: [https://github.com/Mossaka/chat-app-slight](https://github.com/Mossaka/chat-app-slight/tree/main)

*   [deislabs/wagi](https://github.com/deislabs/wagi) 快速实现 http handler 的 wasm 模块

*   [fermyon/spin](https://github.com/fermyon/spin) 构建和运行 wasm 的开发工具

### wasm 平台

*   **\[Dei Labs]** WASM PAAS 平台

    Website: <https://github.com/deislabs/hippo>

*   **\[wasmCloud]** 简单的全面的 wasm 开发运行平台

    Website: <https://github.com/wasmCloud/wasmCloud>

*   **\[Cosmonic]** wasm 平台

    Website: <https://cosmonic.com/>

## 工具(库)

### WebAssembly 社区

<https://github.com/WebAssembly/wabt>

<https://github.com/WebAssembly/wasi-testsuite>

### 字节码联盟

<https://github.com/bytecodealliance/cargo-component>

<https://github.com/bytecodealliance/wasm-tools>

<https://github.com/bytecodealliance/wit-bindgen>

### 其他
*   [dphilla/marcotte-wasm](https://github.com/dphilla/marcotte-wasm) 创建于 host 无关的系统调用中间层
*   [loopholelabs/wasm-toolkit](https://github.com/loopholelabs/wasm-toolkit) 包含了类似 strace 的命令的工具集，可以查看 wasm 模块对 外部调用/wasi 的依赖
*   [peterhuene/wasmbuilder.app](https://github.com/peterhuene/wasmbuilder.app) 组合 component，生成新的 component

    Demo: <https://github.com/peterhuene/wasmday-demo> 使用 [viceroy](https://github.com/fastly/Viceroy) 来运行
    Video: <https://www.youtube.com/watch?v=JCIwpc7x4jU&list=PLj6h78yzYM2Pdj8vnO0wfFyKcbKNy3e5j&index=18>

*   [engineerd/wasm-to-oci](https://github.com/engineerd/wasm-to-oci) 从 oci 镜像中获取 wasm 模块

### Demo

<https://github.com/radu-matei/wasm-components-example>
