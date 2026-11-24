# LexiGate

A semantic gateway between **Microsoft Teams** (and other chat fronts) and **AWS business databases** (RDS / Aurora, PostgreSQL and MySQL). People ask in everyday language; answers come from a governed semantic layer. Raw business rows stay in the customer VPC.

Open-Core: the architecture, the `semantic_map` contract, and a local demo toolkit are public; enterprise governance (Entra ID row-level security, audit export, outbound tunnel, admin console) is commercial and private.

**Start here:** [lexigate-core](https://github.com/lexigate/lexigate-core) (Apache License 2.0).

> The first publication is documentation, the v0 specification, and fictional demo data. The scanner CLI and a runnable local demo are planned next and are not shipped yet.

---

## English

LexiGate sits between a chat client and a read-only copy of the customer’s database. A **dual-path** engine answers common questions with fixed, parameterized metric queries, and only falls back to model-generated SQL (behind read-only, `LIMIT`, `EXPLAIN`, and RLS session checks) when the catalog does not cover the question. Generated answers carry a soft “please double-check” note and suggested follow-ups that steer the next question back onto a fixed query.

The default deployment is **Mode A**: a customer-hosted endpoint, no operator relay, bring-your-own model in the customer account. An outbound-only TLS passthrough (Mode B) is optional and is not used as license enforcement. Enterprise licensing is an offline signed file.

The **LexiGate Semantic Engine** (metric SQL, romaji dictionaries, prompt logic) is a black box in the public diagram. What *is* public is the contract: [`semantic_map`](https://github.com/lexigate/lexigate-core/tree/main/spec), the security principles, and the MCP tool shapes.

The name LexiGate is a trademark; a Japanese application is planned. Contributions to the open core use the Developer Certificate of Origin (no CLA for now).

- Specification and docs: [lexigate-core](https://github.com/lexigate/lexigate-core)
- Security reports: please use a private advisory, not a public issue ([SECURITY.md](https://github.com/lexigate/lexigate-core/blob/main/SECURITY.md))

---

## 中文

LexiGate 位于聊天客户端与客户业务库的只读副本之间。**双路径**引擎对常见问题走语义层的固定参数化查询；只有目录未覆盖的问题，才在只读校验、强制 `LIMIT`、`EXPLAIN` 和 RLS 会话检查之后，允许模型生成 SQL。模型生成的回答会带一句温和的「请留意核对」，并附上能走回固定查询的问法提示。

默认部署是 **模式 A**：客户自托管端点，不经过运营方中继，模型跑在客户自己的云账户里。仅出站的 TLS 直通中继（模式 B）是可选项，不用来做许可证控制。企业许可是离线签名文件。

公开架构图里，**LexiGate Semantic Engine**（口径 SQL、罗马音词典、提示词逻辑）是黑盒。公开的是契约：[`semantic_map`](https://github.com/lexigate/lexigate-core/tree/main/spec)、安全原则，以及 MCP 工具形状。

LexiGate 是商标，计划申请日本商标。公开核心的外部贡献采用 DCO，暂不要求 CLA。

- 规范与文档：[lexigate-core](https://github.com/lexigate/lexigate-core)
- 安全问题请私下报告，不要开公开工单（[SECURITY.md](https://github.com/lexigate/lexigate-core/blob/main/SECURITY.md)）

---

## 日本語

LexiGate は、チャットのクライアントと、お客様の業務データベースの読み取り専用コピーの間に置きます。**二経路**のエンジンは、よくある質問をセマンティック層の固定パラメータ付きクエリで答え、カタログがカバーしていない質問だけ、読み取り専用チェック、必須の `LIMIT`、`EXPLAIN`、RLS セッションを通したうえで、モデルに SQL を生成させます。モデルが作った回答には「念のため内容をご確認ください」と控えめに注記し、次は固定クエリで聞けるような問い方のヒントを付けます。

既定の導入は **モード A** です。エンドポイントはお客様がホストし、運営者の中継は使いません。モデルはお客様自身のクラウドアカウントで動かします。アウトバウンドのみの TLS パススルー中継（モード B）は任意であり、ライセンスの強制手段にはしません。エンタープライズのライセンスはオフラインの署名ファイルです。

公開アーキテクチャ図では、**LexiGate Semantic Engine**（口径 SQL、ローマ字辞書、プロンプト論理）をブラックボックスとして描きます。公開するのは契約です。[`semantic_map`](https://github.com/lexigate/lexigate-core/tree/main/spec)、セキュリティの原則、MCP ツールの形です。

LexiGate は商標であり、日本での出願を予定しています。オープンコアへの貢献は DCO で受け付け、現時点で CLA は求めません。

- 仕様と文書：[lexigate-core](https://github.com/lexigate/lexigate-core)
- 脆弱性は公開 Issue ではなく、非公開でご報告ください（[SECURITY.md](https://github.com/lexigate/lexigate-core/blob/main/SECURITY.md)）
