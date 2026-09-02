# Shared generation-prompt framework

This framework is internal execution guidance. Keep ordinary user-facing Chinese natural and concise; do not expose these field names as if the user needs to understand them. The model-facing generation brief must preserve the structure below rather than collapsing into a list of style adjectives.

## Execution order

Use this order for every image-generation task:

```text
Evidence Pack
→ Product Fidelity Lock
→ 当前任务产品状态
→ Visual Plan
→ 生成前可行性检查
→ Path Adapter
→ Candidate Feasibility
→ Generation Brief
→ Coverage Pass
→ 生图
→ 结果检查
```

`Product Fidelity Lock` is the bridge between evidence and planning. `Candidate Feasibility` applies only to Path B and Path C; Path A defaults to one result.

## Product View Feasibility Check（产品视角可行性检查）

在写最终生图提示词前，先检查计划中的镜头和产品落位是否被现有产品依据支持：

- 计划镜头会露出产品的哪些面（正面、顶部、侧面、背面或内部）；
- 每个将被露出的关键面是否有可靠的图片依据或用户确认；
- 产品放置的位置是否会因为视角、比例或支撑面而暴露未验证结构；
- 产品是否足够大、足够清楚，并保持第一视觉主体；
- 支撑面、接触点、重力、透视和操作空间是否同时成立。

如果镜头会暴露未验证的关键结构，不能直接生成，也不能只靠再次重复同一方案解决。应先调整产品落位或镜头、改走可保真的候选方向，或向用户索取对应角度的产品依据；只有冲突消除或风险被明确接受后才能继续。

## Layer 1 — Evidence Pack

Record only what the product evidence or explicit user confirmation supports:

- product source and its authority: original product image or user-confirmed product master;
- working role confirmation: whether the user explicitly designated this image as the product itself / Product Master;
- visible-detail confirmation scope: which visible appearance or structure the user explicitly confirmed, if any;
- SKU, version, color, accessories, Logo, controls, and other user-confirmed identity facts;
- current-view silhouette, visible faces, proportions, component count, and topology;
- identity-critical areas that must remain visible;
- areas that may be covered in this task;
- unverified structure that must remain hidden or unchanged;
- provenance and named limitations when the user explicitly designates an image as the product itself;
- for a scene image used as Product Master, the product-region boundary and scene information excluded from product identity.

The Path B background and the Path C visual reference are scene / visual-method sources. They do not add product facts to the Evidence Pack.

When a generated, watermarked, or scene image is user-designated as Product Master, the designation changes its working role but not its provenance. Record each important structure with its source and verification scope. A visible detail can be used for visual consistency without being described as independently verified by an original product source.

## Bridge — Product Fidelity Lock

Derive this block from the Evidence Pack and the current task:

```text
【本次必须保持】
-

【本次必须可见】
-

【本次允许遮挡】
-

【本次不得生成或推断】
-
```

Do not treat this lock as new product evidence. It is the task-specific selection of what the generation must protect.

Product Structure Map entries must retain provenance and verification scope. After Role Confirmation, user-confirmed visible details may update the current working structure record, marked as user-confirmed rather than independently source-verified. Hidden or unshown structure remains unverified. For a scene-derived Product Master, map only the identified product region; do not import props, background, environmental color cast, occlusion, or perspective distortion into the product structure.

## Current task product state

Record the one approved state or change for this generation:

```text
【当前任务产品状态】
- drawer / lid / door / control state:
- cleanup or refinement requested:
- small fidelity adjustment allowed:
- other explicit state change:
```

An unapproved state change must not be hidden inside the product facts or scene plan.

## Layer 2 — Visual Plan

### Expression and hierarchy

- core expression goal or visual experience, without inventing a product claim;
- desired narrative moment or use context;
- product role: Hero Product, product-in-scene, or product + human interaction;
- first-visual-subject rule and product prominence.

### Camera, composition, and space

- camera height, direction, distance, shot scale, viewpoint, and visible product faces;
- product size, placement, orientation, safe area, and no-crop / no-occlusion boundaries;
- foreground, middle ground, and background structure;
- visual hierarchy and focal path;
- information area or intentional negative space, when relevant.

### Light, color, material, props, and people

- light sources, direction, softness, contrast, contact shadow, and product-to-environment light relationship;
- dominant and accent color areas, materials, texture density, and finish;
- furniture, food, props, and human function, with each element's supporting role;
- lived-in or minimal density appropriate to the current reference and goal.

### Physical placement

- support surface, scale, clearance, gravity, and contact point;
- perspective, horizon, depth, and camera relationship;
- reflected light, color spill, and material response;
- operating clearance and visibility of controls, handles, doors, or interfaces.

## Path Adapter

### Path A — product refinement and white-background image

- input: product original image and target size;
- default: one result, no Candidate Feasibility check;
- visual plan: complete silhouette, suitable product scale, white or approved plain-color background, clean edges, material, grounding shadow, and natural light;
- scene fields such as furniture, people, foreground / middle / background, and reference-method transfer are `N/A` unless the user explicitly requests them.

### Path B — specified-background compositing

- input: confirmed product master, specified background, and target size;
- Candidate A is fixed as `原场景锁定融图`;
- Candidate B is fixed as `场景语言创意重拍`;
- A preserves scene identity, camera, major spatial structure, and primary relationships; this does not promise pixel-identical background preservation;
- B preserves scene identity, materials, palette, light, and atmosphere, then changes camera, product prominence, functional zone, or surrounding relationships;
- both candidates share the same product evidence, fidelity lock, goal, and target size;
- any local adjustment for credible placement must be minimal and disclosed.

### Path C — reference-led original visual rebuilding

- input: confirmed product master, visual reference, and target size;
- extract the reference's visual method: narrative, hierarchy, camera, composition, spatial layers, light, color, material, people, and prop function;
- rebuild high-recognition implementation anchors such as source product, Logo, text, person identity, concrete room geometry, product coordinates, and distinctive object combinations;
- use new scene relationships and the confirmed product's evidence to implement the visual method;
- default to two meaningful visual directions after plan confirmation, with a single-candidate fallback when two valid directions do not exist.

## Candidate Feasibility

Apply only to Path B and Path C before presenting the generation plan:

```text
是否存在两个真正有意义、保真且可执行的方向？
→ 是：Candidate A / Candidate B
→ 否：单候选，并说明具体原因
```

For Path B, the first-level difference is always the fixed A / B production logic above. Select any further visual axis only inside the relevant route, and make its camera, product placement, spatial, prop, or human consequences move together.

For Path C, select one task-specific high-level axis such as camera / depth, product dominance, product-to-person relationship, demonstration versus lifestyle, use narrative, lighting mood, or information-area organization.

A small prop swap, tiny color change, crop, or scale change is not a meaningful candidate difference.

## Layer 3 — Model-facing Generation Brief

Assemble the final prompt in this order:

```text
1. 输出任务
2. 产品证据
3. Product Structure Map
4. Product Fidelity Lock
5. 当前任务产品状态
6. 画面规划
7. Path 专属规则
8. 候选差异
9. 产品物理落位
10. Preserve
11. Exclude
12. Replacement
13. 尺寸与交付处理
```

### Preserve / Exclude / Replacement

Pair a real risk with a positive preservation instruction whenever useful:

```text
【Preserve】
- 必须保留的产品、场景和视觉关系

【Exclude】
- 与当前风险直接对应的具体避免项

【Replacement】
- 被排除内容如何替代，或如何重新组织
```

Use precise, narrow exclusions. Do not ban useful categories such as food, furniture, or lifestyle props unless the user explicitly requires it. User-facing interaction may describe the outcome positively; exclusions remain internal model-facing controls.

For any identity-critical region with incomplete evidence (for example a perforated panel, control area, top opening, connector, handle, or interface), name the whole region in the brief and inspect the whole region after generation. Do not treat one corrected detail as proof that the rest of the region is faithful.

## Coverage Pass

Before each generation call, map the confirmed plan to the candidate brief. Check only fields applicable to the current Path and candidate; mark other fields `N/A`.

| 检查项 | 必须能回答的问题 |
|---|---|
| 产品证据 | 产品依据、确认信息和来源是否明确？ |
| 结构边界 | 哪些部位必须保持、必须可见、可以遮挡或不能推断？ |
| 产品状态 | 本次允许呈现的状态是否已经传入？ |
| 共同骨架 | 叙事、层次、焦点、镜头、光线、色彩和材质关系是什么？ |
| 候选差异 | A / B 的高层差异及至少两个联动变化是什么？Path A 是否正确保持单结果？ |
| 物理落位 | 产品放在哪里，为什么站得住、拍得对？ |
| 视角与依据 | 当前镜头会露出哪些产品面？每个关键面是否有依据？ |
| 主体性 | 产品在缩略图下是否足够大、清楚并保持第一视觉主体？ |
| 道具与人物 | 每个元素承担什么功能，如何保持产品第一主体？ |
| Preserve / Exclude / Replacement | 关键风险和有用元素是否都有对应处理？ |
| Source Distance | Path C 的可迁移方法和必须重建的身份锚点是否都传入？ |
| 尺寸 | 目标、原生和最终交付尺寸分别如何处理？ |
| 适用性 | 当前 Path 不适用的字段是否标记为 `N/A`，没有被虚构？ |
```

If a decision-changing answer is missing, resolve or disclose it before generation. Do not rely on the model to improvise a missing product fact, state change, physical relationship, or candidate difference.

## Dimension and delivery handling

Before generation, write only the target pixels, aspect ratio, and approved crop / padding / scaling policy. After generation, measure and record the actual native file and final delivered file, plus the actual processing method. Never report prompt dimensions as measured output dimensions.
