# 双版本提示词模板

先把方括号内容替换成原图观察。不要把不确定的食材强行命名。每个版本都从原图独立生成。

## 共享锁定段

```text
Use case: precise-object-edit
Asset type: a polished food photo for sharing on WeChat Moments
Input image: Image 1 is the edit target, not merely a style reference.
Primary request: Re-photograph this exact real meal as a beautifully composed food image. Preserve the same food and main vessel, but do not automatically preserve the original framing, background coverage or casual snapshot composition. Follow the canvas policy for aspect ratio and dimensions.
Canvas policy: [If the user specified exact output dimensions, preserve those pixel dimensions exactly; otherwise choose the strongest aspect ratio.] Canvas dimensions do not lock the original camera angle, perspective or composition.
Food invariants: Preserve every original food type, cooking state and approximate total amount. Preserve the visual identity of [original food groups]. Do not add, replace, remove, duplicate, merge or invent food.
Vessel policy: Follow the selected version. Preserve the identity and geometry of [main vessel or takeout containers] in every version except the explicitly labeled Refined Replating Option.
Scene policy: Follow the selected version. Distinguish narrative anchors from clutter before removing objects. Do not accidentally rewrite an office, business trip, restaurant or home scene into another lifestyle.
Geometry invariants: Preserve the true shape of the table, tabletop edges, main vessels, plates, cups and containers. A square table must remain square and round plates must remain round. Correct edge stretching and accidental perspective distortion without inventing a different table or room.
Camera plan: [equivalent focal length / camera height / overhead or three-quarter angle / crop]. If the source shows close-range wide-angle distortion, simulate stepping back and using a natural 2x–3x perspective before composing.
Composition plan: [one selected structure: centered symmetry / lower-third negative space / diagonal / triangle / T-shape / S-curve / parallel lines / tight crop]. Primary hero: [food or dish]. Supporting elements: [existing dishes or objects]. Eye path: [describe].
Focus plan: Keep [hero food] on the single primary focus plane. Use [only existing foreground element, if any] as a subtle natural foreground and let supporting dishes recede with physically plausible depth. Do not blur random parts of the same plane.
Negative-space plan: Keep one intentional clean area at [location] only if it supports the composition; remove unstructured empty tabletop elsewhere.
Object policy: Remove [distracting objects], including unhelpful cups, chopsticks, crumbs and clutter, unless one object clearly strengthens the chosen composition.
Plating: Reorganize only the original ingredients inside the same vessel to look like a thoughtfully arranged dish just served by a good restaurant. Create one clear focal area, layered depth, color rhythm and readable ingredient groups. Keep believable quantities and slight natural irregularity; do not create rigid compartments.
Lighting: Use the original light direction as a base, with soft dimensional restaurant-window light, warm-neutral color, realistic shadows, natural moisture and restrained highlights.
Style: refined contemporary food photography that still feels believable for a personal WeChat Moments post; intentional and appetizing, not a casual snapshot and not a commercial menu advertisement.
Avoid: visible television or media cabinet; accidental diagonal tabletop boundary; unstructured empty tabletop; generic wide overview; close-range wide-angle stretching; changed table shape; all dishes equally sharp and equally bright; messy evenly spread food; invented foreground, bokeh or light spots; new garnish, sauce, steam, tableware or props; ingredient drift; deformed vessel; artificial studio background; plastic texture; excessive saturation, orange cast, sharpening, gloss or blur; text, logo or watermark.
```

## 外卖、办公或出差：场景保真版

检测到外卖容器和工作、酒店或旅途线索时，把共享锁定段与以下内容组合成第一张：

```text
Version: Context-Faithful Takeout Story.
Narrative intent: Preserve the feeling of eating takeout while working, traveling or staying away from home. This is a polished documentary food photograph, not a home dining scene.
Container invariants: Keep every food-filled takeout container recognizable with its original disposable material, shape, color and divisions. Do not replace takeout boxes with ceramic plates or bowls.
Scene anchors: Preserve a restrained, aesthetically controlled portion of [open laptop / hotel desk / work equipment / luggage / travel setting] so the viewer understands the situation. Remove private or readable screen content, logos and distracting detail. Do not remove every work or travel cue.
Cleanup: Remove empty packaging, duplicate lids, plastic bags, disposable cutlery wrappers, crumbs, stains and objects that add no story. Move and straighten the remaining containers into a compact, abundant arrangement.
Composition: Make the food occupy about 65–80% of the useful frame. Use one container as the foreground hero and arrange the other food-filled containers in a clear supporting triangle. The work or travel cue must remain secondary and quieter.
Lighting: Expose for the food with bright soft window-like light. The meal is the brightest, warmest and sharpest meaningful area; the working environment is slightly cooler and softer but still believable.
Final impression: “I am busy and tired, eating takeout while still working, but I know how to notice and photograph my life.”
```

## 外卖、办公或出差：精致重摆版

把共享锁定段与以下内容组合成第二张：

```text
Version: Refined Replating Option.
Interpretation: This is an explicit alternative presentation, not a scene-faithful record.
Food invariants: Transfer the exact same foods, cooking states and believable quantities from the takeout containers into simple attractive household ceramic plates or bowls. Do not upgrade ingredients, add side dishes, garnish, duplicate food or alter recipes.
Vessel exception: Replacing disposable takeout containers is allowed only in this version. Use modest, coherent household tableware rather than luxury restaurant ware.
Scene: Remove takeout packaging and most work clutter. Use a clean, believable home-style tabletop presentation without turning it into a commercial studio or fine-dining advertisement.
Composition: Build a strong hero-and-support hierarchy, keep the spread generous and orderly, and make every original food category readable.
Lighting: Bright, warm-neutral natural light with realistic shadows and restrained highlights.
Final impression: the same real takeaway meal, deliberately replated for a prettier pure-food Moments post.
```

## 完整菜品构图

把共享锁定段与以下内容组合成一次独立编辑：

```text
Version: Complete dish hero composition.
Composition: Follow the canvas policy and the selected composition plan rather than copying the source camera position. Use [selected camera height and angle] because it suits [dish count, vessel geometry and food height]. Keep [hero dish or hero ingredient] on the primary focus plane and let [supporting dishes or existing objects] form the selected eye path. Show only clean original tabletop or meaningful scene context around it; crop unrelated room detail completely out of the image.
Cropping: It is acceptable to crop [specific vessel edge, handle or peripheral supporting dish] intentionally if the cut is clean and improves the selected composition. Avoid awkward edge tangencies or nearly-complete objects clipped by a few pixels.
Plating: Arrange [original hero food group] as the clear focal cluster and use [other original food groups] to create readable supporting rhythm, front-back layering and color contrast. Preserve every original food type and approximate total quantity. Make it look freshly and carefully served, not mixed into a chaotic pile or divided into rigid artificial sections.
Final impression: a sophisticated complete-dish photo someone with excellent taste would confidently post to WeChat Moments.
```

## 第二视角：默认局部质感特写

把共享锁定段与以下内容组合成另一次独立编辑：

```text
Version: Tactile food detail close-up.
Composition: Choose a bold close crop and a clearly different viewpoint from the complete dish version. Fill the frame with [the most appetizing original food combination]. Show only a purposeful arc or edge of [the original main vessel]; the whole vessel does not need to be visible. Exclude unrelated room detail and unstructured empty tabletop entirely.
Focus: Establish one sharp focal plane across [hero food detail] with a gentle, physically plausible falloff. Emphasize the original browned edges, cut surfaces, sauce, moisture, crispness or layered texture that is actually visible without inventing qualities the food does not have.
Plating: Arrange the original ingredients with restaurant-level intention and enough separation to read each component. Keep the frame abundant but not cluttered; do not scatter ingredients evenly or form rigid sections.
Final impression: an intimate, appetizing detail photograph that feels carefully shot at the table and works as a standalone WeChat Moments image.
```

如果原图已有适合的餐具或审美统一的环境，可根据 [style-profile.md](style-profile.md) 把第二版替换为餐具互动或环境叙事镜头。不得从参考调性中复制饮品、绿色勺柄、陶瓷盘、蛋黄、葱花、芝麻、文字或水印。

每次先根据 [composition-system.md](composition-system.md) 完成镜头决策卡，再填写共享锁定段中的 Camera plan、Composition plan、Focus plan 和 Negative-space plan。不得把这些字段留成笼统的“更好看”“更高级”或“优化构图”。

外卖、办公和出差场景不要使用普通的“完整菜品 + 局部特写”默认组合；优先使用上面的`场景保真版 + 精致重摆版`。只有用户明确要求纯食物视角时才改用其他组合。

## 定向返工句

构图或摆盘不成立时从原图重做，并只附加最相关的修正：

- `Remove the entire television, cabinet and tabletop boundary from the frame; use only a tight clean-tabletop food composition.`
- `Replace the generic wide overview with a decisive close crop; the dish must dominate the frame and there must be no large empty tabletop.`
- `Straighten or entirely exclude every table edge and background line; do not allow an accidental diagonal boundary behind the dish.`
- `Restore the real table and vessel geometry. Simulate stepping back and using a natural 2x–3x perspective; do not turn a square table into a round table or stretch edge plates into ovals.`
- `Choose one clear hero dish and one primary focus plane. Let the other existing dishes support it with physically plausible foreground and background falloff instead of keeping the entire table equally sharp.`
- `Recompose this multi-dish scene with one intentional S-curve, triangle, diagonal or parallel-line structure. Do not average every plate across the frame.`
- `Keep the requested output pixel dimensions exactly, but redesign the camera angle, perspective and internal composition within that canvas.`
- `Rebuild the plating around one clear hero cluster; separate the original ingredient groups and eliminate the chaotic evenly spread pile.`
- `Use a bolder intentional crop of the pan and handles; avoid almost-complete objects awkwardly clipped at the frame edge.`
- `Restore the exact original ingredient inventory and cooking state; remove anything that was not present in Image 1.`
- `Reduce the restaurant-advertising polish while preserving the strong composition and organized plating; make it believable as a personal post.`
