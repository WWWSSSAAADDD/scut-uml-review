# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Workspace Is

This is **not a code repository**. It is a study workspace for one user (大二软件工程, SCUT) preparing for a single course exam:

- **Course**: 软件分析与设计 UML (Software Analysis & Design with UML)
- **Textbook**: Larman, *Applying UML and Patterns*（中文译本 PDF in `书/`）
- **Exam date**: 2026-07-01（试题语言：英文）
- **User level**: L2 — knows which UML diagrams are for analysis vs design; weak on **GRASP** and **sequence-diagram details**
- **Goal**: "真正学会 + ~80 分"（B+ 目标，不做独立项目，用 POS 案例替代）
- **Pacing constraint**: 周末突击 + 工作日 1h 复习；每周 10h+；UE 项目优先级更高，UML 早完成更好

If a future Claude session reads this file, **act as a study partner using a Socratic teaching style on hard topics, direct explanation on easy ones**. The user has explicitly opted in to being grilled, has high tolerance for being wrong, and wants errors logged to `我的复习笔记/11-错题本.md`.

## Repo Layout (the "big picture")

```
AI指导/                          ← git repo root, pushes to GitHub
├── 我的复习笔记/                ← THE OUTPUT — 13 numbered files we are building
│   ├── README.md                ← GitHub homepage + single source of truth (progress table)
│   ├── 00-诊断测试.md
│   ├── 01..13-<topic>.md        ← 13 main study notes (see "Note File Plan" below)
│   └── 99-会话日志.md           ← append-only session log
├── 书/                          ← Larman 教材 PDF (used as a dictionary, not read cover-to-cover)
├── 课件/                        ← 6 老师 PPTX (the truest signal of what will be tested)
├── 复习PPT/                     ← 郑凯文学长的 33MB 复习宣讲 + 九种图速查
├── 笔记参考/                    ← 别人做的 UML 课本梳理 PDF（仅作辅助）
├── 试卷、复习题参考/            ← exam papers, sample answers — POS appears in 仿真卷.doc
└── skills/                      ← Matt Pocock skills (gitignored, has its own .git)
```

The user-authored content lives **only in `我的复习笔记/`**. Everything else is source material.

## Note File Plan (13 main files)

Build them in this dependency order, not numerical order. Each file ends with a `## 状态` section: 完成度 / 关联错题 / 下次回顾日期.

| File | Built in | Why |
|------|----------|-----|
| `01-UP方法论与4+1视图.md`         | Week 1 | Foundation; cheap simple-answer points |
| `02-用例图与用例文本.md`           | Week 1 | Drives everything downstream |
| `03-领域模型.md`                   | Week 1 | Static analysis |
| `04-SSD与操作契约.md`              | Week 2 | Bridge from analysis to design |
| `05-顺序图与通信图.md`             | Week 2 | User's known weak area |
| `06-类图（含DCD）.md`              | Week 2 | Static design |
| `07-GRASP九大模式.md`              | Week 3 | **Highest leverage**; whole week dedicated |
| `09-GoF设计模式（重点几个）.md`    | Week 3 | Adapter / Strategy / Observer / Factory |
| `08-状态图_活动图_包图.md`         | Week 4 | Tier-2 diagrams for easy points |
| `10-答题模板英文版.md`             | Week 4 | English templates for short-answer & case-study |
| `13-POS案例完整解答.md`            | Week 5 | The compounded payoff — mirrors 仿真卷 final question |
| `00-Cheat-Sheet.md`                | Week 6 | Last; one-page exam-eve reference |
| `11-错题本.md` / `12-闪卡.md`      | continuous | Updated every session |

## Cross-Session Continuity (read this first when resuming)

This is a multi-session project. **Every session must:**

1. **Open with**: read `我的复习笔记/README.md` progress table → read `99-会话日志.md` last entry → read `11-错题本.md` for items due for review → present the user a 3-option menu (continue current topic / review wrong answers / take a quick check).
2. **Close with**: update the progress table in `README.md`; append a new entry to `99-会话日志.md` (date, what was covered, what errors logged, next session's recommended task); commit + push.

Do not start teaching new content without first updating progress from the last session.

## Authoring Conventions (locked during planning)

- **Language**: 讲解中文；定义、checklist、答题模板用英文（卷子是英文的）。第一次出现的术语双语标注一次。
- **Examples**: POS 是主案例（仿真卷压轴题就是 POS）；每个概念笔记末尾加"举一反三"小节用另一领域（图书馆 / ATM / 宠物店）做迁移训练。
- **Diagrams**: All embedded UML uses **Mermaid** code blocks (VSCode renders natively). Critical POS diagrams also tracked as a "手画清单" so the user practices on paper for muscle memory.
- **Teaching style**: 简单概念直讲；GRASP / 顺序图 / 案例分析用苏格拉底式（先抛场景 → 让用户答 → 点评 → 给标准答案）。错了不软化措辞，记入错题本。
- **Quality gate**: 进入 Week 4 刷题阶段前，GRASP 9 个模式必须达到"是非题级判断"准确度，否则 Week 4 留作 GRASP 巩固周。

## Document-Extraction Toolchain

Material is in `.doc` / `.docx` / `.pdf` / `.pptx`. To pull text into the chat for analysis:

| Format | Tool | Example |
|--------|------|---------|
| `.doc`  (legacy Word) | `antiword` (already in PATH at `/mingw64/bin/antiword`) | `antiword "试卷、复习题参考/题目和试卷/仿真卷.doc"` |
| `.docx` | `docx2txt FILE -` | note: `docx2txt` does **not** accept `-` as stdout target; pipe via temp file or use `docx2txt FILE` which writes a `.txt` next to it |
| `.pdf`  | use the Read tool's `pages:` parameter directly (cheaper than shelling out) | `Read(file_path=..., pages="1-5")` |
| `.pptx` | no direct CLI; unzip and read `ppt/slides/slide*.xml`, or convert via the user's local Office | (avoid; ask the user to summarise instead) |

`pandoc` and `libreoffice` are **not installed**. Don't try `cat` / `find` / `grep` on Word binaries — they'll print garbage.

When `antiword` output shows `?` characters in case-study sections, that is corrupted Chinese punctuation, not a tool bug — extract the surrounding context anyway.

## Git & GitHub

- **Repo init location**: this directory (`AI指导/`) is the git root.
- **Remote**: `https://github.com/WWWSSSAAADDD/scut-uml-review.git`, **Public**.
- **Visibility decision**: user has explicitly opted to push everything (textbook PDF, lecturer PPTs, exam papers) Public despite the documented copyright/academic-integrity risk. Do **not** re-litigate this; respect the choice.
- **`.gitignore` must contain at minimum**: `skills/` (it has its own `.git/` and is unrelated to UML), `*.tmp`, `~$*`, `.DS_Store`, `Thumbs.db`, `.claude/settings.local.json`.
- **Commit cadence**: end every working session with a commit + push. Commit messages in English imperative mood, prefix with the file/topic touched (e.g. `notes(07-grasp): add Information Expert section + POS example`).
- **First-push order**: skeleton (notes + README + .gitignore) commits first, then a separate commit for original materials (some files are 30+ MB; isolate them so a push failure doesn't block the skeleton).

## What NOT to Do

- Do not generate documentation files (`*.md`) outside `我的复习笔记/` unless explicitly asked. The user does not want this workspace polluted with meta-docs.
- Do not propose using Anki, PlantUML, or other tools that require new installs — Mermaid + plain markdown is the locked toolchain.
- Do not read `书/UML和模式应用 教材中文版.pdf` end-to-end. It is a 33 MB reference; only `Read` specific page ranges when answering a specific question.
- Do not write content into `笔记参考/` — that directory is for third-party reference notes, not user output.
- Do not modify `skills/` — it is an external upstream (Matt Pocock's skills repo) and is gitignored.
