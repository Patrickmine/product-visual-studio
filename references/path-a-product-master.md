# Path A — White-background product master

## Required input

- One raw product image or one user-confirmed retouched product image.
- Concrete target pixel dimensions.
- Any requested product-state change that is not already visible, such as closing an open drawer.

## Intake and decision

Inspect the product silhouette, viewpoint, visible structure, color, accessories, text and Logo, crop, occlusion, and source pixels.

Classify each requested change:

- Deterministic cleanup: background removal, edge cleanup, dust removal, conservative color correction, crop, padding, or verified resizing.
- Product-fidelity generation: rebuilding light, shadow, reflections, a small occluded area, or a user-requested state whose key structure is sufficiently evidenced.
- Creative reconstruction: inventing hidden structure, an unsupported angle, accessory, control, or other identity-bearing feature.

If the request needs creative reconstruction, either obtain supporting product evidence or state that the result is not independently verified as a product master before user confirmation.

This is a provisional evidence judgment, not a veto on the user's working decision. Distinguish `Role Confirmation` from `Visible Detail Confirmation`: a generated or watermarked-source result may become Product Master when the user explicitly says it may represent the product or serve as the product master; that statement does not mean every visible detail was individually confirmed. Record the user's confirmed-detail scope, preserve provenance and named limitations, and do not describe unverified details as independently verified by the original source. A reply such as `无修改意见` without an explicit product-master instruction is not a promotion.

## Generation brief

When generative editing is needed, build the prompt with [the shared generation-prompt framework](generation-prompt-framework.md):

1. Label the supplied image as the product source and state the target product state.
2. Fill Product Structure Map and the task-specific Product Fidelity Lock before describing the white background.
3. Preserve the SKU identity, viewpoint, overall proportions, materials, colors, visible controls, accessories, Logo, and verified text.
4. Change only the approved product state, occluded region, background, cleanup, lighting, and grounding shadow.
5. Use a pure white studio background or an explicitly approved plain-color background. Do not turn Path A into a scene composition by adding props or a lifestyle setting.
6. Keep a natural contact shadow and realistic material separation; avoid floating, over-smoothed, or CGI-like surfaces.
7. Fill `Preserve`, `Exclude`, and, where useful, `Replacement` with concrete risk controls; do not use a generic adjective list or broad bans that erase useful product detail.

For identity-critical regions with incomplete or obstructed evidence, describe the entire region in the generation brief and review the entire region after generation. A local improvement does not prove that the rest of the region is accurate. If the planned edit would expose an unsupported face or hidden structure, obtain evidence or keep that area unchanged; do not solve it by repeating the same generation plan.

Path A defaults to one result and does not run Candidate Feasibility. Mark scene, reference-method, and candidate-comparison fields `N/A` unless the user explicitly requests a specific additional version.

## Path A checkpoint

Deliver one candidate as `产品图｜待确认` or `白底交付图｜待确认`, with the original preserved. Start with `✅ **生成和检查已经完成。**` and report in plain language. Use bold short labels such as `**产品外观：**`, `**像素：**`, `**背景：**`, and `**风险：**`:

- What was intentionally changed.
- What was preserved.
- Which regions were generated rather than directly verified.
- Target, native, and final pixels.
- Any structure, Logo, text, color, or material risk.
- Whether each high-risk region was inspected as a whole, not only at one local detail.

Then ask separately for the working role and, only if needed, the visible details that should be treated as confirmed. If the user confirms that this image may serve as the product master, promote it for that role and preserve the provenance note; if the user names particular details, record those details as user-confirmed. If the user only wants a white-background delivery, keep it as that delivery image. After the result, show the next actions in an unnumbered three-column table with `下一步`, `你可以回复`, and `接下来会做什么`; do not collapse it to a two-column list. The rows must cover stopping with the white-background image, continuing to Path B by providing a background, continuing to Path C by providing a visual reference, accepting this image as the product master when the user wants that role, or requesting one targeted revision. Do not force the user to choose between Path B and Path C if they only want to finish with the white-background image.

If the user supplies the target pixels and delegates the remaining choices, treat that as authorization for the conservative plan already stated, but restate immediately before generation that the image will be used as the current working product basis. Do not treat that delegation as confirmation of every visible detail.

Use this three-column next-action table shape in the visible result card:

| 下一步 | 你可以回复 | 接下来会做什么 |
|---|---|---|
| 到这里结束 | 确认作为白底交付图 | 保留这张白底图，本轮结束 |
| 作为后续产品母版使用 | 确认作为产品母版，并接受已说明风险 | 按用户指定的工作角色记录这张图，并保留来源和风险 |
| 继续做指定背景融图 | 提供一张背景图 | 先规划两种方案，再等待确认 |
| 继续做参考视觉重建 | 提供一张视觉参考图 | 先提取视觉方法并规划两种原创方案，再等待确认 |
| 修改这张白底图 | 指出一个最优先修改点 | 只处理这一项修改，保留其他已确认内容 |
