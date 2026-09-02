# Product Visual Studio

Product Visual Studio 是一个面向单个商品的 Codex Skill，用于制作精修白底图、指定背景融图和参考视觉原创重建图。

它会先确认产品图中的可用外观和结构，再根据任务进入 Path A、Path B 或 Path C。生成前会展示画面方案，生成后会检查产品外观、场景关系、来源距离、实际像素和主要风险。

## 三条路径

| 路径 | 适合做什么 | 需要提供 |
|---|---|---|
| **Path A｜产品精修与白底图** | 整理产品原图，制作适合电商使用的白底产品图 | 产品原图 + 最终尺寸 |
| **Path B｜指定背景融图** | 把产品放进用户指定的具体背景 | 已确认的产品白底图或产品图片 + 指定背景图 + 最终尺寸 |
| **Path C｜参考视觉原创重建** | 借鉴参考图的视觉方法，为产品重新设计原创场景图 | 已确认的产品白底图或产品图片 + 视觉参考图 + 最终尺寸 |

Path B 默认比较两种制作逻辑：**方案 A｜原场景锁定融图**与**方案 B｜场景语言创意重拍**。Path C 默认提供两个有实质差异的原创视觉方向；如果客观条件无法形成两个有效方向，则说明原因并降为单候选。

## 主要规则

- 一次只处理一个产品；
- 产品母版的工作角色由用户确认，来源、风险和未核实区域仍需保留；
- 生成结果默认处于待确认状态；
- Path B / C 生成后，用户回复“无修改意见”时保留所有合格候选，不强制二选一；
- 结果卡使用自然语言、符号和无序号表格，不向用户暴露 QA、Gate、Asset 等内部术语；
- 最终文件分别记录目标像素、原生生成像素和最终交付像素；
- 不自动生成 Listing 文案、图片文字排版、批量 SKU、详情页套图或 Canva 设计。

## 仓库结构

```text
product-visual-studio/
├── SKILL.md
├── V1_MVP_CONTRACT.md
├── agents/openai.yaml
├── references/
└── cases/
```

## 安装

```bash
git clone https://github.com/<your-account>/product-visual-studio.git ~/.codex/skills/product-visual-studio
```

重新打开或刷新 Codex 后，使用 `$product-visual-studio` 调用。

Skill 的运行规则和提示词组装方法见 `SKILL.md` 与 `references/`。PRD、历史契约和测试报告保留在本地项目资料中，不随安装包分发。
