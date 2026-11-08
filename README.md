<div align="center">

# 美熙723

**把「能用」做到「敢给别人用」**

AI 应用 · 服务器基础设施 · 中文文档强迫症

</div>

---

## 我在干什么

做 AI 应用（RAG、Agent）和服务器基础设施（代理、部署、运维）。

代码写得越多越发现一件事：**让程序跑起来只要一天，让人敢用它要一个月。**

所以我的项目有个共同点 —— 文档比代码长，**已知限制写得比特性还清楚**。
我不写"完美支持 X"，我只写"我在哪台机器上跑通过，哪里还没测"。

---

## 项目

### ⚡ [pasarguard-cn](https://github.com/MeiXi723/pasarguard-cn)

> PasarGuard 官方安装脚本的中文安全加固外壳 · `Shell`

官方脚本本身很强：5 种数据库、Let's Encrypt、多节点、8 个发行版支持。
但在自己机器上装的时候，有五个坑得手工补：

| 官方留下的坑 | 这个项目怎么补 |
| :--- | :--- |
| 装完 `admins` 表是空的，面板登不进去 | 自动创建 owner 账号 |
| pgadmin 默认启动并暴露 25 端口 | 默认不启动，端口封掉 |
| 没有 `--yes`，只能一路交互 | 全参数化，一条命令装完 |
| 报错和提示全英文 | 中文交互 + 中文排障表 |
| 国内拉 Docker 镜像慢 | 镜像测速优选 |

**不 fork、不复制官方代码。** 每次运行重新拉取官方脚本，所以官方更新你自动受益。

<sub>实测范围：Debian 12 · 全新安装 / 幂等重跑 / 端到端自检全绿</sub>

---

### 🧠 [research-agent](https://github.com/MeiXi723/research-agent)

> 从零实现的 ReAct 研究智能体 · `Python`

MCP 工具协议、多角色流水线、FAISS 语义记忆、三层漏斗意图路由。

```
四层测试      168 单测/集成 + 5 e2e
真实基准      HotpotQA / 2Wiki / MuSiQue 90 题 · recall@5 均值 92.2%
端到端        EM 60% · LLM-judge 90% · 2,976 token/题
```

<sub>为什么这些数字重要：v1 那套 30 个测试里 13 个是坏的，跑绿了也跑不起来。</sub>

---

### 📊 [rag-qa](https://github.com/MeiXi723/rag-qa)

> 金融文档 RAG 问答后端 · `Python`

FastAPI + FAISS/BM25 双路检索 → RRF 融合 → CrossEncoder 精排 → 答案置信度。
JWT 认证、Docker 一键起、72 个测试。

<sub>检索层移植自 AFAC2026 参赛管道，不是玩具 demo。</sub>

---

## 技术栈

`Python` `FastAPI` `FAISS` `BM25` `LangGraph` `MCP` `Docker` `Shell` `Nginx`

---

## 一点数字

| | |
| :--- | :--- |
| 公开项目 | 3 个 |
| 测试用例 | 240+ |
| 过去一年提交 | 128 次 |

---

<div align="center">
<sub>所有项目均为个人作品，与所封装的上游项目无隶属关系。</sub>
</div>
