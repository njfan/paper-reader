# paper-reader

一个用于阅读计算机领域论文的 Codex skill。它从论文链接或 PDF 生成九节中文速读笔记，整理 baseline、问题、贡献、实验、消融、局限和相关工作。

Notion 为可选功能。配置后，skill 会在阅读前查重，并将笔记保存到个人论文数据库；未配置时仍会正常输出笔记，并询问是否创建数据库模板。

## 安装

在 Codex 中调用 `$skill-installer`，并把本仓库的 GitHub 链接发给 agent：

```text
$skill-installer 请安装这个 GitHub skill：https://github.com/njfan/paper-reader。SKILL.md 位于仓库根目录，安装名使用 paper-reader。
```

agent 会从 GitHub 下载并安装到 Codex skills 目录。安装完成后，从下一轮对话开始使用：

```text
$paper-reader https://arxiv.org/pdf/xxxx.xxxxx
```

如果本地已经存在同名的 `paper-reader`，安装器会停止而不会覆盖；请先备份或移走旧版本，再重新安装。

## 输出结构

1. 基本信息
2. 一句话概括
3. Baseline
4. 要解决的问题
5. 解决方案 / 创新点
6. 实验结果
7. 消融实验
8. 局限性
9. 相关论文

## Notion 配置

首次使用时可以让 skill 在已连接的个人 Notion 中创建 `paper-reader` 数据库。skill 会按照内置模板创建字段，并把连接信息保存到本地 `references/notion-config.md`。

也可以复制 `references/notion-config.example.md` 为 `references/notion-config.md`，再填写自己的数据库 URL、数据源 ID 和可选视图 ID。该文件已被 Git 忽略，不会提交到公开仓库。

Notion 未连接或没有配置时，论文阅读与聊天输出仍然可用。

## 隐私

不要提交 `references/notion-config.md`、访问令牌、私人论文笔记或其他账号信息。发布前检查待提交文件中是否包含个人路径、工作区 URL 或数据库 ID。
