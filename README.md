# thesis skills

> *把流程交给技能，把学术判断留给你。*

面向学位论文、期刊投稿与系统综述的 Agent Skills 集合。每个技能都是 `skills/<技能名>/SKILL.md`，供 OpenCode、Cursor、Claude Code、Trae 等环境中的 AI 读取后执行。

---

## 先看这个：`agents.md`

`skills/` 提供通用能力；`agents.md` 决定你的项目如何落地（路径、初始化信息、路由、长期偏好）。

- 你可以手动维护 `agents.md`。
- 也可以让 AI 先生成草案，你确认后再写入。
- 没有 `agents.md` 时，Agent 只能给通用建议；有它后才能稳定复用项目上下文。

一句话：`skills` 是能力库，`agents.md` 是项目控制面板。

---

## 快速开始（3 步）

### 1) 获取仓库

```bash
git clone <你的仓库 URL> thesis-skills
```

也可作为论文项目的 `git submodule` 使用，便于版本固定与更新。

### 2) 让 Agent 能读到 `SKILL.md`

- 通用：仓库在工作区内，路径为 `skills/<技能名>/SKILL.md`。
- Cursor：将 `skills/` 复制到 `.cursor/skills/`，或将 `.cursor/skills` 做 junction 指向本仓库 `skills/`。
- OpenCode 等：如约定 `.opencode/skills/`，用复制或符号链接映射。

### 3) 接上驾驶舱

把 [agents.md](agents.md) 放到你的论文项目根目录，填写占位符与初始化状态。首次协作建议按第 0 节先问一轮。

---

## 用户场景：怎么开口

### 场景 1：刚起步，不知道先写哪章

```text
我在写硕士论文，当前只有零散笔记和几篇核心文献。
请先给我“先写什么、后写什么”的顺序，并给每章 3-5 个写作要点。
若需要长期约定，请先问我再写入 agents.md。
```

### 场景 2：文献综述只要“述”不要“展望”

```text
我要写相关研究，只做“问题—方法—证据”的综述，不要末章展望。
请选一个技能并先读取 SKILL.md，再把下面内容改成可直接进正文的综述段落。
```

### 场景 3：提交前质量自查

```text
我准备提交当前稿件。请按“结构-证据-术语-格式”做一轮质量自查，
给我“问题类型 + 修改优先级 + 可直接替换句子/操作建议”。
```

### 场景 4：只改局部，不动整章

```text
不要改整章，只改这一段（粘贴）。目标：压到 320 字，
保留结论和数据，不改变原意，输出可直接粘贴版本。
```

---

## 多轮对话模板（推荐）

多轮通常比一次性大请求更稳定：

1. 第一轮只说清“这一步要什么”；
2. 第二轮只推进一个子目标；
3. 第三轮做术语/字数/引用/格式精修。

### 第一句话模板

```text
我在写【论文类型】，当前卡在【章节/任务】。
材料在【路径或粘贴正文】，目标是【字数/风格/格式】。
请先选一个技能并读取 SKILL.md 再执行；需要长期约定请先问我再写入 agents.md。
```

### 路线 A：学位论文（3 轮）

- 第 1 轮：先给章节顺序与每节目标。
- 第 2 轮：只写某一小节，给字数与保留项。
- 第 3 轮：不改观点，做压缩与一致性检查。

### 路线 B：期刊综述（4 轮）

- 第 1 轮：先给综述框架（只述不展望）。
- 第 2 轮：把文献摘要归到各小节。
- 第 3 轮：先写单节正文。
- 第 4 轮：补引用位并标待补 DOI。

### 路线 C：课程报告（3 轮）

- 第 1 轮：按老师模板列提纲。
- 第 2 轮：只写“分析”部分。
- 第 3 轮：统一语体并给摘要。

实用原则：每轮尽量只包含 **一个目标 + 一段材料 + 一个约束**。

---

## 技能索引（速查）

详细触发条件与组合路径以 [agents.md](agents.md) 为准。

### 文献与综述

- `literature`：检索、笔记、引用、BibTeX、去重
- `literature-summary-zh`：科学性综述（只述不展望）
- `sci-journal-literature`：SCI/顶会导向检索
- `systematic-review-lite`：轻量 PRISMA 流程

### 写作与结构

- `academic-writing`：润色、人味化、术语统一
- `thesis-abstract-zh`：摘要专项
- `thesis-conclusion-outlook-zh`：末章结论与展望
- `chapter-structure-refactor`：整章重构

### 评审与一致性

- `thesis-reviewer`：盲审向评审、摘要专项、AI 痕迹
- `intro-reviewer`：绪论专审与方法-文献支撑

### 格式、图表与演示

- `latex-compile`：XeLaTeX 编译 PDF
- `formula-normalizer`：公式符号一致性
- `svg-flowchart`：学术流程图
- `image-description`：图注与正文描述
- `academic-presentation`：答辩/汇报幻灯片
- `pdf`：技能内约定的 PDF 操作（非通用通读）
- `docx`：技能内约定的 Word 操作（非通用解析）

### 扩展

- `skill-creator`：新建技能模板
- `mcp-builder`：MCP 开发说明

---

## 设计边界与学术诚信

- 本仓库用于辅助写作流程，不替代原创研究与学术判断。
- 不建议把输出不经实质性修改直接提交。
- 不代劳：创新点决断、实验/调查方案设计、代写可提交全文。
- 不提供：以本仓库为入口的 doc/pdf/html 通用通读与批量解析管线。
- `pdf`/`docx` 目录仅覆盖各自 `SKILL.md` 标注场景。

---

## 运行环境（需自备）

- LaTeX：MiKTeX / TeX Live / MacTeX
- Word：Microsoft Word / WPS（依学校要求）
- 格式转换：[Pandoc](https://pandoc.org/)
- 脚本：Python 3 + 各技能 `requirements.txt`

本仓库不负责本机 TeX/Pandoc 环境排障。

---

## 仓库结构

```text
skills/
  <skill-name>/
    SKILL.md
    references/
    scripts/
agents.md
README.md
.cursor/   # 可选
.opencode/ # 可选
```

---

## English

**thesis skills** is a skill pack for thesis writing, literature workflows, and review-oriented drafting. Each workflow lives in `skills/<name>/SKILL.md`; agents should read it before acting.

- `skills/` gives generic capabilities.
- `agents.md` is project-specific control (paths, initialization, routing, long-term preferences).
- One task, one skill; iterate in short multi-turn loops.

---

更多细则与路由： [agents.md](agents.md)