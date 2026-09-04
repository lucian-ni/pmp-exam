# 出题测试提示词

> 用法：对 Claude 说「出 Study Hall」或「出 10 道」。冲刺阶段默认只刷 Study Hall。

## 提示词

请从 **Study Hall 英文版**出 **{{题数，默认 10}}** 道题考我。

要求：
- 题源：`04-practice/studyhall/studyhall英文版Q.md`（对答案用 `studyhall英文版Q&A.md`）。不要用中文版 md、不要用 Q&A&D。
- 以英文原题为底，**现场译成中文** + 附英文原文。每题标题用 **`### Study Hall #N`**（N 即 `## 第N题`，与 PDF Question #N 相同）。格式见 `CLAUDE.md`。
- 先不给答案。查已刷题号与待重做。待重做超过 10 道则本批先清错题。
- 记录对错，结束后汇总。先对错总表，再只讲错题（中英全文 + 逐选项）。
- **家**：错题当场写入 `05-mistakes/studyhall.md` + 领域文件，题号写入刷题进度。
- **公司**：只写 inbox——`LOG` 记范围（如 SH#1–#10），`MISTAKE` 记错题 SH# + 对错字母；不写题干。
