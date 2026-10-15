# domn-film-kamen-raider

![domn-film-kamen-raider 封面](assets/readme/hero.webp)

> 假面骑士风高保真 CG 内容创作（UE5 / Warframe 视觉）。

## 是什么

假面骑士风高保真 CG 内容创作（UE5 / Warframe 视觉）。本仓库是一个 Agent 技能（SKILL.md 为唯一权威定义），把上面的方法论沉淀为可被对话触发的可执行流程。

## 怎么做（工作流）

<p align="center">
  <img src="./assets/readme/workflow.svg" width="100%" alt="domn-film-kamen-raider 工作流：读流程 → 锁画风 → 防撞车 → 索双图 → 套四拍。独创流程优先，点名才走复刻">
</p>

1. **读流程**
2. **锁画风**
3. **防撞车**
4. **索双图**
5. **套四拍**

## 怎么用

将本仓库放入支持 `SKILL.md` 的 Agent 技能目录：

- **WorkBuddy**：`~/.workbuddy/skills/domn-film-kamen-raider/`
- **Codex / 其他**：对应 skills 目录

然后在对话中触发，例如：

```
用 domn-film-kamen-raider 帮我处理一段需求。
```

## 依赖

纯提示词方法论 + references/ 弹药库；CG 依赖 UE5 / Warframe 视觉参考.

## 仓库结构

```
domn-film-kamen-raider/
├── SKILL.md                 # 技能定义（唯一权威）
├── references/              # 方法论弹药库
├── assets/                  # 模板 / 占位素材
└── assets/readme/           # 本 README 的视觉资产（hero.webp / workflow.svg）
```

## 许可

本仓库内容以 `SKILL.md` 为唯一权威定义。如附带 `LICENSE` 文件，以其为准。

---

*README 由 `beautify-github-readme` 生成 · 封面图来自作者作品集，强调色由封面图采样派生。*
