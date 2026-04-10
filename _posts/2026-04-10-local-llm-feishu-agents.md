---
layout: post
title: "本地部署大模型，手机飞书接入家里的五个 agent"
date: 2026-04-10 10:00:00 +0800
categories: [tech]
author: "Hilalum"
tags: [tech, ai, omlx, ccconnect, feishu, m1pro]
summary: "从闲鱼 4000 块的无头 M1 Pro 开始，我把家里的 Mac 变成了一台 7x24 小时在线的多智能体中心，并将其通过 Feishu 接入手机。"
---

这篇文章的开头要从一次捡漏说起。

最近我在闲鱼上以 4000 块的价格，蹲到了一台 **M1 Pro (10 核) + 32GB 内存** 的“无头”MacBook Pro。所谓“无头”，就是屏幕碎了或者直接被拆掉了，只能当迷你主机用。

在此之前，我一直用的是一台 M2 芯片、16GB 内存的 Mac Mini。原本觉得 M2 的单核性能挺香，但真折腾起本地大模型（LLM）来，**内存大小才是唯一的真理**。16GB 内存扣掉系统开销，跑个稍微大点的模型（比如 Llama-3-70B 的量化版）就捉襟见肘，更别提同时跑多个 agent 了。

换上这台 32GB 的 M1 Pro 后，我终于可以随心所欲地在本地部署两个主力模型，并让五个不同分工的 Agent 常驻在线。

# 为什么从微信换到飞书

很多人问我：既然是自己用的 Agent，为什么不直接接入微信？

理由很简单：**微信不是为开发者准备的，但飞书是。**

1. **API 友好度**：微信的个人号机器人全靠 Hook 或者各种非官方协议，随时面临封号风险。而飞书（Lark）提供了官方的机器人开发平台，支持 Webhook、事件订阅、富文本消息卡片，稳定性极高。
2. **多 Agent 隔离**：在飞书里，我可以轻松创建五个互不干扰的机器人，分别对应不同的 Agent。而在微信里，想在同一个对话框里调配五个身份，体验非常割裂。
3. **消息卡片**：飞书的消息卡片支持 Markdown、交互按钮、多列布局。当我的 Agent 返回一段代码或者对比图表时，飞书的渲染效果远超微信。

# 架构设计

整套系统的架构非常清晰，分为三层：

1. **LLM 基础设施层 (`omlx`)**：利用 Apple Silicon 的统一内存架构，高效运行量化后的 LLM。
2. **智能体逻辑层 (`Agents`)**：定义五个具有不同 Prompt 和 Tools 的独立 Agent。
3. **连接层 (`ccconnect`)**：作为中间件，将本地 Agent 的输入输出映射到飞书机器人的 API。

# 第一步：使用 omlx 本地部署模型

**omlx** 是我最近发现的一个针对 Apple Silicon 深度优化的本地模型推理工具（基于 MLX 框架）。它的特点是冷启动极快，且能最大限度压榨 M1/M2/M3 芯片的带宽。

在我的这台 M1 Pro 上，我部署了两个模型：
- **主力模型**：用于复杂逻辑推理和代码生成（如 Llama-3-70B-Instruct 的 4-bit 量化版）。
- **轻量模型**：用于简单的文本分类、意图识别和快速响应（如 Mistral-7B 或 Phi-3）。

### 部署过程：

首先确保安装了 `omlx`：
```bash
brew install omlx
```

接着下载并运行模型：
```bash
omlx serve --model llama-3-70b-4bit --port 8080
omlx serve --model phi-3-mini --port 8081
```

得益于 32GB 的统一内存，这两个模型可以同时驻留在内存中，响应速度非常理想。

# 第二步：五个 Agent 的设定

我并没有搞一个“全能”的机器人，而是将其功能拆解到了五个垂直的 Agent 中：

1. **Code Expert (代码专家)**：接入主力模型，拥有最高的上下文长度，专门写代码和 Review。
2. **Research Assistant (研究助手)**：带搜索工具，专门帮我总结网页和论文。
3. **Daily Planner (日程管家)**：对接了我的日历和待办清单。
4. **Content Creator (文案手)**：风格偏向创意写作。
5. **System Monitor (监控哨兵)**：负责监控家里服务器的运行状态，出问题主动推送。

# 第三步：使用 ccconnect 接入飞书

这是最关键的一步。**ccconnect** 是一个强大的多端连接器，它可以将本地运行的各种 Agent（支持 OpenAI 格式接口）桥接到不同的 IM 平台。

### 配置流程：

1. **在飞书开发者后台创建五个机器人**，并拿到它们的 `App ID` 和 `App Secret`。
2. **配置 `ccconnect.yaml`**，定义每个 Agent 指向的飞书机器人以及对应的本地模型接口：

```yaml
connectors:
  - name: "code-agent"
    platform: feishu
    app_id: "cli_xxxxx"
    app_secret: "yyyyy"
    model_endpoint: "http://localhost:8080/v1"
    system_prompt: "You are a senior software engineer..."
  
  - name: "research-agent"
    platform: feishu
    app_id: "cli_zzzzz"
    app_secret: "wwwwww"
    model_endpoint: "http://localhost:8081/v1"
    system_prompt: "You are a meticulous researcher..."
  # ... 其他三个配置
```

3. **启动 `ccconnect`**：
```bash
ccconnect start --config ./ccconnect.yaml
```

# 实际体验

现在，我无论是在排队买咖啡，还是在通勤路上，只要打开手机飞书，就能随时召唤这五个 Agent。

- **情景 A**：想起一个 Bug 没修，给“代码专家”发一段描述，它直接在本地跑完逻辑，把 Diff 传给我看。
- **情景 B**：刷到一篇长文章没空看，直接转发给“研究助手”，它一分钟内把要点总结好发到对话框。

这种把**高性能算力留在家里，把交互界面装进口袋**的感觉，真的比单纯在手机上用网页版 ChatGPT 要爽得多。

# 总结

这次“无头 MBP”的升级是非常成功的。对于想要玩转本地大模型的朋友，我的建议是：**别看 CPU 核心数，直接看内存。** 32GB 是起步，64GB 是天堂。

而通过 `omlx` + `ccconnect` + `飞书` 的组合，我成功把一台廉价的闲鱼二手 Mac 变成了全家人的“智能大脑”。这套方案低成本、高效率、隐私受控，非常推荐给各位折腾党。
