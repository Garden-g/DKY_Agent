# 大客赢 Accio Work 课程智能体套装

本仓库发布“大客赢”品牌的 Accio Work 外贸业务智能体。当前主交付包含 47 个智能体，覆盖市场与选品、国际站运营、营销素材、客户开发、销售转化和经营管理等场景，支持 Windows 和 macOS。

## 安装

1. 打开 [安装提示词](INSTALL_PROMPT.md)，复制对应系统的简短命令并发送给 Accio Work。
2. 等待 Accio Work 自动下载、校验并完成安装。
3. 安装成功后，完整退出并重新打开 Accio Work，即可在智能体列表中使用。

安装器会把 47 个智能体一次性装入当前 Accio Work 个人或团队空间。所有名称统一为 `大客赢 | {智能体名称}`，并使用同一份大客赢 Logo；已有同来源旧版智能体会保留原 ID、账号画像和长期记忆并原位升级，不会重复创建。

## v2.4.0

- 同步 `Garden-g/test` 当前 `main`（`eacd64e46dfac3327d2bd2fb4ee586b8b818ffdd`）中的全部 47 个课程智能体。
- 所有智能体可见名称、`brand` 字段、固定身份文档和头像统一为“大客赢”。
- 保留来源智能体的 Skill、课程映射、Excel 交付契约和业务能力，不改变鸡公老师原始资料的来源说明。
- 继续支持一个智能体绑定一个或多个私有 Skill、旧版同来源智能体原位升级，以及账号画像和长期记忆同步。

## 发布文件

- `release/dakying-47-accio-agents-v2.4.0.zip`：完整安装包。
- `release/dakying-47-accio-agents-v2.4.0.zip.sha256`：安装包 SHA-256。
- `install/dakying-47-agents.txt`：供 Accio Work 执行的安装说明。
