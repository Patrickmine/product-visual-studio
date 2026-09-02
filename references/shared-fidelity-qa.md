# Shared fidelity, status, and interaction rules

This reference is the shared arbitration source for Path A, Path B, and Path C. Keep the user-facing wording natural; the English labels below are internal bindings.

## Evidence roles

- **Product source:** the original product image or a product image the user has explicitly confirmed as representing the product for the current work.
- **User-confirmed product master:** the confirmed product basis required before Path B or Path C. Record the SKU, version, color, accessories, visible structure, provenance, and any named limitation.
- **Specified background:** the Path B scene source. It supplies the scene, spatial, lighting, and placement context for the product.
- **Visual reference:** the Path C visual-method source. It supplies transferable narrative, composition, camera, light, color, material, depth, people, and prop relationships.
- **Generated result:** an output produced by the image-generation step. It starts as `待确认` and does not become a product source automatically.

Distinguish two user decisions:

- **Role Confirmation:** the user explicitly says an image may represent the product or serve as the product master. Any source image may take this working role.
- **Visible Detail Confirmation:** the user explicitly confirms particular visible appearance or structure. Role Confirmation alone does not confirm every visible detail.

Record the source, confirmed-detail scope, provenance, and named risk. A designated image may guide later visual consistency, but its unshown structure remains unverified. For a scene image, the working product role covers only the identified product region and explicitly confirmed product presentation; background, props, people, environmental light or color cast, occlusion, and perspective effects remain scene information.

## Shared review dimensions

Review the actual exported image, not the prompt or the plan as if it were the result:

1. **Input and path:** the product source, background / reference role, and selected Path are correct.
2. **Product evidence:** silhouette, proportions, visible faces, components, state, controls, accessories, Logo, color, material, and text match the confirmed evidence and Product Structure Map, with each key item retaining its source and verification scope.
3. **Product Fidelity Lock:** required visible areas remain visible; allowed occlusions are respected; unsupported structure is not exposed or invented.
4. **View compatibility:** every product face exposed by the planned camera is supported by evidence or explicit user confirmation; unsupported top, side, rear, internal, or interface structure is a hard risk.
5. **Visual plan:** the intended product role, camera, composition, foreground / middle / background, visual hierarchy, light direction, shadow logic, color areas, materials, negative space, props, and people are actually present when applicable.
6. **Physical relationship:** support surface, scale, contact point, gravity, perspective, clearance, contact shadow, reflection, and operating space are credible.
7. **Candidate distinction:** for Path B / C, the candidates differ at thumbnail scale through the named production logic and coordinated changes; Path A remains a single result unless the user asked for more.
8. **Path-specific source boundary:** Path B retains the specified scene identity; Path C transfers visual methods while rebuilding high-recognition implementation anchors.
9. **High-risk regions:** inspect each identity-critical region as a whole, including all holes, controls, interfaces, openings, handles, or other repeated details; a local fix does not clear the remaining region.
10. **Pixel handling:** target pixels, measured native generated pixels, measured final delivered pixels, and crop / padding / scaling method are recorded separately.
11. **Asset and delivery state:** asset type, candidate identity, user-confirmed role, provenance, risk, and current delivery status are all recorded.

Every identity-critical Product Structure Map entry must retain a source and verification scope. A user-confirmed visible detail may be used as a working structure record; it must not be rewritten as independently source-verified. For a scene-derived Product Master, record only the product region and exclude scene contamination.

Classify a deviation as structure, appearance, material, lighting, composition, text / Logo, scene logic, source distance, or pixels. Do not label every visual drift as a structure failure.

## Path-sensitive applicability

Coverage Pass checks only fields that matter to the current Path and candidate. Mark non-applicable fields `N/A`; do not invent furniture, people, reference-transfer rules, or candidate differences merely to fill a template.

- **Path A:** product evidence, Product Structure Map, Product Fidelity Lock, current product state, white-background plan, physical grounding, and dimensions are critical. Candidate Feasibility is `N/A` by default.
- **Path B:** confirmed product master, specified background, fixed A / B production logic, scene identity, physical placement, candidate feasibility, and dimensions are critical.
- **Path C:** confirmed product master, visual blueprint, source distance, dynamic candidate axis, physical placement, candidate feasibility, and dimensions are critical.

## Delivery statuses

Keep asset type and delivery status separate.

- `待确认`: generated and checked, awaiting the user's inspection or modification opinion.
- `已确认`: the user explicitly accepts the result for the stated image role.
- `带已说明风险交付`: the user explicitly accepts a named, bounded deviation for the stated image role.
- `撤回`: the candidate is removed from the current candidate group because it failed a hard boundary or material scene-logic requirement.
- `不可作为产品保真交付`: product identity is wrong or an unsupported structure is materially exposed. This describes the product-fidelity limit; it does not prevent the user from retaining the image for another explicitly stated visual role.

`无修改意见` means that the user has no requested visual revision. It does not by itself promote an image to a product source, accept a key structural risk, or retain a hard-failing candidate.

## Candidate-group rules

- Path A defaults to one result.
- Path B and Path C default to two candidates only after Candidate Feasibility finds two meaningful, faithful, and executable directions.
- If only one valid direction exists, retain one candidate and state the concrete reason.
- Review each candidate independently. One candidate passing does not rescue the other.
- If both eligible candidates pass and the user replies `无修改意见`, retain both; do not force an A / B choice until a downstream use needs one image.
- If a candidate fails a hard boundary, mark it `撤回` and offer at most one targeted correction.

## User-facing result card

All user-facing Chinese must use natural language. Do not expose `QA`, `Asset`, `Gate`, `Revision`, `Product Structure Map`, or similar internal labels in ordinary interaction.

After generation, use this order:

1. Start with `✅ **生成和检查已经完成。**`.
2. Show an unnumbered status table with the candidate / result / what was actually produced.
3. Use bold short labels such as `**产品外观：**`, `**像素：**`, `**场景：**`, `**风险：**`, and `**生成方式：**`.
4. State only what was observed in the exported images, including actual pixels and material risks.
5. End with a visually prominent feedback request, for example:

```text
🔔 **请你告诉我：** 如果没有修改意见，回复“无修改意见”；如果要修改，请指出方案和一个最优先修改点。
```

For Path A, follow the result with an unnumbered next-step table: finish with the white-background image, continue to Path B with a background, continue to Path C with a visual reference, or request one targeted revision.

For Path B / C, do not ask the user to choose one candidate merely to close the current generation. A user request for one targeted revision names one candidate and one priority change. A clear revision request authorizes that one revision; a question or exploratory comparison does not.

## Dimension timing

Before generation, record only the target pixels, aspect ratio, and approved crop / padding / scaling policy. After generation, measure the actual native file and final delivered file and record the actual processing method. Never report prompt dimensions as measured output dimensions or call a file final when its measured pixels do not equal the declared Final Delivery Size.

## Retry and stopping rule

If the call fails, is cancelled, times out, or returns no asset, allow one reasonable retry. If an asset exists but is not displayed, recover its display without regenerating. After the user confirms no modification, accepts a named risk, or chooses to stop, record the applicable asset type and delivery status and stop; do not automatically enter another Path or add copy, text, Logo layout, Canva work, or external upload.

A hard failure caused by unsupported geometry or a camera/placement conflict requires a changed plan before any retry; do not rerun the same plan with wording-only changes.
