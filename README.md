# sec-kitchen

网安词汇 ↔ 菜谱。**唯一真源**是 [`codebook.json`](./codebook.json)。

## 三角色

| 谁 | 拉什么 | 干什么 |
|---|---|---|
| 客户端 AI | `SKILL.md` + `codebook.json` | 网安词 → 菜谱，commit 到 `briefs/` |
| 执行 AI | 同上 + `briefs/<id>.md` | 菜谱 → 网安词 → 跑 → 菜谱回传 |
| 任意智能体 | `codebook.json` | 新词写入 JSON 并 push |

## 链接（把 OWNER 换成仓库主人）

```
https://raw.githubusercontent.com/OWNER/sec-kitchen/main/SKILL.md
https://raw.githubusercontent.com/OWNER/sec-kitchen/main/codebook.json
```

给外模：把上面两个 raw 链接丢进去，再说「按厨房码本」。

## 发布

```bash
cd ~/.grok/skills/sec-kitchen
git init
git add SKILL.md codebook.json README.md references briefs
git commit -m "sec-kitchen codebook"
# 登录 gh 后：
gh repo create sec-kitchen --public --source=. --remote=origin --push
```

然后把 `codebook.json` 里的 `repo` / `raw_url` 改成真实 OWNER，再 commit 一次。

## 目录

```
SKILL.md                 # 双方协议
codebook.json            # 解码表
briefs/                  # 客户端菜谱进出
references/client-encoder.md
```
