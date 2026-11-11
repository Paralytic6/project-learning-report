# Project Learning Report · 项目学习报告

给用 AI 辅助开发、同时想学会读代码和看实验结果的人。这个 Codex Skill 会在一次开发、排障或实验完成后，结合当前项目的源码、测试和运行结果，写一份能跟着学的报告。

报告会说明问题为什么值得解决、从哪个文件读起、结果是怎么得出的，并留一道可以自己做的小练习。小任务可以简写，完整阶段可以加上图表、失败案例和复现步骤。

[查看示例报告](.agents/skills/project-learning-report/references/example-report.md)

## 安装

在 Codex 中发送下面这条消息。安装器会从本仓库下载整个 Skill 目录，包含示例报告。

```text
$skill-installer 从 Paralytic6/project-learning-report 安装 .agents/skills/project-learning-report
```

也可以下载或克隆仓库，把 `.agents/skills/project-learning-report` 整个目录复制到个人技能目录（`~/.agents/skills/`），或者复制到目标项目的 `.agents/skills/`。复制后应能在 `project-learning-report` 目录下直接找到 `SKILL.md`。若技能列表里没有出现，重启 Codex 再检查。 [Codex Skill 安装和发现路径](https://learn.chatgpt.com/docs/build-skills)

## 使用

在你要学习的项目里开一个 Codex 对话。先试一次只读任务，看看报告能否帮你顺着代码找到证据。

```text
$project-learning-report 根据已有代码和测试结果，写一份这次改动的中文学习报告。
从一个具体例子讲起，给我一道能自己核对的小练习。只生成报告。
```

也可以把报告和开发任务一起交办。

```text
修复导入空文件时的报错并运行相关测试。做完后用 $project-learning-report
解释空输入怎么走到出错位置、修复后发生了什么，以及我怎么自己确认。
```

默认生成简体中文 Markdown。沿用项目的报告目录，没有约定时写到 `docs/<主题>学习报告_<日期>.md`。需要 PDF 或其他语言时，在提示词里注明。

## 设为项目默认

如果希望在这个项目的开发任务结束时自动写报告，在项目根目录的 `AGENTS.md` 加入下面这段，并确保 Codex 能发现已安装的 Skill。 [Codex 项目规则说明](https://learn.chatgpt.com/docs/agent-configuration/agents-md)

```markdown
完成本项目的开发、排障、实验或技术分析后，在最终答复前使用
project-learning-report Skill 写一份学习报告，并附上报告路径。
小任务简写。按用户当次指定的范围和格式交付。
```

## 怎么判断报告写得好

- 能在项目里找到报告提到的文件、函数和结果。
- 读得懂一个关键判断，知道输入、输出和单位。
- 能看出哪些结论有测试或实验支持，哪些还需要验证。
- 能按练习独立核对一次，知道怎样算通过。

欢迎通过 Issue 反馈容易漏写的任务或难懂的段落。可以附上去掉项目敏感信息的任务描述和预期报告内容。

## 许可证

[MIT](LICENSE)
