# Path C — Reference-led original visual rebuilding

## Scope

Use Path C when the user supplies one confirmed product master and one visual reference whose visual method should inform a new original product image. The reference supplies visual strategy only; it does not supply user-product facts, claims, copy, brand authority, or permission to reproduce its concrete implementation.

Path C always produces a pure-image result around the user's confirmed product master. It does not support a no-product output, listing copy, embedded text, Canva layout, or multi-reference mixing in V1. Do not route this work to another skill; apply the rules below directly.

Path C is a self-contained runtime. Read only this Skill's entrypoint, this Path C reference, and the shared references linked from the entrypoint. Do not read, invoke, route to, or depend on another Skill for task positioning, candidate planning, interaction language, generation decisions, QA, revision, or fallback. A missing external Skill must never change Path C behavior.

Required input:

- One confirmed product master for the current SKU.
- One readable original visual reference.
- Concrete Final Delivery Size in pixels.
- Optional user-stated core expression goal, hard exclusions, or framing boundary.

Treat every new visual reference as a new Path C task. A previously confirmed product master may be reused only when the same SKU, color, version, visible accessories, and task-relevant appearance remain clear. Do not inherit the previous reference's scene, camera, candidate route, or unfinished revision.

The roles of Candidate A and Candidate B are stable; their content is not. The comparison-table rows are a stable interaction schema, not a fixed candidate library. Re-analyze every new reference and create task-specific scene, camera, narrative, product-role, and lighting routes. Never reuse labels such as `lifestyle route`, `product hero route`, `daylight route`, or `evening route` unless the current reference and core goal independently justify them.

## Establish the reference role

Path C always includes the user's product, but the reference may play one of two roles:

- Source-product replacement reference: the reference contains a clear product subject carrying the main commercial or narrative role. Rebuild that role around the user product without retaining the source product's identity, form, brand, copy, or selling-point expression.
- Scene-led insertion reference: the reference has no primary product subject to replace. Learn its scene and visual logic, then give the user product a clear, physically credible role in a newly built implementation.

Infer the role internally. Ask only when the source product's role or the user's desired product presence is materially unclear. Do not expose mode numbers.

Whether people appear is a reference-dependent content branch, not a separate user-facing mode. When the reference contains people, extract and rebuild only their narrative function. When it contains no people, default to a no-person plan; do not invent a person merely because an earlier task used one. Add a person to a no-person reference only when the user explicitly requests it or the confirmed candidate plan makes that change visible and material.

## Extract a Visual Blueprint

Before planning candidates, separate the reference into the following layers.

### Reusable visual strategies

Extract relationships rather than an object inventory. This analysis must be converted into concrete prompt instructions, not left as a list of adjectives:

- Core narrative: what moment or experience the image communicates.
- Product / person / scene hierarchy: which subject leads, which supports, and how attention moves.
- Scene grammar: setting type, spatial openness, work or display surface, foreground / middle / background organization, and lived-in versus minimal density.
- Light grammar: natural versus artificial sources, direction, softness, contrast, time-of-day feeling, and product-to-environment light relationship.
- Color and material grammar: warm or cool balance, dominant neutrals, accent colors, material contrast, texture density, and finish quality.
- Camera and depth family: eye level or elevated, frontal or diagonal, intimate or environmental, shallow or layered depth.
- Human function when present: the person's narrative job, product relationship, emotional tone, and degree of demonstration versus lifestyle support.
- Food and prop function: whether they establish use, scale, depth, completion, or atmosphere without becoming unsupported product evidence.
- Information-area logic when present: where low-distraction visual space exists and how it remains integrated with the scene. Do not add text in V1.

At minimum, make the following visible in the blueprint whenever the reference supports them: foreground treatment and blur, the intended sharp focal subject, product-to-environment light direction, wall or surface shadow logic, furniture and prop hierarchy, functional zones, color-area location and visual weight, and the intended amount of open or lived-in space. A phrase such as `warm domestic scene` is not enough to carry these relationships into a generation brief.

Summarize the useful scene language in a short `场景视觉语言` line in the user-facing Task Positioning Card. This must name the transferable visual relationships, not merely say “warm kitchen” or list decor.

When no person is present, state the scene hierarchy without inventing a human function. When a person is present, distinguish the transferable narrative role from the source person's identity, pose, activity, location, and relationship that must be rebuilt.

### Product facts and Product Structure Map

Use only the confirmed product master and user-confirmed identity information. Record the non-negotiable visible facts:

- silhouette and overall proportions;
- component count, topology, symmetry or asymmetry;
- visible panels, drawers, handles, controls, feet, accessories, and Logo placement;
- required visible product faces and no-crop / no-occlusion areas;
- any structure the available product master does not verify.

Derive a task-specific Product Fidelity Lock from these facts and the current task:

- what must remain unchanged;
- what must remain visible;
- what may be covered;
- what must not be generated or inferred.

Record the current product state separately, including any approved drawer, lid, door, control, cleanup, or small fidelity change. Do not bury a state change inside the product evidence.

The reference product never overrides the Product Structure Map. If the reference shows an interaction that exposes unverified structure, such as an opened drawer, internal basket, rear panel, or hidden accessory, request supporting product evidence or redesign the interaction so the unverified structure stays hidden. Do not present generated hidden structure as fact.

### Source identity anchors to rebuild

Identify concrete elements that must not survive together as a recognizable template:

- source product form, brand, Logo, interface, copy, packaging, awards, or certifications;
- exact room geometry and the original relationship among cabinets, windows, shelves, furniture, and surfaces;
- exact product coordinates, camera path, crop, prop arrangement, and distinctive object combination;
- a person's facial identity, hair, wardrobe, pose, activity, position, gaze, and relationship to the product;
- distinctive cards, graphic geometry, protected characters, or unapproved text.

Preserve the useful visual strategy through a new implementation. A face swap, decor swap, or product swap inside the same concrete scene is not enough source distance.

### Layout adaptation

Record Reference Canvas and Final Delivery Size. When their ratios differ, recompose subject hierarchy, safe areas, background depth, and no-crop zones for the target canvas. Do not simply crop the reference composition.

### Core expression goal and shared constraints

Write one short core expression goal that both candidates must answer. It must describe a visual outcome, not an inferred product claim.

Set Shared Framing Constraints for both candidates:

- Final Delivery Size and target ratio;
- minimum product prominence and required visible structure;
- no-crop and no-occlusion boundaries;
- approved information-bearing area, or `不设信息区`;
- human / food / prop subordination rules;
- source-reconstruction requirements and exclusions.

## User-facing alignment before generation

After all required inputs are available, show one standalone alignment response. Do not generate in the same response.

Use the same interaction sequence for references with people and references without people. Only the task-specific content changes. Keep ordinary turns concise and use these headings when relevant:

- `🟢 已确认` or `🟢 已收到素材` for settled facts that need no action;
- `🟠 风险与建议` for a material issue;
- `🟡 需要你确认` for the one decision that changes generation or revision;
- `🟣 下一步（可选）` only for a user-controlled continuation.

Do not expose Gate, runtime, state-machine, full Generation Brief, `QA`, or other internal terminology in ordinary image-generation interaction. In visible tables, call them `方案 A` and `方案 B`; keep the English candidate labels only for internal binding and filenames.

### Asset Receipt

After the user supplies or refers to inputs, acknowledge them once in a compact form:

```text
🟢 已收到素材
**产品图：** 已确认。**视觉参考图：** 已收到。**目标像素：** 实际宽×高。
```

List only a genuinely missing required item. Do not repeat the receipt after the task is established and do not ask the user to reconfirm information already supplied.

### Task Positioning Card

Use this compact shape:

```text
🟢 任务定位
当前任务类型 · 最终像素
**目标：** 共同核心表达目标。
**保真重点：** 1–3 个最重要的产品结构或外观事实。
**场景视觉语言：** 提取出的叙事、层次、光色、材质和人物 / 商品关系。
**借鉴：** 可迁移的视觉策略。
**改写：** 必须重建的产品、人物、空间和道具身份锚点。
**共同边界：** 两张候选都不能违反的画面限制。
```

Do not replace the `场景视觉语言` line with a generic style label or a decor inventory. It must help the user understand the transferable narrative, hierarchy, depth, light, material, and product / person / scene relationship.

### Candidate Design Plan

When two valid directions exist, show this six-row table with task-specific content:

| 项目 | 方案 A | 方案 B |
| --- | --- | --- |
| 共同目标 | 当前任务的共同核心表达目标 | 相同 |
| 商品位置 / 镜头 | A 的镜头高度、方向、位置、商品占比与可见面 | B 的镜头计划及其有意义的空间差异 |
| 场景路线 | A 如何重构当前参考图的场景视觉语言 | B 如何在同一视觉语言家族中落实本次选定的替代轴 |
| A/B 区别 | 当前参考图的视觉语言重构路线 | 本次任务动态选择的一条高层替代路线 |
| 信息区 | 融入场景的信息区逻辑，或 `不设信息区` | 相同，或说明为什么需要改变组织方式 |
| 重建边界 | 必须重建的来源产品、人物、空间、道具与布局关系 | 相同边界；必要时说明 B 的不同实现方式 |

When Candidate Feasibility has downgraded the task to one candidate, show one candidate column, state the blocked alternative and its concrete reason, and do not invent a second direction.

The table is the visible plan baseline and later prompt-coverage source of truth. Wait for the user to confirm it or give one execution-oriented adjustment. Do not ask the user to choose A or B before generation. One clear confirmation authorizes simultaneous generation of both candidates. A question or exploratory comparison does not authorize generation.

The six row names stay stable so tasks are easy to compare, but every candidate cell must be derived from the current reference. Do not fill the table from a standing pair of candidate archetypes. Candidate A and Candidate B may use visibly different scenes when the named high-level axis requires coordinated changes to setting, time, functional zone, camera, depth, or narrative, provided both remain inside the same visual-language family and serve the same core goal.

After confirmation, respond compactly before execution:

```text
🟢 已确认：将同时生成方案 A 和方案 B
```

For a single-candidate downgrade, confirm only the displayed candidate and retain the stated feasibility reason.

## Candidate policy

Run Candidate Feasibility before presenting the plan. Generate two candidates by default after plan confirmation when two meaningful, faithful, and executable directions exist. If they do not, downgrade to one candidate and state the concrete reason. Do not create a weak second candidate merely to satisfy a format.

### Candidate A — visual-language reconstruction

Candidate A should preserve the reference's effective abstract strategy: scene grammar, hierarchy, light / color / material relationship, depth family, and narrative function. Rebuild the concrete room, person, product coordinates, props, and distinctive relationships so the result is not a product-swapped copy.

Candidate A is not required to mimic the original left / right layout or exact camera path. First make the extracted strategy work for the confirmed product; then create source distance through a new implementation.

### Candidate B — controlled alternative

Candidate B must answer the same core goal, use the same confirmed product facts, and remain inside the same scene-language family. Select one named high-level axis and let its coordinated consequences move together.

Valid axes include:

- camera height, direction, shot scale, or depth relationship;
- product dominance, position, or orientation;
- product-to-person or product-to-scene relationship;
- balance between product demonstration and experiential lifestyle;
- use-scene narrative;
- lighting mood or information-area organization when relevant.

Do not create B through a small prop swap, slight color change, tiny product move, face change, or crop adjustment. Do not maximize difference for its own sake or force an unrelated new scene. At thumbnail scale, A and B must remain recognizable as two different visual routes serving the same goal.

Choose the Candidate B axis from the current reference's real decision space. Scene difference is allowed but not mandatory: change scene geometry, time, functional zone, or use narrative only when those changes are the coordinated consequence of the named axis. A different room with no shared visual-language logic is unrelated concept generation, not Candidate B.

## Human and product interaction rules

When people appear:

- Preserve only their narrative function, not their identity or concrete implementation.
- Rebuild face, hair, wardrobe, pose, activity, location, gaze, camera relationship, and environment sufficiently that the result is not the same person in a modified scene.
- Keep hands anatomically credible and prevent them from covering Logo, controls, handles, or identity-level structure.
- Do not use a human action to expose or imply an unverified product mechanism.
- Keep the user product's intended commercial hierarchy. A compelling face or foreground food arrangement must not silently replace the product as the primary subject when the shared goal is product-led.

When the reference has no people and the confirmed plan does not add them:

- keep both candidates free of people, hands, partial bodies, reflections, or human silhouettes;
- express use through physically credible product placement, scene state, food, tools, or props rather than an invented actor;
- do not treat a no-person scene as an empty background: preserve its narrative, functional zones, depth, light, material, and lived-in or minimal density.

## Generation coverage and execution

Before each Candidate A or B generation call, make an internal coverage mapping from the confirmed card and table:

- core expression goal;
- Product Fidelity Lock and current product state;
- product position and framing;
- candidate scene route;
- A/B difference axis;
- information-area role;
- reconstruction boundary;
- product-fidelity priorities.

Express every approved item in the candidate-specific Generation Brief. Natural compression is allowed; silent omission or weakening is not.

Also verify that the candidate brief carries the reference's actual visual skeleton: foreground / middle / background layers, focal sharpness, furniture or prop hierarchy, product-to-environment light direction, material and color-area relationships, negative space, and any human or no-human consequence. Verify that `Preserve`, `Exclude`, and `Replacement` address the named source-distance and product-fidelity risks. If the brief only repeats subject nouns and mood adjectives, it is incomplete and must be rewritten before generation.

Run a lightweight preflight immediately before generation: the original reference, confirmed product master, confirmed plan, and Final Delivery Size must all be accessible and aligned. Never substitute an earlier AI candidate for a missing original asset.

Bind each candidate label to its completed generation result. If generation succeeded but the asset did not display, recover the existing display rather than generating a duplicate. Retry once only after an actual error, timeout, cancellation, or no-asset result.

## Review before candidate-group confirmation

Review the actual image rather than repeating the plan as if it materialized:

- core expression goal and shared constraints;
- product appearance and Product Structure Map;
- candidate-specific camera and scene route;
- whether the extracted scene visual language actually appears in narrative, hierarchy, light, color, materials, and depth;
- thumbnail-visible A/B differentiation;
- source distance in product, room geometry, people, activity, pose, wardrobe, props, camera, and relationships;
- competitor identity, source Logo, copy, certification, protected character, unsupported claim, or unapproved text removal;
- human anatomy, hand / product contact, and occlusion risk;
- scene physical logic: scale, perspective, gravity, support, contact, circulation, operating clearance, and functional-zone consistency;
- prop and food logic when present: coherent purpose, plausible quantity and portion, usable placement, non-duplicated relationships, realistic material response, and no synthetic clutter or decorative abundance that lacks a scene function;
- when the reference and core goal call for a lived-in domestic scene, require a small number of functional, zone-appropriate use cues while preserving open work surface; an empty showroom-like counter and decorative clutter are both scene-plausibility failures. Do not apply this criterion to references whose intended language is deliberately minimal, studio-like, or otherwise non-domestic;
- visual hierarchy after rendering: faces, food, props, highlights, or foreground objects must not displace the confirmed product role;
- Native Generation Size and measured Final Delivery Size.

Meaningful A/B differentiation does not make either image valid automatically. Before comparing creative value, require each candidate to pass its own product-evidence boundary, Product Structure Map, scene physical logic, source distance, exclusions, and actual-pixel checks. A beautiful image may still fail; a less attractive image may remain a valid candidate when it passes facts and physical logic.

For scene-plausibility handling:

- Minor scene deviation: disclose the exact local issue and its visual impact; keep the candidate available only when the core narrative and physical use remain credible.
- Material scene-logic failure: label the result `创意方向图｜待确认`, withdraw it from the candidate group, name the failed relationship, and offer one targeted revision. Do not present it as a valid candidate merely because the product structure is correct.
- Product-identity or unsupported-structure failure continues to follow the stricter product-deviation states below.

If replacing the user product with the source product would make the result look like an edited reference, mark a source-distance failure. A good-looking scene does not override product-structure or source-distance failure.

Classify product deviations using Product Visual Studio delivery states:

- Mild visual deviation: disclose the exact dimension of drift; the user may accept `原创视觉底图｜带已说明风险交付`.
- Key structural risk: keep as `创意方向图｜待确认` until the user explicitly accepts the named risk; after acceptance use `原创视觉底图｜带已说明风险交付` when the user wants that role. If the user explicitly promotes the image to a product master, allow that working role while retaining the risk and provenance note.
- SKU-identity error: explain that the image is not independently product-faithful. If the user still explicitly designates it as a working template, honor that designation for the stated role and label it as user-confirmed with the identity risk; do not silently present it as source-verified.

Distinguish Role Confirmation from Visible Detail Confirmation. A user designation lets the image serve as Product Master for later visual consistency, but does not mean every visible product detail was individually confirmed. If the designated image is a Path C scene image, use only the identified product region and explicitly confirmed product presentation; exclude the rebuilt room, props, people, environmental light or color cast, occlusion, and perspective distortion from the product structure record.

Do not call a file final when measured pixels do not equal Final Delivery Size. Record target, native, and final pixels plus any crop, padding, or measured non-stretch adaptation.

## Checkpoint and revision

Deliver the two reviewed results as `原创视觉底图｜待确认`. Start with `✅ **生成和检查已经完成。**` and show a compact status table before the details:

| 方案 | 结果 | 这张图实际怎么做 |
|---|---|---|
| 方案 A | 通过 / 撤回 / 待你确认 | 一句话说明实际场景、镜头和视觉重点 |
| 方案 B | 通过 / 撤回 / 待你确认 | 一句话说明实际差异和联动变化 |

Then report the one-sentence A/B difference, actual pixels, and material product, human, or source-distance risk. Use bold short labels such as `**产品外观：**`, `**像素：**`, `**场景：**`, `**风险：**`, and `**生成方式：**`.

Use this compact result pattern when both candidates pass:

```text
🟢 已生成
A：一句话说明实际生成的路线。
B：一句话说明实际生成的路线。
实际尺寸：实测宽×高。
🟠 风险与建议
只说明实际观察到的重大风险。
🔔 **请你告诉我：** 如无修改意见，回复“无修改意见”，两张合格方案都保留；如需修改，请指出一张方案和一个最优先修改点。
```

If one candidate fails, withdraw it from the candidate group. State the concrete failure and offer a single targeted revision; if the remaining candidate has no modification requested, it may be confirmed without an A / B choice.

After a user requests a revision, accept one local visual revision target at a time. A clear execution request authorizes that revision without another redundant confirmation; a question or exploratory discussion does not. A revision must not silently change product facts, Final Delivery Size, core expression goal, shared constraints, or the candidate route.

Before executing a clear revision, state the lock compactly:

```text
🟢 本次修订
只调整已确认的单一目标；保留对应候选路线与共同边界。
```

Once the user confirms no modification, or accepts a named risk for one or both eligible candidates, record each candidate's applicable Product Visual Studio asset type and delivery state, then stop. Do not force a single-candidate selection. Do not automatically enter Canva, create copy, add text, upload externally, or continue into another path.
