# 大客赢 Accio Work 课程智能体（共 49 个）

仓库目前共发布 49 个“大客赢”课程智能体，并已合并为一个可一次安装的完整套装。其中包括原有 47 个外贸业务智能体、“企业 AI 底座搭建智能体”和“企业知识库问答智能体”，覆盖企业 AI 底座、知识库问答、市场与选品、国际站运营、营销素材、客户开发、销售转化和经营管理等场景，支持 Windows 和 macOS。

业务内容已同步 `Garden-g/test` 的 `v2.7.3`；所有可见名称、品牌字段和头像继续使用“大客赢”品牌与大客赢 Logo。

## 安装

1. 打开 [安装提示词](INSTALL_PROMPT.md)，复制对应系统的简短命令并发送给 Accio Work。
2. 等待 Accio Work 自动下载、校验并完成安装。
3. 安装成功后，完整退出并重新打开 Accio Work，即可在智能体列表中使用。

安装器会把 49 个智能体一次性装入当前 Accio Work 个人或团队空间。所有名称统一为 `大客赢 | {智能体名称}`，并使用同一份大客赢 Logo；已经安装旧 47-Agent 套装的用户再次运行时，会补充第 48、49 个智能体；已经安装“大客赢”旧版的用户再次运行时，只原位升级发生变化的模板。升级会保留原 Agent ID、账号画像和长期记忆，不会重复创建。

## 企业 AI 底座搭建智能体

完整套装中的第 48 个是 `大客赢 | 企业 AI 底座搭建智能体`，连续覆盖课程 2-1 至 2-9：

- 2-1 至 2-7：通过多轮 Ask User、文件读取和必要的公开检索，形成公司、产品、问答案例、市场、法规和竞品标准资料。
- 2-8：整理脱敏知识库上传包、权限和版本台账；上传、绑定和权限仍由用户在 Accio Work 可见界面完成。
- 2-9：使用 `knowledge-base-plugin` 的 Get/Search 能力完成 RAG 检索验收。
- 私有 Skill 内置 8 份可直接阅读的 DOCX 和 7 份 XLSX，包含扩充后的企业定位与标准公司介绍、产品资料、客户问答、案例、市场、竞品与知识库成果。

该智能体随完整 49-Agent 套装统一安装，也提供[独立安装说明](install/dakying-enterprise-ai-foundation-agent.txt)。目标 Accio Work 环境仍需安装并授权知识库插件。

## 企业知识库问答智能体

完整套装中的第 49 个是 `大客赢 | 企业知识库问答智能体`，用于企业资料完成入库后的日常检索问答：

- 企业知识问题必须先调用 `search_kb_file_contents` 或 `get_kb_file_contents`，不能仅凭模型记忆回答。
- Search 首轮读取 20 个候选块；证据不足时主动更换检索词并提高到 30，必要时最高 50。
- 每次回答都列出实际引用的知识库文件；没有证据时明确说明未找到可引用文件。
- 回答前核对 Memory；知识库与 Memory 不一致时提醒用户判断是否需要更新知识库。

该智能体随完整 49-Agent 套装统一安装，也提供[独立安装说明](install/dakying-enterprise-knowledge-base-qa-agent.txt)。目标 Accio Work 环境仍需安装并授权 `knowledge-base-plugin`。

## v2.7.3 找客户与背调搜索链路修正

本次只更新课程 5-2 至 5-4 的 15 个找客户智能体，以及课程 6-1 的公司背调报告智能体；其余 33 个模板保持不变：

- 公开线索获取和核验统一为 `Search → Fetch → Accio Browser Relay`：Search 建立候选池，Fetch 回读官网与公开正文，Browser Relay 只读复核动态公开页面。
- 全部移除 Apify、外部 Actor、爬虫服务、MCP 采集器和 `accio-mcp-cli` 辅助入口，避免运行时回退到外部批量采集。
- 谷歌搜索找客户、谷歌地图找客户、脸书主页找客户三个纯搜索智能体不声明插件；其余 13 个 Excel 智能体只保留 `spreadsheets`，且只用于生成和复核 Excel，不参与找客户。
- 公司背调报告把原有采集字段改为 Browser Relay 公开页面证据，仍交付“背调报告、联系信息、开发行动计划”三个 Sheet。

完整 49-Agent 套装版本为 `v2.7.3`。发布文件：

- `release/dakying-49-accio-agents-v2.7.3.zip`
- `release/dakying-49-accio-agents-v2.7.3.zip.sha256`
- `install/dakying-49-agents.txt`
