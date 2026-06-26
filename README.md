# Project Review Council

[![Author](https://img.shields.io/badge/Author-qomob.ai-blue)](https://qomob.ai)
[![Version](https://img.shields.io/badge/Version-v1.0.0-green.svg)](https://github.com/qomob/skillforge)
[![Language](https://img.shields.io/badge/Language-%E4%B8%AD%E6%96%87-red.svg)](https://github.com/qomob/skillforge)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Built with](https://img.shields.io/badge/Built_with-SkillForge-violet.svg)](https://github.com/qomob/skillforge)

世界级项目评审委员会 Skill。20 位独立角色对任意项目做对抗式多维度审计，输出基于证据的 Go/No-Go 决议。

## 快速使用

向 AI 说："用项目评审委员会审计这个项目：[项目描述/链接/仓库]"

## 架构

- `SKILL.md` — 路由器（< 300 行）
- `workflows/` — 10 阶段 Pipeline（理解 → 证据 → 角色审计 → 交叉 → 风险 → 隐藏 → 商业 → 执行 → 决议 → 红蓝）
- `roles/` — 20 个角色人格（参数化，可启停）
- `rubrics/` — 评分 / 风险等级 / 决策矩阵 / 评级
- `checklists/` — 产品 / 架构 / 商业 / 安全 / 代码 / 增长
- `templates/` — 输出契约（防格式漂移）
- `examples/` — Few-shot 标杆
- `config/` — 角色 / 权重 / 深度（YAML 化，不改主 Prompt）

## 核心机制

1. **Fan-out** — 20 角色并行独立审计
2. **Adversarial** — 交叉反驳 + 红蓝对抗
3. **Pipeline 门控** — 阶段不可跳，每阶段有 Exit Gate
4. **干验分离** — Independent Auditor 只验证不产出

## 扩展方式

| 需求 | 做法 |
|------|------|
| 加角色 | `roles/xxx.md` + 在 `config/roles.yaml` 注册 |
| 调评分权重 | `config/weights.yaml` |
| 改审计深度 | `config/settings.yaml` 的 `depth` |
| 加行业清单 | `checklists/industry-*.md` |

## 配置

```yaml
# config/settings.yaml
depth: standard   # quick(5 角色) / standard(12) / deep(20)
language: zh
evidence_level: strict
min_report_words: 3000
enable_phase_10: true
```

## 加入群聊

<div align="center">
  <img src="https://qomob.ai/xskill.jpg" width="600" alt="XSkill">
</div>
