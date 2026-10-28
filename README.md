# PIN Cephalometric Analysis — Codex Skill

中文 | [English](#english)

一个供 Codex 使用的工作流程技能，用于维护、排查和扩展 PIN 网站中的头影测量分析模块。技能说明涵盖本地研究性 AI 标点、人工复核与描绘、测量、病例保存和经确认的数据回填。

本仓库只包含技能指南（`SKILL.md`、`references/` 和 `agents/`）。它依赖**另行取得的 PIN 项目**，不包含网站源码、AI 模型或患者资料，也不能独立运行。使用前请确保 Codex 能访问您的 PIN 项目；若项目位置不同，请在请求中提供路径。

## 安装与使用

在终端执行：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/Pintoteeth/pin-cephalometric-analysis.git ~/.codex/skills/pin-cephalometric-analysis
```

如果目标目录已存在，请先备份或选择其他位置，避免覆盖已有技能。然后在 Codex 中调用，例如：

```text
$pin-cephalometric-analysis 帮我检查头影测量模块的标点和测量流程
```

若新安装的技能未立即出现，请开启新的 Codex 会话。

## 使用边界

- 本技能及其说明不是独立应用，也不是经过临床验证的诊断工具。患者影像和病例默认保留在本机；向外部服务上传前需获得明确授权。
- 现有 AI 模型仅供研究和教学，其结果不得用于诊断或治疗。使用模型前应查阅对应模型卡、许可证及适用限制；人工复核也不能消除这些限制。
- 本仓库的 MIT 许可仅适用于本仓库内容。PIN 项目、第三方代码、模型及其运行组件分别受各自许可和使用条件约束。

## License

[MIT](LICENSE)

---

## English

A Codex skill for maintaining, troubleshooting, and extending the cephalometric analysis module in the PIN website. Its workflow covers local research AI landmarks, manual review and tracing, measurements, case persistence, and explicitly confirmed data transfer.

This repository contains **skill guidance only** (`SKILL.md`, `references/`, and `agents/`). It requires a separately obtained PIN project. It does not include the website source, AI models, or patient data, and cannot run independently. Ensure Codex can access your PIN project and supply its path if needed.

### Install and use

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/Pintoteeth/pin-cephalometric-analysis.git ~/.codex/skills/pin-cephalometric-analysis
```

If the destination already exists, back it up or choose another location to avoid overwriting an existing skill. Invoke it in Codex, for example:

```text
$pin-cephalometric-analysis Review the landmark and measurement workflow in my PIN project.
```

Start a new Codex session if the newly installed skill is not immediately available.

### Boundaries

- This skill is neither a standalone application nor a clinically validated diagnostic tool. Keep patient images and case files local by default; obtain explicit authorization before uploading them to an external service.
- The existing AI model is restricted to research and education; its output must not be used for diagnosis or treatment. Consult the relevant model card, license, and restrictions before use. Manual review does not remove those restrictions.
- The MIT license applies only to this repository. The PIN project, third-party code, models, and runtime components are subject to their own licenses and terms.
