# 贡献指南

本仓库只存放个人主页 README。流程刻意做轻：**main 受保护，改动走短分支 + PR**，
不引入 develop 长分支，因为这里不存在多版本并行集成的需求。

## 分支与命名

| 分支 | 用途 | 生命周期 |
|---|---|---|
| `main` | 唯一主干，内容直接展示在 GitHub 个人主页 | 永久 |
| `docs/<短名>` | 内容修订 | 数小时 |
| `fix/<短名>` | 链接失效、错别字等修正 | 数小时 |
| `chore/<短名>` | 配置调整 | 数小时 |

命名用小写加连字符，如 `docs/add-new-project`、`fix/broken-links`。

`main` 的保护规则：禁止直接推送、禁止 force push、合并需 1 次评审且 CI 通过。
管理员保留 bypass 权限（单人维护，否则会锁死自己）。

## 提交信息

统一 Conventional Commits：

```
docs: 新增 FlyTrap 项目介绍
fix: 修正项目链接拼写错误
chore(deps): 升级 actions/checkout 到 v4
```

`type` 取值：`feat` `fix` `docs` `style` `refactor` `perf` `test` `build` `ci` `chore` `revert`。
本仓库几乎只会用到 `docs`、`fix`、`chore`。

本地配置模板：

```bash
git config commit.template .gitmessage
```

因为使用 squash merge，PR 标题会成为最终提交信息，
所以 CI 用 `amannn/action-semantic-pull-request` 校验 **PR 标题**。

## 流程

```bash
git switch main && git pull
git switch -c docs/add-new-project
# 修改 README.md
git add -A && git commit
git push -u origin docs/add-new-project
gh pr create --fill
```

合并前 CI 会检查 README 里的外链是否失效——这是本仓库唯一真正有价值的自动化检查。

## 内容准则

1. 不写入任何密钥、令牌、真实证件号、家庭住址等敏感信息
2. 项目链接必须指向真实存在的仓库
3. 奖项与经历如实描述，不夸大
4. 修改联系方式（邮箱等）时确认该渠道仍在使用

## 发版

本仓库**不使用语义化版本**：内容型仓库没有「版本」概念，打 tag 只会制造噪音。
变更追踪依靠 [CHANGELOG.md](./CHANGELOG.md) 的日期条目与 Git 历史。
