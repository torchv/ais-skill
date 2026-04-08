# AIS Skill Overview
  
[English](README.md) | [中文](README_CN.md)  
  
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  
  
This is a local skill package compliant with the **Agent Skill standard**, designed to operate the **TorchV AIS Knowledge Base (KB)** via remote HTTP execution.  
  
---  
  
## 🎯 Design Goals  
  
This skill is designed with the following principles:  
  
* 🚫 **No local dependencies required** for the agent or runtime  
* 🌐 All `kb ...` commands are executed remotely  
* 🔁 Commands are forwarded via `scripts/kb_execute.py`  
* 📦 Full file capabilities (upload / download / link generation)  
* 🧭 Clear and structured **workflow constraints for agents**  
  
---  
  
## 🧩 How It Works  
  
```text  
Agent → kb_execute.py → HTTP → AIS Execution Service → Response  
```  
  
The local environment acts only as a **forwarding layer** — all actual execution happens in AIS remotely.  
  
---  
  
## 📁 Project Structure  
  
```bash  
.  
├── README.md  
├── SKILL.md                # Core skill definition (entry point)  
├── references              # Detailed capability docs  
│   ├── read.md             # Read / search / locate  
│   ├── write.md            # Create / publish / structure ops  
│   ├── update.md           # Patch-based updates  
│   └── file-transfer.md    # File operations  
└── scripts  
    └── kb_execute.py       # Command forwarding core```  
  
### Key Components  
  
* 📘 `SKILL.md`  
  Defines terminology, execution constraints, and default workflows (**must-read for agents**)  
  
* 🔍 `references/read.md`  
  Read, search, and link rendering capabilities  
  
* ✏️ `references/write.md`  
  Create, copy, move, delete, and publish operations  
  
* 🧬 `references/update.md`  
  Precise modifications using patch semantics  
  
* 📦 `references/file-transfer.md`  
  Upload, download, and link generation  
  
* ⚙️ `scripts/kb_execute.py`  
  Core execution entry (command forwarding layer)  
  
---  
  
## 🚀 Quick Start  
  
👉 Download this repository (ZIP) and load it into your agent environment to start using it.  
Or
**get from clawhub**: https://clawhub.ai/liuchuan01/ais-skill
**get from clawhub**: https://clawhub.ai/liuchuan01/ais-skill
---  
  
## ⚙️ Configuration  
  
It is recommended to use environment variables:  
  
```bash  
export KB_EXECUTE_URL="https://bot.torchv.com"
export KB_TOKEN="your-token"
```  
  
---  
  
### 🧪 Or Invoke Explicitly  
  
You can also provide the URL and token directly to the agent, which will execute commands like:  
  
```bash  
./scripts/kb_execute.py \
  --url "https://bot.torchv.com" \
  --token "your-token" \
  "kb ls"
```  
  
---  
  
### 🌐 Getting `KB_EXECUTE_URL`  
  
`KB_EXECUTE_URL` only needs the AIS site address.  
  
📌 Steps:

1. Open your AIS instance
2. Copy the site origin from the browser address bar

👉 Example:

```text
https://bot.torchv.com
```
---  
  
### 🔐 Getting `KB_TOKEN`  
  
**Recommended:**  
  
```  
AIS → Admin Center → API Keys → Create Key  
```  
  
**Temporary (for debugging only):**  
  
```  
Browser DevTools → Network → Copy token / Authorization header  
```  
  
---  
  
## 🔌 Looking for MCP Version?  
  
👉 [https://github.com/torchv/ais-mcp](https://github.com/torchv/ais-mcp)  
  
---  
  
## 🧠 About AIS  
  
AIS is TorchV’s core product — not a traditional knowledge base, but:  
  
> 🧠 **An Enterprise AI Knowledge Engine**  
  
### Core Capabilities  
  
* 🔄 Transform scattered data → structured knowledge  
* 🔍 Searchable  
* 🧩 Governable  
* ⚡ Composable  
* 📈 Optimizable  
  
---  
  
## 🎁 Try AIS  
  
📲 Contact us (CEO WeChat):  
  
![img.png](resource/wechat.png)