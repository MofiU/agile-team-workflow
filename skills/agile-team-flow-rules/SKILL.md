---
name: agile-team:flow-rules
description: 敏捷流程规则 - 代码审查、DoD定义、Quorum规则、Turn估算。当需要了解代码审查要求、质量门控、团队Quorum规则时使用。
---

# Flow Rules (AI Teams)

## 代码审查策略

### 审查要求矩阵

| 代码类型 | 审查要求 | 原因 |
|---------|---------|------|
| **关键路径** (安全/支付/认证) | 100% peer review | AI可能在高风险逻辑产生缺陷 |
| **常规功能** | 自动化门控通过 + 可选异步review | 核心逻辑已被测试覆盖 |
| **Bug修复** | 自动化门控通过 + 可选 | 测试证明修复有效 |
| **文档/配置** | 无需review | 无执行风险 |

### 关键路径定义

- 认证和授权逻辑
- 支付和金融计算
- 数据隐私和合规代码
- 基础设施和安全配置

### 谁来审查？

- 开发者互相review代码
- 关键路径需要2+ reviewers
- Reviewer必须与作者不同

### 审查流程

1. 提交PR并描述
2. 自动化门控必须通过(ESLint, tests, SAST, CVE)
3. 如果是关键路径 → 等待peer review approval
4. 如果是常规 → 自动化门控通过即可merge

---

## Definition of Done (DoD)

### 自动化门控 (100%强制)

| 门控 | 要求 |
|------|------|
| ESLint/Prettier | 0 errors |
| TypeScript | strict mode, 0 errors |
| 单元测试 | 核心业务逻辑覆盖 |
| SAST | 0 vulnerabilities |
| CVE | 0 known vulnerabilities |

### 手动门控

- 关键路径代码：peer review approval
- 常规代码：自动化门控足够

### NOT in DoD

- 覆盖率数字游戏
- 测试setter/getter
- 测试配置文件

---

## Quorum规则

### 仪式参与矩阵

| 仪式 | Quorum | 必须参加 |
|------|--------|---------|
| Sprint Planning | **2/3 + All Devs** | SM, PO, All Devs |
| Daily Standup | 无 | 工作的开发者 |
| Sprint Review | **2/3 + Stakeholders** | SM, PO, Devs |
| Retrospective | **2/3 (incl PO)** | SM, Team |

### Quorum规则

```
✅ Quorum满足：仪式可以继续，决策有效
❌ Quorum不满足：延迟或异步替代
⚠️ 所有开发者必须参加Planning（无例外）
```

---

## Turn估算规则

### Team Self-Assessment

```
PO: "优先级是 A, B, C, D, E"

SM: "团队，我们有35 turns。能commit多少？"

Team: "A需要15 turns, B需要12, C需要8。加起来35。"

SM: "C还是D？"

Team: "C。D太模糊了。"

PO: "好，C优先。拆成小块。"

SM: "Commit: A, B, C。Sprint Goal锁定。"
```

### Key Principle

**Team commits to turns, not PO allocates turns.**

---

## Phase参与规则

### Discovery Phase
**参与**: SM, PO, UI/UX, Architect
**排除**: Developers, QA (直到设计就绪)

### Planning Phase
**必须**: SM (facilitates), PO (priorities), **All Developers** (commit!)
**排除**: QA, UI/UX (除非关键设计决策)

### Development Phase
**参与**: SM, Assigned Developers, DevOps (when needed)
**拉入**: UI/UX **仅当developer提出问题时**

### Testing Phase
**参与**: Developers (bug fixes), QA (owns testing)

### Sprint Review
**必须**: Full Scrum Team + Stakeholders
**角色**: Developers demo their own work

### Sprint Retrospective
**必须**: Full Scrum Team (SM, PO, All Developers)
**PO参与**: Required - PO是团队一部分

---

## Pull-In Pattern

### Developer提出UI问题
```
Developer: "UI与spec不符"
SM: 安排Developer和UI/UX同步
```

### Technical Blocker
```
Developer: "数据库迁移被阻塞"
SM: 拉入Architect或DBA咨询
SM: 在blocker log记录解决方案
```

---

## Emergency规则

### Turn Borrowing
```
SM: "发现关键bug。需要5个额外turns。"

Team: "共识是从下个sprint借5个？"

Team: *consensus* "同意。"

SM: "借5 turns。通知PO。记录。"
```

### Emergency Reprioritization
```
PO: "紧急：影响50%用户的关键bug。"

SM: "团队，PO宣布紧急。能消化5 turns的热修复吗？"

Team: "能，可以去掉D消化热修复。" 或 "不能，会错过Sprint Goal。"
```
