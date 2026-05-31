# 591 v3.0 进化路线图

> 「大道至简，衍化至繁」——老子
>
> 基于 2025-2026 年全球 AI Agent 生态的外部智慧，合成 591 的下一步进化方向。

---

## 〇、外部智慧全景

### 搜寻范围

| 平台 | 搜寻内容 | 关键发现 |
|------|---------|---------|
| GitHub | 10+ 多Agent框架 | Harmonist(186 agents), OATS(self-improving), Tresor(664★), MetaGPT(48k★) |
| Anthropic | Building Effective Agents | 5可组合模式；大道至简三原则 |
| 学术 | MASPO, EvoAgentX | 联合提示词优化；自动化Agent进化 |
| Claude Code | 生态最佳实践 | 子Agent隔离上下文；Hooks强制>Prompt建议 |

### 核心共识（2025-2026）

```
所有成功的 Agent 系统的共同特征：

1. 简单 > 复杂     — Anthropic: "最成功的实现不使用复杂框架"
2. 契约 > 信任      — Harmonist: "机械执行 > 信任提示词"
3. 独立 > 共享      — Anthropic Research: 子Agent隔离上下文
4. 分层 > 平铺      — OATS: Opus战略 + Sonnet执行
5. 进化 > 固化      — MASPO: 提示词随实战自动优化
```

---

## 一、591 现有优势（已验证的外部验证）

| 591 设计 | 外部验证 |
|---------|---------|
| 生成者 ≠ 批判者 | Anthropic Evaluator-Optimizer 模式 |
| 执行者 ≠ 验证者 | Anthropic Parallelization + Voting 模式 |
| 7 函数分解 | 等价于 Anthropic 5 模式但更完整 |
| 诚实能力边界 | 对齐 Anthropic "不为所有事构建Agent" |
| 进院自进化 | 对齐 MASPO 提示词联合优化 |
| 协省编排 | 对齐 Anthropic Orchestrator-Workers |

---

## 二、v3.0 进化方向

### 方向 1：大道至简——5 模式内化

将 Anthropic 的 5 个可组合模式内化为 591 的原生操作模式：

| Anthropic 模式 | 591 映射 | 使用场景 |
|---------------|---------|---------|
| **Prompt Chaining** | 标准流水线（察→策→谏→协→做→验） | 顺序依赖的多步任务 |
| **Routing** | 协省路由表（单领域→单部 / 复合→多部） | 任务分类与分发 |
| **Parallelization** | 九部并行执行（Sectioning+Voting） | 独立子任务同时处理 |
| **Orchestrator-Workers** | 协省动态分解 + 九部执行 | 未知子任务结构的开放问题 |
| **Evaluator-Optimizer** | 谏省审查 + 验省验证（双环反馈） | 需要迭代优化的任务 |

### 方向 2：契约式 Handoff——从信任到保证

借鉴 Harmonist 的机械执行理念：

```
当前：Agent A 产出 markdown → Agent B "请基于此继续"  (基于信任)
进化：Agent A 产出 {output: markdown, contract: {checks: [...], schema: {...}}} 
      → 协省验证 contract  → Agent B 接收已验证的输入  (基于契约)
```

**新增契约字段**：
- `validation_gate`: 协省在传递前必须检查的条件
- `expected_schema`: 产出的 JSON Schema，验省自动比对
- `confidence_score`: 策省对方案的自评置信度（谏省据此调整审查深度）

### 方向 3：模型分层——用对的人做对的事

借鉴 OATS 的 Manager/CEO 双层模型：

| 591 阶段 | 推荐模型 | 原因 |
|---------|---------|------|
| 察省（问题定义） | Sonnet | 结构化分析，低延迟 |
| 策省（方案生成） | Opus | 需要创造性+多路径思考 |
| 谏省（对抗审查） | Opus | 需要深度推理发现隐藏缺陷 |
| 协省（编排路由） | Sonnet | 结构化任务，低延迟 |
| 九部（执行） | Sonnet | 领域知识应用 |
| 验省（验证） | Sonnet | 逐条对比，结构化 |
| 进院（进化） | Opus | 模式提取需要深度推理 |

### 方向 4：Token 预算意识——量入为出

借鉴 OATS 的 Token 预算断路器：

```
每次任务启动时：
  察省估算任务复杂度（1-5级）
  → 协省根据复杂度分配 Token 预算
  → 各阶段消耗实时追踪
  → 预算消耗 80% 时预警
  → 预算耗尽时自动降级为极速模式
```

### 方向 5：进院自进化——从记录到优化

借鉴 MASPO 的联合提示词优化：

```
当前：进院记录绩效 → 手动 `/591 进化` 触发分析
进化：进院自动检测 → 当某Agent连续3次被驳回/返工 → 自动提示优化建议
```

---

## 三、实施优先级

| 优先级 | 方向 | 投入 | 收益 | 状态 |
|--------|------|------|------|------|
| P0 | 方向1：5模式内化 | 1个新文档 | 让591与行业标准对齐 | ✅ v3.0 |
| P0 | 方向3：模型分层 | CLAUDE.md更新 | 提升每阶段产出质量 | ✅ v3.0 |
| P1 | 方向2：契约式Handoff | Handoff协议升级 | 减少Agent间信息丢失 | 📋 v3.1 |
| P1 | 方向4：Token预算意识 | 新增预算模块 | 防止上下文溢出 | 📋 v3.1 |
| P2 | 方向5：进院自进化 | 进院.md升级 | 实现真正的自进化闭环 | 📋 v3.2 |

---

## 四、与外部项目的对标

| 维度 | 591 | Harmonist | OATS | Tresor | MetaGPT |
|------|-----|-----------|------|--------|---------|
| 核心理念 | 第一性原理 | 机械执行 | 自我改进 | 智能自选 | SOP模拟 |
| Agent 数 | 15 | 186 | 6+skills | 141 | ~5 |
| 手协议 | Handoff数据包 | 机械gate | 契约 | 自动选择 | SOP |
| 模型分层 | ✅ v3.0 | ❌ | ✅ Opus/Sonnet | ✅ 自动 | ❌ |
| 自进化 | 进院 | ❌ | ✅ validator | ❌ | ❌ |
| 诚实边界 | ✅ | ❌ | ✅ | ❌ | ❌ |
| 部署方式 | Markdown | Git hooks | Bash | Markdown | Python |

**591 的独特优势**：第一性原理基础 + 诚实边界 + 中华经典框架 + 全 Markdown 零依赖部署

---

## 五、一句话总结

> **591 v3.0 = 7 函数（不变核心）+ 5 模式（Anthropic 内化）+ 15 Agent（角色库）+ 契约协议（Harmonist 启发）× 大道至简（行业共识）**
>
> 不只是设计文档和提示词。是经过 4 循环 PDCA 自我审查、对齐全球最佳实践、可以在任何 Claude Code 中加载使用的通用解题引擎。
