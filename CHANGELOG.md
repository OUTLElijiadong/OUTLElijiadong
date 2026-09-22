# Changelog

格式参考 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)。

本仓库**不使用语义化版本与自动发版**：README 是内容型文件，没有「可发布的版本产物」，
打 tag 只会制造噪音。变更按日期倒序手工记录即可。

## [未发布]

## 2026-09-22

### 修复

- 修正项目链接中的用户名拼写错误：原先指向 `OUTLEliadiadong/*`，实际应为
  `OUTLElijiadong/*`，两个项目链接此前均为死链

### 新增

- MIT LICENSE（仓库此前无任何许可证，他人无明示使用权限）
- `.gitignore`（重点排除凭据与私钥类文件）
- `CONTRIBUTING.md` / `SECURITY.md` / `CHANGELOG.md` / `.gitmessage`
- CODEOWNERS、issue 与 PR 模板
- CI：README 外链失效检查、Conventional Commits 标题校验
- Dependabot：每周更新 workflow 引用的 action 版本

## 2026-09-13

### 新增

- 初始个人主页 README：个人简介、代表项目、奖项、技术方向
