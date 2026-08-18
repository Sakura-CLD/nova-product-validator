# NOVA Framework — 创新产品机会验证方法论

> 一个 Claude Code Skill，帮你系统性地回答：**「这个创新产品为什么不会重蹈前人覆辙？」**

## 简介

NOVA Framework 是一套面向创新产品的 7 节点机会验证方法论，适用于：

- 产品立项前的可行性论证
- 竞品与失败案例的精确归因
- 蓝海/红海判断 + 护城河体系设计
- 项目方向可行性论证

## 快速使用

在 Claude Code 中直接调用：

```
/Product Feasibility Analysis
```

或描述你的产品方向，包含以下关键词之一即可自动触发：
`创新产品` · `这个方向有没有机会` · `和失败产品有什么不同` · `蓝海还是红海` · `护城河` · `商业化` · `竞品分析`

## 7 个分析节点

```
Node 0：机会信号捕捉      → 需求/资本/供给缺口信号
Node 1：本质解构（北极星）→ 产品本质声明 [所有节点的对齐基准]
         ↓ 同时并行 ↓
Node 7：政策合规扫描      → 风险等级评定（红/橙/黄/绿）
Node 2：失败案例归因      → 归因矩阵（结构性/执行性/时机性）
Node 3：用户需求验证      → 止痛药 or 维生素 + 付费意愿
Node 4：市场格局判断      → 蓝海/红海 + TAM/SAM/SOM
Node 5：差异化与护城河    → 7 Powers + 四维差异化 + 时间线
Node 6：商业化可行性      → 商业模式 + LTV/CAC + 业务加成
```

## 三种执行模式

| 模式 | 时长 | 包含节点 | 适用场景 |
|------|------|----------|----------|
| 快速验证 | ~1小时 | Node 1 + 2 + 7 | 快速筛选方向 |
| 完整分析 | 半天 | 全部 7 节点 | 立项 / BP 准备 |
| 面试准备 | ~30分钟 | 重点输出标准答法 | 求职 / 投资人对话 |

## 输出示例

```
## [产品名] 机会验证报告

### 一句话结论
[产品本质声明]——我们的竞争对手不是 X，而是 Y。

### 核心论证（三层）
1. 为什么需求是真实的（Node 0+3）
2. 为什么我们不会重蹈前人覆辙（Node 1+2）
3. 为什么我们能赢（Node 5）

### 最大风险与应对
政策风险：[等级] + [说明]
主动承认：[可直接使用的措辞]
```

## 仓库结构

```
Product Feasibility Analysis/
├── SKILL.md              # Skill 主入口（Claude Code 读取）
├── README.md             # 本文件
├── agents/
│   ├── grader.md         # 评测执行结果的 Grader Agent
│   ├── analyzer.md       # 对比分析 Agent
│   └── comparator.md     # 盲测比较 Agent
├── eval-viewer/
│   ├── viewer.html       # 评测结果可视化页面
│   └── generate_review.py
├── evals/
│   └── evals.json        # 6 条测试用例（含正/负样本）
├── references/           # 7 节点详细执行手册
│   ├── node-0-signal.md
│   ├── node-1-essence.md
│   ├── node-2-failure.md
│   ├── node-3-user.md
│   ├── node-4-market.md
│   ├── node-5-moat.md
│   ├── node-6-business.md
│   └── node-7-risk.md
└── scripts/              # Eval 自动化脚本
    ├── run_eval.py       # 运行单次评测
    ├── run_loop.py       # 循环优化 description
    ├── improve_description.py
    └── utils.py
```

## 运行评测

```bash
# 安装依赖（需要 Python 3.10+）
pip install anthropic

# 运行触发率评测
python scripts/run_eval.py --skill-path . --model claude-opus-5

# 循环优化 description 直到全部通过
python scripts/run_loop.py --skill-path . --max-iterations 5
```

## 核心方法论来源

- **7 Powers**（Hamilton Helmer）— 护城河分析框架
- **JTBD**（Jobs-to-be-Done）— 产品本质重新定义
- **Blue Ocean Strategy** — 战略画布 + 蓝海/红海判断
- **Sean Ellis PMF Test** — 产品市场契合度验证
- **CB Insights 失败归因** — 结构性 vs 执行性失败区分

## License

MIT
