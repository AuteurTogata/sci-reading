# 杨师兄 SCI 文献精读 Skill

版本：v1.0

## 这个 Skill 做什么

它把 Codex 从“论文摘要器”变成“文献精读助手”：围绕研究问题、Research Gap、方法设计、Claim–Evidence、图表、机制、局限和科研复用，完整拆解一篇 SCI，并输出一页结论卡、完整精读笔记和证据索引。

## 典型用法

把论文 PDF 放到 Codex 当前工作区，然后直接说：

- `用 yang-sci-deep-reader 完整精读这篇论文。`
- `用文献精读 Skill，先做 5 分钟快速精读。`
- `按照杨师兄 SCI 精读模板读这篇 PDF，并告诉我对我的 SOFC 课题有什么用。`

如果文件名明确，也可以说：

- `精读 ./papers/xxx.pdf，使用完整深度模式。`

## 输出

默认生成：

```text
sci-reading-output/<论文短标题>/
├── 01_一页结论卡.md
├── 02_SCI文献精读笔记.md
├── 03_证据索引.md
└── 04_待确认信息.md  # 仅信息不完整时
```

## 安装

OpenAI 的 Skills 使用 `SKILL.md` 作为工作流说明文件，支持附带模板、示例、脚本等资源。该文件夹可作为完整 Skill 目录上传/安装；在 Codex 中也可放入支持的 skills 目录后使用。

## 文件说明

- `SKILL.md`：主工作流和硬规则。
- `assets/`：三份正式输出模板 + 原始简单模板参考图。
- `references/evidence-rules.md`：证据、来源分层与反幻觉规范。
- `references/figure-reading-rules.md`：图表精读标准。
- `references/study-type-routes.md`：不同研究类型的自适应路线。
- `references/quality-gate.md`：交付前质量门禁。
- `scripts/validate_output.py`：输出结构与证据定位的轻量校验脚本。

## 设计原则

1. 不以“总结更多”为目标，而以“建立可核验的理解”为目标。
2. 不要求所有论文填满同样的字段，文章不适用的部分允许 N/A。
3. 重要主张必须有原文位置。
4. 原文事实、作者解释、Codex 推断和待验证假说必须分开。
5. 一页结论卡用于快速复习；完整笔记用于深入理解；证据索引用于追溯与后续写作。
