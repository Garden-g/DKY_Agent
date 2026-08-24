# 项目上下文

本仓库用于发布“大客赢”品牌的 Accio Work 外贸业务智能体套装。当前主交付是 47 个智能体，安装入口从 `INSTALL_PROMPT.md` 进入，再读取 `install/dakying-47-agents.txt`，下载并校验 `release/dakying-47-accio-agents-v2.4.0.zip`，最后由压缩包内的系统启动脚本调用 `installer/install.mjs` 完成安装。

压缩包内的 `bundle-manifest.json` 定义套装版本、智能体数量、名称、Skill 绑定关系和 Logo 摘要；每个 `agents/*/profile.jsonc` 定义智能体可见名称、品牌、内嵌 Logo、工具白名单和运行时 Skill；`agent-core/AGENTS.md`、`IDENTITY.md`、`SOUL.md` 是固定身份文档。安装器会生成唯一的 `MID-*`，原子写入当前 Accio Work 账号目录，并同步当前主智能体的用户画像和记忆。

品牌或版本更新通常需要生成新的版本化 ZIP、对应的 SHA-256 文件和安装指令，不能直接覆盖旧发布文件。不要修改历史 ZIP，也不要删除或覆盖用户现有的无关智能体。验证时至少检查 ZIP 完整性、清单声明的 47 个智能体、全部名称前缀、品牌字段、Logo 摘要、每个智能体声明的一个或多个私有 Skill，以及安装器预检、隔离安装和重复安装结果。
