# 🧠 AIS 中文说明

这是一个符合 **Agent Skill 标准** 的本地技能包，用于通过远端 HTTP 执行服务，操作 **TorchV AIS / 知识库（KB）**。

---

## 🎯 核心目标

本 Skill 的设计目标是：

* 🚫 **无需本机/Agent安装额外依赖**
* 🌐 所有 `kb ...` 命令统一通过远端执行
* 🔁 使用 `scripts/kb_execute.py` 转发命令
* 📦 支持完整文件能力（上传 / 下载 / 链接生成）
* 🧭 为 Agent 提供清晰的 **操作工作流约束**

---

## 🧩 工作原理

```text
Agent → kb_execute.py → HTTP → AIS 执行服务 → 返回结果
```

本地只负责“转发”，所有实际执行发生在远端 AIS。

---

## 📁 项目结构

```bash
.
├── README.md
├── SKILL.md                # 技能主文件（核心入口）
├── references              # 详细能力说明
│   ├── read.md             # 读取 / 搜索 / 定位
│   ├── write.md            # 新建 / 发布 / 结构操作
│   ├── update.md           # patch 修改
│   └── file-transfer.md    # 文件传输能力
└── scripts
    └── kb_execute.py       # 命令转发核心
```
* 📘 `SKILL.md`：定义术语、执行约束、默认工作流（**Agent 必读**）
* 🔍 `references/read.md`：读取 / 搜索 / 渲染链接
* ✏️ `references/write.md`：创建 / 复制 / 移动 / 删除 / 发布
* 🧬 `references/update.md`：基于 patch 的精确修改
* 📦 `references/file-transfer.md`：上传 / 下载 / 下载链接
* ⚙️ `scripts/kb_execute.py`：命令转发入口（核心执行点）

---

## 🚀 快速开始

👉 下载本项目 zip，交给你的 Agent 安装即可使用

---

## ⚙️ 环境配置

推荐使用环境变量：

```bash
export KB_EXECUTE_URL="https://aisdevserver.dev.torchv.com/kb/atomix/execute"
export KB_TOKEN="xxxxxx"
```

---

### 🧪 或者显式调用

将你的url、token告知agent。
它将通过运行时指定：
```bash
./scripts/kb_execute.py \
  --url "https://aisdevserver.dev.torchv.com/kb/atomix/execute" \
  --token "xxxxxx" \
  "kb ls"
```

---

## 🌐 获取 `KB_EXECUTE_URL`

`KB_EXECUTE_URL` 是 AIS 知识库执行接口地址。

📌 获取方式：

1. 打开你正在使用的 AIS 页面（例如：`https://ais.xxx.com`）
2. 在域名后拼接：

```
/kb/atomix/execute
```

👉 示例：

```text
https://bot.torchv.com/kb/atomix/execute
```

---

## 🔐 获取 `KB_TOKEN`

推荐方式：

```
AIS → 管理中心 → 开放密钥 → 创建密钥
```

临时方式（仅调试使用）：

```
浏览器开发者工具 → Network → 复制 token / Authorization
```

---

## 🔌 需要 MCP 版本？

👉 [https://github.com/torchv/ais-mcp](https://github.com/torchv/ais-mcp)

---

## 🧠 关于 AIS

TorchV 的核心产品是 **AIS（AI 知识引擎）**。

它不是传统知识库，而是：

> 🧠 **企业级 AI 知识引擎系统**

核心能力：

* 🔄 将分散数据 → 转化为结构化知识
* 🔍 可检索（Searchable）
* 🧩 可治理（Governable）
* ⚡ 可调用（Composable）
* 📈 可优化（Optimizable）

---

## 🎁 试用 AIS

📲 扫码联系（CEO微信）：

![img.png](resource/wechat.png)
