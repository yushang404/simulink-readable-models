# Simulink Readable Models

A Codex skill for readable, runnable Simulink models. It guides region-based layouts, port alignment, clean orthogonal wiring, consistent labels, and simulation verification.

一份面向原生 Simulink 建模的中文 Skill，将可读性要求转化为具体操作顺序与验收标准。

## 核心规则

- 中小型控制模型优先同层展开，用功能区域组织，保留必要的执行边界。
- 区域标题放大、加粗、顶部居中。
- 先对齐实际端口，再连接；能直连就直连，反馈走预留通道。
- 模块名称统一放在上下留白处，文字不压线、不遮挡。
- 明确信号单位、维度、采样周期及坐标约定，参数集中初始化。
- 分别验证连接、实际仿真、真实画面和保存重开结果。
- 用户明确要求纯 Simulink 时，使用原生模块及模型内参数，避免增加外部脚本运行依赖。

## 安装与使用

将此仓库克隆到 Codex 的个人 skills 目录，文件夹名称保持为 `simulink-readable-models`。Windows PowerShell 示例：

```powershell
git clone https://github.com/yushang404/simulink-readable-models.git "$env:USERPROFILE\.codex\skills\simulink-readable-models"
```

调用：

```text
使用 $simulink-readable-models，按功能区域整理当前模型，统一标题和块名位置，清理走线，并实际运行后查看画面。
```

需要能够访问 MATLAB/Simulink 的建模工具或桌面操作环境；本 Skill 本身是工作说明，不是自动排版插件。`building-simulink-models` 可作为可选配合项，未捆绑第三方 Skill。

## 文件

- [SKILL.md](SKILL.md)：建模规范、执行顺序与完成标准。
- [布局与走线](references/layout-patterns.md)：排布示例、标签及区域标题处理。
- [车辆接口](references/vehicle-interfaces.md)：车辆/MPC/CarSim 场景下的接口核对。
- [agents/openai.yaml](agents/openai.yaml)：Codex 展示信息和默认调用提示。

## 验证边界

格式检查不证明模型运行正确；仿真通过不证明画面整洁。每个模型都需要实际运行与视觉检查。文档中的 MATLAB R2026a Update 5 观察仅适用于对应历史示例，不代表跨版本保证。本仓库不包含仿真器、模型数据或其许可证。

## 许可证

[MIT](LICENSE)。欢迎通过 Issues 和 Pull Requests 提交排布问题与改进建议。
