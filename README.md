# Visual Studio Code 原始碼解析筆記


# 目錄

```
├── build         # gulp编译构建脚本
├── cli
├── extensions    # 内置插件
├── product.json  # App meta信息
├── out           # 编译输出目录
├── remote
├── resources     # 平台相关静态资源
├── scripts       # 工具脚本，开发/测试
├── src           # 源码目录
├── test          # 测试套件
└── src/vs
    ├── base        # 通用工具/协议和UI库
    │   ├── browser # 基础UI组件，DOM操作
    │   ├── common  # diff描述，markdown解析器，worker协议，各种工具函数
    │   ├── node    # Node工具函数
    │   ├── parts   # IPC协议（Electron、Node），quickopen、tree组件
    │   ├── test    # base单测用例
    │   └── worker  # Worker factory和main Worker（运行IDE Core：Monaco）
    ├── code        # VSCode主运行窗口
    ├── editor        # IDE代码编辑器
    |   ├── browser     # 代码编辑器核心
    |   ├── common      # 代码编辑器核心
    |   ├── contrib     # vscode 与独立 IDE共享的代码
    |   └── standalone  # 独立 IDE 独有的代码
    ├── platform      # 支持注入服务和平台相关基础服务（文件、剪切板、窗体、状态栏）
	├── server
    ├── workbench     # 工作区UI布局，功能主界面
    │   ├── api              #
    │   ├── browser          #
    │   ├── common           #
    │   ├── contrib          #
    │   ├── electron-browser #
    │   ├── services         #
    │   └── test             #
    ├── loader.js     # AMD loader（用于异步加载AMD模块）
```


# src目錄
```
├── bootstrap-amd.js    # 子进程实际入口
├── bootstrap-fork.js   #
├── bootstrap-window.js #
├── bootstrap.js        # 子进程环境初始化
├── buildfile.js        # 构建config
├── cli.js              # CLI入口
├── main.js             # 主进程入口
├── paths.js            # AppDataPath与DefaultUserDataPath
├── typings
│   └── xxx.d.ts        # ts类型声明
└── vs
    ├── base            # 定义基础的工具方法和基础的 DOM UI 控件
    │   ├── browser     # 基础UI组件，DOM操作、交互事件、DnD等
    │   ├── common      # diff描述，markdown解析器，worker协议，各种工具函数
    │   ├── node        # Node工具函数
    │   ├── parts       # IPC协议（Electron、Node），quickopen、tree组件
    │   ├── test        # base单测用例
    │   └── worker      # Worker factory 和 main Worker（运行IDE Core：Monaco）
    ├── code            # VSCode Electron 应用的入口，包括 Electron 的主进程脚本入口
    │   ├── electron-browser # 需要 Electron 渲染器处理API的源代码（可以使用 common, browser, node）
    │   ├── electron-main    # 需要Electron主进程API的源代码（可以使用 common, node）
    │   ├── node        # 需要Electron主进程API的源代码（可以使用 common, node）
    │   ├── test
    │   └── code.main.ts
    ├── editor          # Monaco Editor 代码编辑器：其中包含单独打包发布的 Monaco Editor 和只能在 VSCode 的使用的部分
    │   ├── browser     # 代码编辑器核心
    │   ├── common      # 代码编辑器核心
    │   ├── contrib     # vscode 与独立 IDE共享的代码
    │   ├── standalone  # 独立 IDE 独有的代码
    │   ├── test
    │   ├── editor.all.ts
    │   ├── editor.api.ts
    │   ├── editor.main.ts
    │   └── editor.worker.ts
    ├── platform        # 依赖注入的实现和 VSCode 使用的基础服务 Services
    ├── workbench       # VSCode 桌面应用程序工作台的实现
    ├── buildunit.json
    ├── css.build.js    # 用于插件构建的CSS loader
    ├── css.js          # CSS loader
    ├── loader.js       # AMD loader（用于异步加载AMD模块，类似于require.js）
    ├── nls.build.js    # 用于插件构建的 NLS loader
    └── nls.js          # NLS（National Language Support）多语言loader
```
