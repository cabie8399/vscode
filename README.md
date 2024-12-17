# Visual Studio Code 原始碼解析筆記


# 目錄

```
├── build         # gulp编译构建脚本
├── cli
├── extensions    # 内置插件
├── product.json  # App meta信息
├── remote
├── resources     # 平台相关静态资源
├── scripts       # 工具脚本，开发/测试
├── src           # 源码目录
├── test
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
