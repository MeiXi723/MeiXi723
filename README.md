# 美熙723

写 AI 应用和服务器部署。习惯把踩过的坑记下来。

---

## 在做什么

三件事，按花的时间排序：

**RAG 和 Agent 工程。** 检索质量、上下文预算、token 成本 —— 这些没人在 demo 里讲、但真上线就要命的部分。

**服务器部署。** 装 PasarGuard 的时候被官方脚本坑了五次，索性把补丁写成脚本。

**中文文档。** 我觉得这是国内开源最缺的东西。所以我的项目文档比代码长。

---

## 项目

### [pasarguard-cn](https://github.com/MeiXi723/pasarguard-cn)

`Shell` · PasarGuard 官方安装脚本的中文安全加固外壳

官方脚本装完 `admins` 表是空的，面板登不进去；pgadmin 默认把 25 端口开到公网，几天内就会被扫成垃圾邮件中继。这两个我在自己机器上都踩到了，所以写了这个。

不 fork 官方代码，每次运行重新拉取 —— 官方更新你自动受益。

<sub>只在 Debian 12 上完整测过。Ubuntu 和 arm64 没测，README 里写明了。</sub>

---

### [research-agent](https://github.com/MeiXi723/research-agent)

`Python` · 从零实现的 ReAct 研究智能体

v1 那套 30 个测试里有 13 个是坏的，全绿也跑不起来。v2 重写成四层测试，168 个用例 + 5 个 e2e。

真实基准 90 题，retrieval recall@5 均值 92.2%。

<sub>MCP 子进程的网络出口管不住，需要宿主防火墙兜底。这条写在 README 的「已知限制」里。</sub>

---

### [rag-qa](https://github.com/MeiXi723/rag-qa)

`Python` · 金融文档 RAG 问答后端

BM25 + 向量双路召回，RRF 融合，CrossEncoder 精排（可选，不装就静默降级）。答案带 `answer_confidence` 三档，会告诉你它是不是在编。

<sub>FAISS 用的还是 Flat 索引，O(N)。数据量上来必须换 HNSW，现在没换。</sub>

---

## 一些事实

| | |
| :--- | :--- |
| 公开项目 | 3 个，都是自己写的 |
| 测试用例 | 240+ |
| 过去一年提交 | 128 次 |
| 会写 | Python · Shell · Nginx |
| 不太会 | C++ · Rust（在学，很慢） |

---

<sub>所有项目均为个人作品，与所封装的上游项目无隶属关系。</sub>
