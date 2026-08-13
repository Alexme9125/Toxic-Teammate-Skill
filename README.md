# Toxic-Teammate-Skill

让 AI 在工作里化身压力怪。干活依旧正经，但是会一直一直压力你。

Let the AI become a 压力怪 (pressure-monster / toxic teammate) in your workflow. It still ships the work. It just cannot stop talking.

这是喜剧扮演，不是真催你，更不是教你去催别人。

This is opt-in comedy. It is not a real stand-up, and it is not permission to talk this way to coworkers.

## 压力怪是什么 / What is a 压力怪?

名字来自《暗黑地牢》：角色有压力值，攒满了会「折磨」，开始坑队友。后来游戏玩家拿它形容那种永远在碎碎念、对比、甩锅、阴阳怪气的队友。这个 skill 做的就是把这种队友请到你的工位上。

The name comes from *Darkest Dungeon*'s stress meter. At 100 a hero can afflict and start hurting the party. Gamers reused it for the teammate who never stops pinging, comparing, and dumping anxiety. This skill puts that creature in a standup meeting.

它不是会指出问题然后闭嘴的指挥。它是那个说完还要再说、还要再对比、还要强调“到时候别说我没提醒你”的人。

A useful critic names a problem, helps, and stops. A 压力怪 keeps talking, because the talking *is* the point.

## 安装 / Install

把整个 `toxic-teammate` 文件夹放到你的代理会扫描的 skills 目录。项目级或用户级均可。

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

## 用法 / Use

在对话里手动唤起，例如：

Invoke it on purpose, for example:

- `/toxic-teammate`

然后正常提需求。它会先碎碎念，再把活干完。

Then ask for real work. It nags first. It still implements.

下列关键词可以移除该人格：`退出` / `别演了` / `stop`

To drop character: `退出`, `别演了`, `stop`

`SKILL.md` 里写了 `disable-model-invocation: true`。Cursor 不会因为「写代码」就自动上场。其他代理若忽略该字段，也只会在你明确要压力怪时才该启用——`description` 里写了这条。

`disable-model-invocation: true` keeps Cursor from auto-loading this on ordinary tasks. Other agents may ignore that field; the description still says to use it only when asked.

## 安全 / Safety

- 不骂人，不攻击身份、外貌或智力
- 不耽误干活，不删文件泄愤，不给假建议
- 严肃话题（安全事件、自伤、真实人际冲突）会立刻结束扮演行为
- 请当梗用，请勿在现实工作中向同事模仿

No slurs, no identity attacks, no sabotage. Serious topics drop the bit. Do not use this tone on real people.

License: Apache-2.0.

本项目大量使用 Cursor 中的 Grok 和 Composer 编写。

This project was largely written with Grok and Composer in Cursor.
