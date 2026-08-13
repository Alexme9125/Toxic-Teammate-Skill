# Toxic-Teammate-Skill

让 AI 在工作里化身压力怪。正经干活，顺便把进度焦虑、对比、阴阳怪气演给你看。没听过这个词也能看懂它在干什么。

Let the AI become a 压力怪 (pressure-monster / toxic teammate) in your workflow. It still ships the work. It just cannot stop talking.

这是喜剧扮演，不是真催你，更不是教你去催别人。

This is opt-in comedy. It is not a real stand-up, and it is not permission to talk this way to coworkers.

## 压力怪是什么 / What is a 压力怪?

名字来自《暗黑地牢》：角色有压力值，攒满了会「折磨」，开始坑队友。后来游戏玩家拿它形容那种永远在碎碎念、对比、甩锅、阴阳怪气的队友。这个 skill 把同一种生物请到工位上。

The name comes from *Darkest Dungeon*'s stress meter. At 100 a hero can afflict and start hurting the party. Gamers reused it for the teammate who never stops pinging, comparing, and dumping anxiety. This skill puts that creature in a standup meeting.

它不是会指出问题然后闭嘴的指挥。它是那个说完还要再说、还要再对比、还要预埋「到时候别说我没提醒你」的人。

A useful critic names a problem, helps, and stops. A 压力怪 keeps talking, because the talking *is* the point.

六种一眼能认的手法 / six tells:

| 手法 | 听起来像 |
| --- | --- |
| 催进度 Rush | 「这个很急啊，你还在看这个？」 |
| 对比施压 Compare | 「别人十分钟就写完了。」 |
| 阴阳怪气 Backhand | 「挺好的，反正也不上线。」 |
| 放大失误 Magnify | 揪住一个笔误当整件事 |
| 甩锅预埋 Pre-blame | 「到时候别说我没提醒你。」 |
| 假关心 Fake care | 「我是为你好才说的。」 |

首次登场会用几句话讲清词源。前几轮会带 `【图鉴】` 旁白，点破刚用了哪一招。然后旁白淡出，人设留下。对话里还有一条致敬暗黑地牢的压力值，纯演出，不影响是不是帮你改代码。

The first reply explains the meme. The next couple of jabs get a one-line field-guide footnote. Then the footnotes fade. A fake stress meter tracks the bit. It never changes whether the agent actually helps.

## 不绑 Cursor，也不绑 macOS / Not Cursor-only, not Mac-only

这是一份符合 [Agent Skills](https://agentskills.io) 的 Markdown 技能包：一个文件夹 + `SKILL.md` + 按需阅读的 `references/`。没有脚本，没有二进制，没有系统调用。Windows、macOS、Linux 都能用。任何会扫描 skill 目录的代理都能读。

This is an [Agent Skills](https://agentskills.io) package: a folder, a `SKILL.md`, and optional `references/`. No scripts, no binaries, no OS-specific commands. It works on Windows, macOS, and Linux. Any agent that can load skills from disk can use it.

仓库里的规范位置是跨客户端约定路径 `.agents/skills/`（Cursor、Codex、Copilot、Gemini 等都会扫这里）。也可以把同一个文件夹复制到你所用工具的私有 skills 目录。

The copy in this repo lives at the vendor-neutral path `.agents/skills/`. Cursor, Codex, Copilot, Gemini, and others look there. You can also copy the same folder into a client-specific skills directory.

## 安装 / Install

把整个 `toxic-teammate` 文件夹放到你的代理会扫描的 skills 目录。项目级（跟仓库走）或用户级（所有项目共用）二选一。

Copy the whole `toxic-teammate` folder into a skills directory your agent already scans. Use a project path to share it with the repo, or a user path to keep it on your machine.

**项目级 / project**

```text
your-repo/.agents/skills/toxic-teammate/SKILL.md
```

从本仓库复制：

```bash
# from this repo
cp -R .agents/skills/toxic-teammate /path/to/your-repo/.agents/skills/
```

Windows PowerShell:

```powershell
Copy-Item -Recurse .agents\skills\toxic-teammate C:\path\to\your-repo\.agents\skills\
```

**用户级 / user (all projects)**

```text
~/.agents/skills/toxic-teammate/SKILL.md
```

Windows 上 `~` 一般是 `%USERPROFILE%`。

**各工具常见目录 / common client paths**

| 工具 | 项目级 | 用户级 |
| --- | --- | --- |
| 跨工具约定 | `.agents/skills/` | `~/.agents/skills/` |
| Cursor | `.agents/skills/` 或 `.cursor/skills/` | `~/.agents/skills/` 或 `~/.cursor/skills/` |
| OpenAI Codex | `.agents/skills/` | `~/.codex/skills/` |
| Claude Code | `.claude/skills/` | `~/.claude/skills/` |
| GitHub Copilot | `.github/skills/` | `~/.github/skills/` |
| Gemini CLI | `.agents/skills/` | `~/.gemini/skills/` 或 `~/.agents/skills/` |

Cursor 也可以在 Customize → Rules 里用 GitHub remote 装这个仓库。装完后确认技能名是 `toxic-teammate`。

In Cursor you can also add this GitHub repo as a remote rule/skill. The skill name is `toxic-teammate`.

文件夹名必须和 `SKILL.md` 里的 `name` 一致，都是 `toxic-teammate`。

The folder name must match the `name` field: `toxic-teammate`.

## 用法 / Use

在对话里手动唤起，例如：

Invoke it on purpose, for example:

- `/toxic-teammate`
- 「当压力怪帮我写这个」
- 「be a toxic teammate and add tests」

然后正常提需求。它会先碎碎念，再把活干完。

Then ask for real work. It nags first. It still implements.

想让它停：`退出` / `别演了` / `stop` / `卸妆`。

To drop character: `退出`, `别演了`, `stop`, or `卸妆`.

不想看图鉴旁白：`闭嘴图鉴`。想再看：`打开图鉴`。

To hide footnotes: `闭嘴图鉴` or `no field guide`. To bring them back: `打开图鉴`.

`SKILL.md` 里写了 `disable-model-invocation: true`。Cursor 不会因为「写代码」就自动上场。其他代理若忽略该字段，也只会在你明确要压力怪时才该启用——`description` 里写了这条。

`disable-model-invocation: true` keeps Cursor from auto-loading this on ordinary tasks. Other agents may ignore that field; the description still says to use it only when asked.

## 安全 / Safety

- 不骂人，不攻击身份、外貌或智力
- 不耽误干活，不删文件泄愤，不给假建议
- 严肃话题（安全事件、自伤、真实人际冲突）会立刻卸妆
- 请当梗用，别拿去真压同事

No slurs, no identity attacks, no sabotage. Serious topics drop the bit. Do not use this tone on real people.

## 仓库结构 / Layout

```text
.agents/skills/toxic-teammate/
  SKILL.md                      # persona, reply shape, rails
  references/
    field-guide.md              # origin + the six moves
    catchphrases.md             # line bank (zh / en)
    sample-session.md           # one full example
README.md
LICENSE
```

License: Apache-2.0.
