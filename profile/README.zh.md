本文是组织主页中文部分的单独副本，完整三语正文见 [README.md](README.md)。


LexiGate 位于聊天客户端与客户业务库的只读副本之间。**双路径**引擎对常见问题走语义层的固定参数化查询；只有目录未覆盖的问题，才在只读校验、强制 `LIMIT`、`EXPLAIN` 和 RLS 会话检查之后，允许模型生成 SQL。模型生成的回答会带一句温和的「请留意核对」，并附上能走回固定查询的问法提示。

默认部署是 **模式 A**：客户自托管端点，不经过运营方中继，模型跑在客户自己的云账户里。仅出站的 TLS 直通中继（模式 B）是可选项，不用来做许可证控制。企业许可是离线签名文件。

公开架构图里，**LexiGate Semantic Engine**（口径 SQL、罗马音词典、提示词逻辑）是黑盒。公开的是契约：[`semantic_map`](https://github.com/lexigate/lexigate-core/tree/main/spec)、安全原则，以及 MCP 工具形状。

LexiGate 是商标，计划申请日本商标。公开核心的外部贡献采用 DCO，暂不要求 CLA。

- 规范与文档：[lexigate-core](https://github.com/lexigate/lexigate-core)
- 安全问题请私下报告，不要开公开工单（[SECURITY.md](https://github.com/lexigate/lexigate-core/blob/main/SECURITY.md)）
