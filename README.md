# PMP 备考资料库

整理日期：2026-07-23 ｜ 已去重 + 压缩瘦身 + 题目转 md（可搜索）

## 目录结构

围绕 **「状态 → 资料 → 学习 → 知识 → 练习 → 错题」** 组织，备考时顺着取用。

```
CLAUDE.md              Claude 的长期行为规范（讲解/出题/复盘/维护进度的工作流）
转换记录.md             习题库 PDF→md 转换日志（历史溯源）

00-dashboard/          学习状态（Claude 自动维护）
  ├ study_plan.md        学习计划
  ├ progress.md          学习进度
  ├ weak_points.md       薄弱知识点
  ├ learning_log.md      每日学习日志
  └ exam_readiness.md    模考趋势

01-material/           教材课件原典（基本只读）
  ├ official/            PMBOK 第七/六版、过程组实践指南（中英文）
  ├ agile/              敏捷实践指南（中英文 + 补充）
  └ slides/             讲义：凌峰班 1-14 章 / 串讲与点睛 / 骐迹

02-learning/           每天真正工作的地方（你自己的笔记）
  ├ 01-foundation        基础：原则、运行环境、项目经理角色
  ├ 02-people           人员：团队、领导力、干系人、沟通
  ├ 03-process          过程：范围/进度/成本/质量/风险/采购/变更
  ├ 04-business         业务环境：合规、价值交付
  ├ 05-agile           敏捷：宣言、三角色、工件与会议
  └ 06-mock-review      模考复盘记录

03-knowledge-base/     长期资产
  ├ concepts/           知识点汇总/提炼/整理（8 份）
  ├ cheat_sheet/        考前速记：N 页纸、九阴真经、蒙题大法、做题 36 计（10 份）
  ├ compare/            概念辨析、难点汇总、疑难答疑（4 份）
  ├ formulas/           口诀、公式、ITTO 助记、132 个工具与技术（4 份）
  ├ mindmaps/           思维导图（14 份）
  ├ glossary/            术语表（待补）
  └ project_mapping/    v6 知识领域 ↔ v7 绩效域 映射（待补）

04-practice/           题库（已转 md，可 grep）
  ├ chapter/           分章：第 1-13 章 + 0-8 绩效域 + 人员/过程/业务环境（27 份）
  ├ studyhall/         PMI 官方题（中英文）
  ├ mock/              模拟与真题 + 冲刺讲义与刷题
  ├ agile/             敏捷专项（测试、专题、密训押题卷）
  └ daily/             每日刷题：乐凯每日一练与周练习 + 考前 10 天每日冲刺

05-mistakes/           错题中心（Claude 维护）
  ├ people / process / business / agile.md
  └ recurring_patterns.md  反复出错模式

exam-info/             报考与考场操作信息（注册流程、答题卡）

prompts/               复用提示词：explain / quiz / review / simulate
```

## 一个月备考路径

1. **打基础（前 2 周）**：`01-material/slides` 课件 + `01-material/official` 教材过一遍，同步看 `03-knowledge-base/concepts` 和 `mindmaps` 建框架，笔记进 `02-learning/01-foundation`。
2. **分章刷题（第 3 周）**：`04-practice/chapter` 按章刷，错题回 `03-knowledge-base` 查漏；敏捷弱的加刷 `04-practice/agile`。错题记入 `05-mistakes/`。
3. **模考冲刺（最后 1 周）**：`04-practice/mock` 计时模考，吃透解析；`04-practice/daily` 每天一套；考前看 `03-knowledge-base/cheat_sheet` 的蒙题大法。
4. **官方题必刷**：`04-practice/studyhall` 是 PMI 官方题，风格最接近真实考试，优先做。

## 怎么用 Claude 陪练

- `/explain <知识点>` 讲解 + 出题考你 + 自动记笔记
- `/quiz <领域> <题数>` 抽题测试，错题自动入库
- `/review <领域>` 复盘错题，找反复模式
- `/simulate <套题>` 计时模考，算分记趋势

（提示词模板在 `prompts/`，行为规范见 `CLAUDE.md`。）

## 双环境：家 / 公司

公司只能 `git pull` 不能 `push`，所以公司里的产出走中转：

1. **公司**：Claude 把笔记/错题/日志写进 `inbox/office-YYYY-MM-DD.md`（已被 gitignore，不进 git）。
2. 拷贝该文件全文带回家。
3. **家**：把文本贴给 Claude，它录入到 `02-learning` / `05-mistakes` / `00-dashboard` 等正式文件，归档 inbox，然后 commit + push。

每次新会话 Claude 会先问你在哪，再按位置决定写入策略。详见 `CLAUDE.md`。

## 整理说明（溯源）

原资料按「机构来源」散落多处，已按内容类型重组，并分轮去重 / 压缩 / 转 md：

- **去重**：md5 严格比对删 35 份字节一致副本；同书多扫描版核实页数后各留 1 份干净版。
- **题目转 md**：`04-practice` 题目转成「题干 + 选项 + 答案 + 解析」结构，可 grep、可标错题；pdftotext 提取（修复 studyhall 乱码与乐凯乱序），质量好的删原件只留 md。详见 `转换记录.md`。
- **压缩**：扫描图型 PDF 降到 100 DPI，759M → 471M。

> 本次（2026-07-23）按「学习工作流」重组为 `00-dashboard` ~ `prompts` 的新结构；旧文件一律用 `git mv` 搬迁保留历史，未删任何内容文件。
