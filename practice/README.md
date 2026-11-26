# Pi Agent 实践课 1-5 作业

个人信息：王陈业（Wangchenye） / GitHub 登录名 `rtzsh`

小组代码仓库：https://github.com/shizishizi111/pi-hunnu-2026

| 实践 | 报告 | 主要内容 |
| --- | --- | --- |
| 实践课1 | [01-pi-agent.md](01-pi-agent.md) | 安装 Pi 客户端、配置模型、模型与思考级别切换、`@` 引用文件、粘贴图片、安装插件 |
| 实践课2 | [02-source-analysis.md](02-source-analysis.md) | 源码获取、11 个子模块分析、依赖关系图与三个问题 |
| 实践课3 | [03-source-build.md](03-source-build.md) | 环境检查、装依赖、本地编译、产物验证、源码入口运行 |
| 实践课4 | [04-agent-loop-trace.md](04-agent-loop-trace.md) | 给 Agent 循环加日志、重新编译、直接问答与读取文件对比 |
| 实践课5 | [05-tool-call-and-session.md](05-tool-call-and-session.md) | 单轮工具调用时序图、恢复旧会话与新建会话对照 |

截图都在 [images/](images/) 目录，报告内用相对路径引用。

## 环境

- Windows 11 + PowerShell
- Node.js v24.18.0 / npm 11.16.0
- Git 2.54.0
- Pi 客户端 v1.6.1（全局安装），小组源码版本 1.5.2

## 说明

- 报告中所有截图均为本机实际运行时截屏，命令、输出、报错都是真实结果。
- 实践 1 的选做项（PPT Skill）没有做，报告里已注明未做及原因，没有伪造。
- 涉及 API Key 的地方一律用环境变量传入，报告与截图中不包含密钥。
