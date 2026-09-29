# 学习系统套件

> WorkBuddy Skill · 屋里涛说

一套面向学生的完整学习系统。五个技能通过「学习 DNA」档案串联成闭环——错题 → 复习 → 复盘 → 规划。

## 技能清单

| 技能 | 说明 |
|---|---|
| **learning-dna** · 学习画像（入口） | 建立学生档案：年级、学科、学习风格、优势与薄弱点、学习目标、可用时间。**其他四个技能都依赖这份档案提供个性化上下文**。 |
| **smart-error-book** · 智能错题本 | 分析错因、引导思考、安排复习。**核心原则：绝不在第一步就给出答案**，用苏格拉底式提问引导学生自己找到解法。 |
| **feynman-learning** · 费曼学习法 | 通过「教别人」检验是否真正理解：选定概念 → 用自己的话讲 → 发现漏洞 → 简化类比。 |
| **study-reminder** · 学习提醒 | 错题复习、作业截止、单词背诵、考试倒计时的定时提醒。底层用 WorkBuddy automation 调度。 |
| **weekly-review** · 每周复盘 | 串联错题、笔记、学习计划与兴趣，做结构化周总结与下周规划。含月复盘模板。 |

## 工作流

```
        learning-dna  ← 学习画像（所有技能的个性化上下文来源）
             │
   ┌─────────┼─────────┬────────────┐
   ▼         ▼         ▼            ▼
 错题本    费曼学习   学习提醒     每周复盘
   └─────────┴─────────┴────────────┘
          错题 → 复习 → 复盘 → 规划
```


## 安装

把 `skills/` 下的技能目录拷贝到 WorkBuddy 的技能目录：

```bash
cp -r skills/* ~/.workbuddy/skills/
```

Windows PowerShell：

```powershell
Copy-Item .\skills\* "$env:USERPROFILE\.workbuddy\skills\" -Recurse -Force
```

重启 WorkBuddy 后，技能列表即可看到。

## 使用要点

- 首次使用先进 `learning-dna` 建档案，其余技能才有上下文。
- 日常循环：做错题 → 错题本分析；搞不懂 → 费曼讲一遍；设提醒 → 定时复习；周日 → 复盘 + 规划下周。

## 环境依赖

- WorkBuddy automation（提醒调度）

## 目录规范

```
learning-system-suite/
└── skills/
    ├── learning-dna/
    ├── smart-error-book/
    ├── feynman-learning/
    ├── study-reminder/
    ├── weekly-review/
```

每个技能遵循统一结构：`SKILL.md`（必需，含 name/description frontmatter）+ `scripts/`（可选）+ `references/`（可选）。

---

## License

MIT — 随意取用、修改、二次分发。
