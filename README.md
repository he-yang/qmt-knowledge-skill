# qmt-knowledge-skill

**迅投 QMT 极速策略交易系统 — AI Agent 智能知识技能包**

[![Version](https://img.shields.io/badge/version-0.2.0-blue.svg)](https://clawhub.ai/he-yang/skills/qmt-knowledge-skill)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](./LICENSE)

为 AI Agent提供结构化的 讯投QMT API 知识库，实现 API 查询、策略代码生成、回测/实盘配置指导、枚举常量查档、常见问题排查等能力。**本 Skill 仅基于本地知识库作答，不进行任何外部网络抓取**。

---

## ✨ 功能特性

本 Skill **仅在用户主动提出 QMT 相关需求时激活**，不主动介入非 QMT 上下文。适用场景如下：

| 场景 | 示例问题 |
|---|---|
| 📖 **新手入门** | 「QMT 怎么运行第一个策略？」「回测和实盘模型有什么区别？」 |
| 💻 **代码生成** | 「帮我写一个双均线策略」「写一个获取全市场 Tick 的脚本」 |
| 🔎 **API 查询** | 「passorder 的参数有哪些？」「get_market_data_ex 怎么用？」 |
| 🎯 **枚举参数** | 「opType 股票买入是多少？」「prType 最新价对应值？」 |
| 🧱 **数据结构** | 「Tick 对象有哪些字段？」「Bar 数据包含什么？」 |
| ⚠️ **错误排查** | 「为什么下单是废单？」「取行情数据为空怎么办？」「pandas 报错如何解决？」 |
| 📊 **指标公式** | 「MA、MACD、RSI、KDJ 怎么引用？」 |
| 🛠️ **环境配置** | 「如何下载历史数据？」「模拟账号和实盘账号区别？」 |

---

## 📁 项目结构

```
qmt-knowledge-skill/
├── SKILL.md              # ⭐ Skill 主入口（Agent 行为规范 + 索引 + 约束）
├── README.md             # 本文件
└── knowledge/            # QMT 官方知识库（按四大类共 16 份文档）
    ├── 01-入门/
    │   ├── 快速开始.md                 # QMT架构总览 / 回测实盘对比 / 三种运行机制
    │   ├── QMT新人上手教程.md          # 从零开始上手步骤
    │   ├── 迅投研新手指南.md           # 迅投研云端版本指引
    │   ├── 使用须知.md                 # Python 3.6 环境 / 白名单 / 账号类型
    │   ├── 变量约定.md                 # ContextInfo / 运行模式 / 变量规范
    │   └── 界面操作.md                 # 账号配置 / 数据管理 / 模型交易界面
    ├── 02-API/
    │   ├── 交易函数.md                 # ⭐ passorder 综合下单 / 持仓查询 / 撤单改单
    │   ├── 行情函数.md                 # 下载 / 获取 / 订阅 / Tick 快照全套
    │   ├── 引用函数.md                 # MA/EMA/MACD/RSI/KDJ/DMI/BOLL/ATR 等指标
    │   ├── 系统函数.md                 # run_time / 板块 / is_last_bar 等
    │   ├── 成交回报实时主推函数.md      # 委托/成交/持仓/资金变动回调
    │   └── 绘图函数.md                 # paint/drawline/LINETHICK/COLOR 等
    ├── 03-数据与枚举/
    │   ├── 枚举常量.md                 # ⚠️ opType/orderType/prType/市场代码 等
    │   └── 数据结构.md                 # Tick/Bar/L2Quote/Position/Account 等字段
    └── 04-示例与FAQ/
        ├── 完整示例.md                 # 两融/K线全推/目标持仓/快速交易/组合套利 模板
        └── 常见问题.md                 # 白名单报错/编码/废单/数据空等高频问题
```

---



## 安装 Skill 到 AI 工具

安装方法 1， 使用命令行安装：

```
openclaw skills install @he-yang/qmt-knowledge-skill
```

安装方法 2， 使用命令行安装：

```
npx skills add https://clawhub.ai/he-yang/skills/qmt-knowledge-skill
```

安装方法 3， 自行导入安装：

下载项目代码：
1. 从本github 仓库直接克隆；
2. 从夸克网盘下载： [https://pan.quark.cn/s/a9103f859084](https://pan.quark.cn/s/a9103f859084)

下载后，将项目代码导入到 AI 工具中。

比如 workbuddy， 找到左侧的`专家·技能·连接器`，点击上侧的`技能`，点击`添加技能` -> `上传技能`，然后导入下载的代码。

## 📋 QMT 策略代码核心约束（重点）

本 Skill 内置以下硬性编码规范，生成的代码全部符合 QMT 内置 Python 3.6 环境要求：

| 规则 | 说明 |
|---|---|
| 🔤 **GBK 编码** | 所有脚本第一行必须写 `# coding:gbk`，否则中文乱码 |
| 🪝 **双钩子结构** | 必须有 `def init(ContextInfo):` + `def handlebar(ContextInfo):` |
| 🐍 **Python 3.6** | 不支持 3.7+ 语法特性（如 f-string = 3.6 可用，但 dataclass/walrus operator 不可用） |
| 📊 **第三方库** | 默认自带 NumPy/Pandas/TA-Lib/SciPy，其他库需要券商开通白名单 |
| 🔢 **枚举值** | opType/orderType/prType 等必须使用 `枚举常量.md` 中合法数值，禁止臆造 |
| ⚠️ **实盘风险** | 所有生成的 passorder 代码自动附带风险提示语 |

### 代码模板

```python
# coding:gbk

"""
功能：XXX 策略
模式：回测模型 / 实盘模型
机制：逐K线 handlebar / 订阅 subscribe / 定时 run_time
"""

account = "test"  # 策略交易界面运行时会自动替换为配置账号

def init(ContextInfo):
    """初始化，策略启动时仅执行一次"""
    pass

def handlebar(ContextInfo):
    """逐K线回调，核心策略逻辑"""
    pass
```

---

## 🧭 高频 API 速览

| # | 功能 | 核心函数 | 知识库位置 |
|---|---|---|---|
| 1 | 🛒 综合下单 | `passorder(...)` | 02-API/交易函数.md |
| 2 | 📈 获取K线行情 | `ContextInfo.get_market_data_ex(...)` | 02-API/行情函数.md |
| 3 | ⬇️ 下载历史数据 | `download_history_data(...)` | 02-API/行情函数.md |
| 4 | 📡 订阅行情回调 | `ContextInfo.subscribe_quote(...)` | 02-API/行情函数.md |
| 5 | 📊 获取 Tick 快照 | `get_full_tick(...)` | 02-API/行情函数.md |
| 6 | 🏦 查持仓/资金 | `ContextInfo.get_trade_detail_data(...)` | 02-API/交易函数.md |
| 7 | 🏭 获取板块成分 | `ContextInfo.get_stock_list_in_sector(...)` | 02-API/系统函数.md |
| 8 | 📐 技术指标 | `MA(...)` / `MACD(...)` / `RSI(...)` 等 | 02-API/引用函数.md |

---

## 🤝 贡献指南

欢迎提交 Issue 或 PR 维护更新知识库：

1. **更新文档**：对应修改 `knowledge/` 下分类 md 文件
2. **新增文档**：放入最合适的分类目录（01-入门 / 02-API / 03-数据与枚举 / 04-示例与FAQ）
3. **SKILL.md 同步**：若新增分类或关键 API，记得同步更新 [SKILL.md](file://./SKILL.md) 中的索引表
4. **保持中文**：所有文档使用中文撰写，与 QMT 官方文档语言一致

提交前请确认：
- 文档中的枚举值、参数列表与 QMT 客户端实际表现一致
- 代码示例均包含 `# coding:gbk` 和 init/handlebar 结构
- 涉及实盘的代码样例默认使用 `quicktrade=0`（逐K线安全模式）

---

## ⚠️ 免责声明

> **量化交易存在巨大风险**。本项目仅提供 QMT API 文档的知识结构化整理与 AI Agent 辅助能力：
> - 生成的所有策略代码仅供学习参考，**不构成任何投资建议**
> - 实盘交易前务必在「模拟信号模式」或「模拟柜台」中充分验证策略逻辑
> - 因使用本项目代码、文档造成的任何盈亏，由使用者自行承担全部责任

QMT、迅投 为迅投公司或其关联公司的商标。本项目仅为社区用户自发整理的非官方知识库。

---

## 📄 License

MIT License

---

## 📋 Changelog

### v0.1.0 (2026-08-11)
首次发布

### v0.2.0 (2026-08-12)

#### 安全加固
- **移除外部 WebFetch Fallback 机制**，改为纯本地知识库模式，不进行任何外部网络抓取
- **收紧触发条件**：description 与 README 措辞改为"用户明确请求 / 主动提出"时才激活，不主动介入非 QMT 上下文
- **下单示例就近强警告**：所有含 `passorder` / `quickTrade=2` 的代码块紧邻位置添加 🚫 高风险警示框
- **敏感字段脱敏**：账号 ID、AccountKey、委托号、资产金额等在示例输出中全部脱敏
- **维护性操作警示**：Lib 文件夹删除、策略导出导入章节补充破坏性/IP 敏感性提示

#### 结构优化
- SKILL.md 新增「下单示例安全默认」强制约束章节
- README 功能特性表顶部增加激活范围限定说明
