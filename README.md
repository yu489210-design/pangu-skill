# 盘古 Skill

`v0.2-candidate`

盘古 Skill 是一个 instruction-only Codex/Agent Skill。它的目标不是让用户制作 Skill 文档，而是在用户说出想制作的对象、作品、产品、内容、工具、学习资料或项目实例后，生成用户真正想要的具体实例。

当前版本保留纯文本说明，不包含脚本、自动化程序或复杂依赖。

## 核心机制

盘古 Skill 的特色是三层结构：

1. 高质量范式实例生产层

   先由与目标对象高度匹配的领域造物专家，通过关键节点式交互，生产一个高质量普遍实例，并留下关键节点轨迹。

2. 炼法成 Skill 层

   把第一层的关键节点轨迹抽象成节点方法和方法链，形成一个针对当前对象类别的临时专用 Skill。

3. 用户实例生成层

   调用临时专用 Skill，根据用户需求生成个性化实例。需求过少时使用范式默认和最小追问；需求过多或冲突时进行需求分层、冲突检测和主线收束。

## v0.2 核心变化

v0.2 在 v0.1 三层结构基础上增加“专家证据链与高风险节点验证”，不新增第四层。

- 领域造物专家不能只声明身份，必须建立当前项目的专家证据链。
- 高风险节点必须先做最小原型、样张、局部验证或场景验证，通过后才能进入批量生产。
- 未验证内容必须标注交付级别，不能伪装成完整交付。
- 证据链摘要必须区分已核验依据和待核验 / 应核验依据。
- 低风险任务仍可直接生成用户实例，不会被过度验证化。

## 临时 Skill 原则

临时 Skill 是内部中间产物，不是默认交付物。

- 不默认展示给用户。
- 不默认永久保存。
- 不默认写入盘古 Skill 本体。
- 只有经过验证且用户确认后，才可能升级为正式专用 Skill。

默认输出应聚焦用户真正想要的具体实例，而不是三层过程解释、节点轨迹或临时 Skill 文档。

## 当前状态

盘古 Skill 当前为 `v0.2-candidate`：

- v0.1 已通过 10 个核心人工测试，覆盖触发范围、需求调节、实例输出和临时 Skill 处理。
- v0.2 已通过 10 个专家证据链与高风险节点验证人工测试，覆盖最小验证闭环、交付级别、禁止跳过验证、升级限制和低风险任务不过度验证化。
- 当前仍为 instruction-only Skill，未使用脚本化测试。

## 仓库结构

```text
.
├─ AGENTS.md
├─ README.md
└─ pangu-skill/
   ├─ SKILL.md
   └─ references/
      ├─ architecture.md
      ├─ v0.2-plan.md
      ├─ test-cases.md
      ├─ test-results-v0.1.md
      └─ test-results-v0.2.md
```

当前没有 `scripts/`、`assets/`、`examples/`、`tests/` 或 `agents/openai.yaml`。

## 核心文件

- `AGENTS.md`：约束本仓库后续工作的项目级规则。
- `README.md`：GitHub 仓库首页与当前版本说明。
- `pangu-skill/SKILL.md`：盘古 Skill v0.2 candidate 的 instruction-only 主体。
- `pangu-skill/references/architecture.md`：三层机制与临时 Skill 处理规则的架构冻结文档。
- `pangu-skill/references/v0.2-plan.md`：专家证据链与高风险节点验证的 v0.2 规划。
- `pangu-skill/references/test-cases.md`：v0.1 与 v0.2 人工测试样例。
- `pangu-skill/references/test-results-v0.1.md`：v0.1 人工测试结果记录。
- `pangu-skill/references/test-results-v0.2.md`：v0.2 人工测试结果记录。

## 版本标签

当前版本标签：`v0.2-candidate`
