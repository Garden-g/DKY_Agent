# 项目上下文

本仓库用于发布“大客赢”品牌的 Accio Work 外贸业务智能体套装。当前主交付是 49 个智能体，业务模板同步自 `Garden-g/test` 的 `v2.7.3`，但名称、品牌字段和头像保持“大客赢”独立品牌。

主安装入口从 `INSTALL_PROMPT.md` 进入，再读取 `install/dakying-49-agents.txt`，下载并校验 `release/dakying-49-accio-agents-v2.7.3.zip`，最后由压缩包内的系统启动脚本调用 `installer/install.mjs` 完成安装。企业 AI 底座搭建和企业知识库问答也各自提供独立 ZIP 与安装说明。

压缩包内的 `bundle-manifest.json` 定义套装版本、智能体数量、名称、Skill 绑定关系和 Logo 摘要；每个 `agents/*/profile.jsonc` 定义智能体可见名称、品牌、内嵌 Logo、工具白名单和运行时 Skill；`agent-core/AGENTS.md`、`IDENTITY.md`、`SOUL.md` 是固定身份文档。安装器会生成唯一的 `MID-*`，原子写入当前 Accio Work 账号目录，并同步当前主智能体的用户画像和记忆。

同步新版本时，以 `Garden-g/test` 当前发布包为业务内容基线，只修改品牌身份层：`bundle-manifest.json`、课程映射、所有 `profile.jsonc` 的名称/品牌/头像字段、固定身份文档、安装器品牌提示和安装说明。不得用“来搜”Logo 覆盖大客赢 Logo，也不得改变鸡公老师资料的来源说明和业务 Skill 的判断逻辑。

品牌或版本更新需要生成新的版本化 ZIP、对应的 SHA-256 文件和安装指令，不能覆盖历史 ZIP。发布链接必须固定到不可变提交，不使用会漂移的 `main` URL。不要修改无关历史发布文件，也不要删除或覆盖用户现有的无关智能体。

验证时至少检查：ZIP 完整性和无 `__MACOSX`/`._*` 条目；清单声明的 49 个智能体与目录一一对应；全部名称前缀、品牌字段和 Logo 摘要一致；每个智能体声明的一个或多个私有 Skill 完整；业务文件除已批准品牌层外与源包一致；安装器预检、隔离首次安装、重复安装和旧 47-Agent 升级均通过，且没有 `.installing-*` 残留。
