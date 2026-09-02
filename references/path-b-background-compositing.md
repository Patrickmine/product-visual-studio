# Path B — Specified-background dual-candidate workflow

## Required input

- One confirmed product master.
- One user-supplied background that defines the concrete scene.
- Concrete target pixel dimensions.
- Optional food, props, people, or exclusions requested by the user.

Label the background as the Path B scene source and the product master as the product identity source. Path B does not ask the user to choose a compositing method before candidate planning. Its default pair compares two production logics around the same product, background, output size, and business goal.

## Default candidate pair

### Candidate A｜原场景锁定融图

User-facing explanation: `直接把产品放进用户上传的这张背景。`

- Use the supplied background's existing camera, spatial structure, major visible objects, and overall arrangement.
- Choose a physically valid product position. If the existing arrangement makes the product too small, too far back, or unsupported, propose and use only the smallest disclosed local adjustment needed for credible placement and product prominence, such as moving a small tabletop prop. Do not alter the room structure or broaden the adjustment without user authorization.
- Treat removals or rearrangements of background objects (for example, removing a tablecloth) as proposed adjustments until the user explicitly requests or confirms them. Do not describe them as already authorized merely because the product itself was accepted.
- Add only the product, its contact shadow, required environmental reflections, and local light or color integration.
- If the target aspect ratio differs, disclose the crop, padding, or extension plan before generation. Cropping may change the visible range but must not be described as a new camera.
- `原场景锁定` means scene identity, camera, spatial structure, and major visible relationships remain stable. It does not by itself promise pixel-identical background preservation.
- If the user explicitly requires unchanged pixels, switch to verifiable deterministic masking, cutout, compositing, and local correction. If that method is unavailable, stop or obtain permission to relax the pixel constraint.

### Candidate B｜场景语言创意重拍

User-facing explanation: `保留参考场景的材质、色彩、光线和气质，为产品重新设计镜头与陈列。`

- Preserve the supplied scene's recognizable identity: characteristic materials, palette, light, atmosphere, and enough architectural or design anchors to remain recognizably derived from that scene.
- Allow a new camera height, direction, shot scale, product placement, depth relationship, and surrounding-object arrangement.
- Remove an object that blocks the product hero area or add product-relevant food and props when doing so improves the commercial image and stays within user authorization.
- Keep the product as the first visual subject. Food, props, people, and room styling must remain supporting elements.
- Do not reveal or invent rear, internal, side, accessory, or structural details unsupported by the product master.

Candidate B remains Path B because the same concrete scene identity must survive. Path C instead learns a transferable visual method and may rebuild the concrete scene implementation into a different original scene.

## Shared constraints and dynamic planning

Both candidates share:

- The same confirmed product master, SKU identity, color, version, target pixels, core business goal, and product-fidelity boundaries.
- The same Product Structure Map, task-specific Product Fidelity Lock, and approved current product state.
- A complete, unobstructed, physically supported product that remains the first visual subject.
- Protected silhouette, proportions, visible structure, accessories, Logo, controls, contact surface, and user-confirmed exclusions.
- No unsupported capacity, speed, health, performance, or usage claim created through styling.

Build both generation briefs with [the shared generation-prompt framework](generation-prompt-framework.md). Lock the common product facts and scene skeleton first; then write the A-specific or B-specific route. For Candidate A, state the original camera, spatial structure, support surface, major object relationships, and any narrowly approved local adjustment. For Candidate B, state the retained scene identity plus the new camera, product prominence, functional zone, and coordinated prop / food changes. Do not reduce either brief to `warm`, `modern`, or another adjective list.

The final Path B prompt must cover, in order: output task; confirmed product evidence; Product Structure Map; Product Fidelity Lock; current product state; shared scene plan; fixed A / B route; candidate-specific changes; physical placement; Preserve / Exclude / Replacement; and dimension handling.

The Candidate A / B labels and production logics are fixed; their actual camera, placement, food, props, and scene solution are dynamic. Do not hard-code a recurring front-view A or high-angle B. Select the B camera and display emphasis from visible product evidence, scene support, product-fidelity risk, product prominence, and commercial decision value.

Run Candidate Feasibility before presenting the plan. Downgrade to one candidate only when the background lacks a physically valid original-scene placement, product-view evidence cannot support a useful creative reshoot, or another hard boundary blocks one production logic. State the exact reason instead of inventing a weak candidate. Path B is the only route where Candidate A / B production meanings remain fixed even when the specific camera, placement, food, props, and scene solution are dynamic.

### Camera, placement, and evidence preflight

Before presenting or generating Candidate A, compare the supplied background camera with the proposed product position. If the combination exposes a top, side, rear, internal, or interface area that the confirmed product basis does not support, do not generate that A plan. First choose the smallest credible change that removes the conflict—such as moving the product onto a higher table, lowering the product's visible top exposure, or changing the product-facing direction. If no such change preserves the original-scene logic, explain the blocked route and either request supporting product evidence or downgrade to the feasible candidate.

After a candidate fails because of unsupported geometry or a camera/placement conflict, do not repeat the same plan with new wording. A retry requires a changed evidence basis, camera, placement, or candidate route; otherwise stop and report the conflict.

## Interaction contract

Use concise, natural Chinese user-facing language. Do not expose internal prompt engineering, `QA`, or other system jargon.

Keep the pre-generation reply to one compact interaction card: receipt, one short task-positioning paragraph, one six-row candidate table, one thumbnail-difference sentence, and the confirmation command. Do not add separate sections for execution audit, material roles, hard constraints, inferences, uncertainties, or post-generation QA when those points are already represented in the card.

If higher-priority instructions require an execution audit, merge only its decision-changing result into `🟢 任务定位` or the table's `硬边界` row. Do not repeat the same facts before and after the table. Surface a separate uncertainty only when it genuinely blocks candidate planning; otherwise make the safe assumption inside the relevant table cell. Save the detailed QA checklist for after images exist.

### 1. Receipt

Show:

```text
🟢 已收到素材

- **产品：** <已确认产品图>
- **场景：** <用户上传背景的简短识别>
- **目标像素：** <宽 × 高>
- **输出方式：** 同时生成两种画面方案
```

### 2. Task positioning

Use one short paragraph. State the common goal and product-first requirement, then mention an aspect-ratio consequence only when it changes the plan. Explain that A uses the uploaded scene directly while B creatively reshoots the product within the same scene identity. Do not restate product facts already shown in the receipt.

### 3. Candidate plan

Show a compact A / B comparison using these fields:

| 对比项 | 方案 A｜原场景融入 | 方案 B｜同场景重新组织 |
|---|---|---|
| 核心做法 | 直接把产品放进这张背景 | 保留场景气质，为产品重新组织画面 |
| 背景处理 | 原镜头、空间结构、主要物体与陈列关系 | 场景身份、材质、色彩、光线与气质 |
| 商品位置与镜头 | 根据原背景的真实落位动态决定 | 根据产品证据和展示目标动态决定 |
| 食物与道具 | 默认不重排；新增内容必须克制 | 可调整或新增，但必须辅助商品 |
| 画面价值 | 产品真实进入当前照片 | 同一场景语言下的商品广告重拍 |
| 硬边界 | 场景锁定不冒充像素锁定 | 不改变场景身份或虚构产品结构 |

If Candidate Feasibility has downgraded the task to one candidate, show only the feasible route, state the blocked route and its concrete reason, and request confirmation for the remaining route. Do not create an artificial second column.

Add one plain-language thumbnail expectation:

- `缩略图下，A 应像“产品真实放进这张照片”，B 应像“沿用这间场景的气质重新拍摄一张商品图”。`

Ask for one confirmation that authorizes the displayed plan: `确认这两种画面方案，开始生成。` When downgraded to one candidate, name that route in the confirmation request instead.

Stop there. Do not append the generation QA checklist, a second summary, or another explanation before the user confirms.

### 4. Generation and QA checkpoint

Generate each candidate independently. A valid result for one candidate does not excuse failure in the other. Apply the retry and revision limits from the main contract.

After generation, show each image with its approved candidate name and explain only the materialized differences. Start with `✅ **生成和检查已经完成。**` and use a compact status table before the details:

| 方案 | 结果 | 这张图实际怎么做 |
|---|---|---|
| 方案 A｜原场景融入 | 通过 / 撤回 / 待你确认 | 一句话说明产品落位、场景保留和实际变化 |
| 方案 B｜同场景重新组织 | 通过 / 撤回 / 待你确认 | 一句话说明镜头、陈列和场景语言变化 |

When the task was downgraded to one candidate, show only that candidate's row and include the feasibility reason in `**风险：**` or the surrounding plain-language explanation.

Then report the details with bold short labels:

Use labels such as `**产品外观：**`, `**像素：**`, `**背景：**`, `**风险：**`, and `**生成方式：**`; keep the explanation after each label in ordinary language.

- Product placement, scale, contact surface, perspective, light, shadow, and reflections.
- Candidate A scene-lock result: camera, crop, spatial structure, major objects, arrangement, and any visible generative redraw.
- Candidate B scene-identity result: retained materials, palette, light, atmosphere, anchors, changed camera, removed objects, and added food or props.
- Product proportion, structure, Logo, control-panel, color, or material drift.
- Whether the product remained the first visual subject in both candidates.
- Whether A / B remain clearly different at thumbnail size because of production logic, not simple scale or crop.
- Target, native, and final pixels plus the dimension-processing method.
- Whether any explicit pixel-preservation request was met, relaxed by the user, or remains unmet.

Use one of these result states per candidate:

- `场景融合图｜待确认`
- `场景融合图｜已确认`
- `场景融合图｜带已说明风险交付`
- `不可作为产品保真交付`

If a candidate fails a hard boundary, withdraw it from the candidate group, state the failure plainly, and offer the one allowed targeted correction. Do not silently regenerate repeatedly.

### Candidate-group confirmation

Candidate A / B are parallel comparison outputs, not mandatory mutual exclusion. If both candidates pass independent QA and the user replies `无修改意见`, keep both and record each candidate's asset type and delivery state independently. “无修改意见” is not permission to keep a hard-failing candidate. If a later downstream use needs one image, ask for A / B selection at that point; this Path B flow does not force a single-image choice in advance.

If the user separately and explicitly designates one generated image as the product master, honor that working-role decision under the shared user-confirmation rule. Record that the designation comes from the user, preserve the image's scene-generation provenance and any product-fidelity risk, and do not imply that the background or generation itself verified new product facts.

If the designated image is a Path B scene image, the Product Master working role applies only to the identified product region and any product presentation details the user explicitly confirms. Do not carry the table, background, props, people, environmental light or color cast, occlusion, or perspective distortion into the product structure or identity record.

After generation, highlight the user-feedback request with a symbol and visual emphasis: `🔔 **请你告诉我：** 如果没有修改意见，回复“无修改意见”；如果要修改，请指出方案和一个最优先修改点。` Both eligible candidates remain available when there is no modification. If there is a modification, ask for one candidate and one priority revision target. Do not automatically continue to Path C.

## Physical and product review

For both candidates, inspect the actual image rather than trusting the prompt. Review:

1. Place the product on a physically valid support surface with realistic scale and clearance.
2. Match camera perspective, horizon, contact shadow, light direction, color temperature, and environmental reflection.
3. Compare every exposed product face with the confirmed evidence; reject unsupported top, side, rear, internal, or interface geometry.
4. Remove cutout halos; reject floating products, impossible intersections, blocked controls, or support-surface penetration.
5. Keep the product silhouette, proportions, visible faces, key structure, accessories, colors, Logo, and controls faithful to the confirmed master.
6. Keep food and props plausible, restrained, and subordinate. They may not cover the product or create unsupported claims.
7. Confirm that the product remains the first visual subject at thumbnail size; check foreground / middle / background hierarchy, furniture or prop support, and whether the light actually comes from the planned direction.
8. Measure final pixels from the exported file, not from the prompt.

Do not add people, packaging, copy, badges, or extra appliances unless requested.
