# 画风锁定与角色设计提示词

> 本文件负责两件事：**把画风锁死在 UE5 实时渲染 / Warframe 高保真科幻装甲**，以及**写出高质量的骑士角色设计生图提示词**。

---

## 1. 画风锁定（强制，每次生成都要带）

### 锁定块（直接复制，放在提示词最前面）

```
  画风锁定：UE5（Unreal Engine 5）实时渲染引擎的电影级画质。写实 PBR 材质与 Nanite 超高模
  几何细节、Lumen 全局光照与体积雾、电影级三点布光与浅景深；**假面骑士设计锚点 × Warframe
  机甲** 的融合风格——以假面骑士的身份骨架（醒目变身腰带 / 非人复眼头盔 / 头胸可读的命名
  母题 / 深色分件底衣 + 局部硬甲片叠层）为本体，外覆 Warframe 式华丽弹道装甲：装甲材质
  统一为 **metal / ceramic ballistic plating（金属 / 陶瓷弹道装甲板，效果最稳最高级）**，金 /
  水晶 / 彩色镶嵌只作小范围装饰（铆钉、纹章、描边），绝不作为甲片主体；ornate ballistic
  plating（带棱角、厚度、接缝、铆钉的分件硬甲）、贯穿甲片的 glowing energy channels（发光
  能量通道）、Tennogen 式 ornamental seams（装饰雕花接缝）、Void-light emissive trim（虚空光
  自发光描边）；**高覆盖率**——胸 / 肩 / 臂 / 腰 / 大腿 / 小腿均被甲片包裹，深色分件底衣仅在
  活动关节（颈、肘、膝、腰折）露出；**纯织物服饰配件** flowing fabric clothing accessories
  （围巾 / 披风 / 衣领 / 裙摆 / 臂袖，呼应骑士围巾传统——**必须是 fabric / cloth 布料材质，
  禁止写成 light armor / 轻甲**，非发光能量旗、非尾巴）；**配色 60/30/10**——dominant 中性
  色（明度冷暖错开）+ secondary 识别色（**低饱和、沉色**，如 deep jade / oxidized crimson）+
  accent 金属色与自发光；**彩度发光化**——饱和度放在 visor 与 energy channels 的发光上，
  不放进大面积甲片材质（大面积高饱和 = 塑料感）；**禁止完全对称**，至少一处结构级不对称；
  high-fidelity subsurface-scattering 材质、能量护目（glowing visor）、rim light
  边缘光、浅景深、轻微胶片颗粒。禁止卡通描边、赛璐璐上色、二次元渲染、橡皮套特摄塑料感、
  低多边形与粗糙贴图。整体观感等同 Warframe 宣传 CG 与 UE5 技术演示。
```

### 必写关键词

```
UE5 real-time render, Nanite high-poly detail, Lumen global illumination, volumetric fog,
physically-based materials, subsurface scattering, Kamen Rider identity (henshin belt,
non-human compound-eye visor) over Warframe-style ornate ballistic plating, glowing energy
channels, Tennogen ornamental seams, Void-light emissive trim, flowing fabric clothing
accessories, neutral-dominant color scheme with a single desaturated signature accent color,
glowing visor and energy channels carrying the saturated color, asymmetric armor design,
dynamic hero pose, cinematic three-point lighting, rim light, film grain, shallow depth of field
```

### 必禁关键词（负面词里必带）

```
anime, cel-shading, cartoon, illustration, painting, comic outline, rubber suit, tokusatsu
practical suit, low-poly, low detail, flat shading, plastic toy, chibi, stylized drawing
```

> **最常见的失败就是忘带锁定块**——模型默认往插画/二次元/低模跑。锁定块必须放在提示词**最前面**。

---

## 2. 角色设计提示词写法

### 2.1 配色 60 / 30 / 10（不是"全中性"，是"彩度归位"）

> ⚠️ 常见误判：为了"高级"把全身上成中性色 → 五个骑士撞成一身、丢失辨识度。**真正廉价的是"大面积高饱和"，不是"有颜色"。**

| 层 | 占比 | 内容 | 写法 |
|---|---|---|---|
| **dominant** | ~60% | 有明度指向的**中性色**（陶瓷白 / 骨白 / 石板灰 / 哑光黑 / 石墨黑 / 铁灰）。**每个骑士必须错开明度与冷暖** | `bone-white ceramic plates`、`matte charcoal plates`、`graphite iron-grey plates` |
| **secondary** | ~30% | **该角色的识别色**，但必须**沉下去**：降饱和、加深、改哑光 | ✅ `deep jade-green`、`oxidized crimson`、`deep teal`、`patina verdigris` ❌ `emerald green`、`bright red`、`vivid teal` |
| **accent** | ~10% | 金属色（金 / 银 / 青铜 / 香槟金）+ **自发光**（visor / energy channels） | `antique gold trim`、`glowing jade-green visor and energy channels` |

**三条铁律：**

1. **彩度发光化**——饱和度交给**发光**，不要交给**材质**。大面积曲面上铺高饱和色 + 高光 = 注塑塑料感；放到 visor 与 energy channels 上，观感是"光"不是"塑料"，识别色照样一眼可辨。判据：材质写低彩度（`deep / oxidized / matte [色]`），发光写高彩度（`glowing [色]`）。
2. **一色原则**——最多 **1 识别色 + 1 金属色 + 1 发光色**；第 4 个颜色砍掉。
3. **底衣不局限于黑**——底衣（undersuit）可以是**白 / 骨白 / 炭黑 / 深灰**，跟随 dominant 走。浅色骑士用 `off-white segmented undersuit`，暗色骑士用 `matte charcoal segmented undersuit`；**关键是底衣与甲片要有明度差**，让缝隙里的底衣勾出分件轮廓。

**左右分区怎么写（不违反一色原则）**：分区的一侧是**识别色**，另一侧是**中性色的明度变体**（更暗或更亮），**不是两种彩度打架**——
`left side deep teal plates, right side matte charcoal plates`（✅ 一彩一中性）
`left half crimson, right half cobalt-blue`（❌ 两个高彩度对撞，显廉价）

### 2.2 装甲与材质

| 部位 | 常用写法 |
|---|---|
| 底衣 | `matte black undersuit`、`segmented undersuit with visible seam lines` |
| 胸甲 | `central chest core with [MOTIF] emblem`、`raised collar guards` |
| 肩甲 | `asymmetric shoulder pauldrons, one spiked one smooth` |
| 手套 / 靴 | `reinforced greaves`、`articulated finger gloves` |
| 分件感 | `segmented plate armor with visible seam lines and mechanical rivets` |
| 质感 | `metallic silver plating`、`glossy enamel finish`、`worn practical prop texture` |

### 2.3 头部与标志元素

- 单眼：`single horizontal visor slit`
- 复眼：`twin compound eyes`
- 拟态：`insectoid crest` / `bat-wing crest` / `rabbit-ear crest` / `horned crest`
- 招牌件：`flowing scarf`、`antenna feeler`、`spiked crown`

### 2.4 完整范例（原创骑士 · 按 §2.6 顺序排布）

```
画风锁定：UE5（Unreal Engine 5）实时渲染引擎的电影级画质。写实 PBR 材质与 Nanite 超高模
几何细节、Lumen 全局光照与体积雾、电影级三点布光与浅景深；**假面骑士设计锚点 × Warframe
机甲**的融合风格——以假面骑士身份骨架（醒目变身腰带 / 非人复眼头盔 / 命名母题 / 深色分件
底衣 + 局部硬甲片叠层）为本体，外覆 Warframe 式华丽弹道装甲：装甲材质统一为 metal / ceramic
ballistic plating（金属 / 陶瓷弹道装甲板），金 / 水晶 / 彩色镶嵌只作小范围装饰（铆钉、纹章、
描边），绝不作为甲片主体；ornate ballistic plating、glowing energy channels、Tennogen
ornamental seams、Void-light emissive trim；高覆盖率——胸 / 肩 / 臂 / 腰 / 大腿 / 小腿均被甲片
包裹，底衣仅在活动关节露出；纯织物服饰配件（围巾 / 披风 / 衣领 / 裙摆 / 臂袖，**必须是
fabric / cloth 布料材质，禁止 light armor / 轻甲**，非发光能量旗、非尾巴）；**配色 60/30/10**
——dominant 中性色（明度冷暖错开）+ secondary 识别色（**低饱和、沉色**）+ accent 金属与自发
光；**彩度发光化**：饱和度放在 visor 与 energy channels 的发光上，不放进大面积甲片材质（大面
积高饱和 = 塑料感）；**禁止完全对称**，至少一处结构级不对称；金属 / 陶瓷 subsurface-scattering
材质、rim light 边缘光、轻微胶片颗粒。禁止卡通描边、赛璐璐上色、二次元渲染、橡皮套特摄
塑料感、低多边形与粗糙贴图。

front-facing full-body character shot, standing upright, arms at sides, pure white seamless
studio background, product-shot framing, no environment, no props. Kamen Rider (仮面ライダー),
NOT a generic Warframe / Destiny mech suit. lean athletic humanoid male build, broad shoulders,
defined musculature beneath the suit, ~185cm commanding stance. Color scheme 60/30/10 — dominant
60% matte charcoal-grey ceramic plating, secondary 30% oxidized crimson (deep, desaturated, NOT
bright red), accent 10% antique gold trim; saturated color carried by emissive only. off-white
segmented undersuit with visible seam lines, overlaid with metal / ceramic ballistic plates in
deep oxidized crimson covering chest, shoulders, arms, hips, thighs and shins; light undersuit
exposed only at flexible joints (neck, elbows, knees, waist) to outline the plate seams.
asymmetric design: enlarged right shoulder pauldron with a mantis-blade crest, smaller plain left
shoulder guard, off-center chest core, single-side helmet crest. mantis motif readable on the
helmet crest and chest core. prominent driver belt buckle at waist — large, centered, mechanical
engraved dial with a rotating mantis-hook lever. Warframe-style ornate ballistic plating, glowing
crimson energy channels, Tennogen ornamental seams, Void-light emissive trim. flowing woven cloth
scarf at the collar (pure fabric, not light armor, not an energy pennant). mantis-armor helmet with
twin compound eyes, glowing crimson visor. UE5 cinematic render, rim light, film grain, highly
detailed.

Negative: extra limbs, extra eyes, blurry, mutated helmet, visible human face, modern casual
clothes, anime, cel-shading, illustration, low-poly, rubber suit, generic superhero armor, plain
full-face helmet, human eyes, tail, energy pennant, light armor, symmetric design, bulky mech blob,
bright saturated full-body color, plastic toy finish.
```

> 注意本范例的排布：锁块 → **取景（白底正面全身）→ 身份 → 体型 → 配色 60/30/10 → 两层结构 + 覆盖率 + 非对称 → 母题 / 头盔 → 腰带 → Warframe 材质 → 织物配件 → 头眼 → 负面**（对应 §2.6 顺序）。
> 关键：① 取景句紧贴锁块第一句，防模型自加场景；② 体型句紧接身份，防退化成 bulky mech；③ **配色紧接体型前置**（模型最容易在颜色上跑偏）；④ 识别色写成 `oxidized crimson`（沉），饱和度交给 `glowing crimson visor and energy channels`；⑤ 不对称写成**结构级**（右肩重甲 + 冠饰偏置 + 偏心胸核），不是色块拼贴；⑥ 围巾写 `woven cloth`（纯织物），不用 light armor。

---

## 2.5 KR × Warframe 融合写法（本技能风格核心）

假面骑士的"帅气高级"不是靠喊一句 Warframe，而是**把 KR 身份骨架焊死、再用 Warframe 机甲材质 / 分件去包裹**：

- **身份骨架（KR 锚点，不可让 Warframe 盖过）**：首句点名 `Kamen Rider (仮面ライダー)`、`NOT a generic Warframe / Destiny mech suit`；腰带（henshin belt / driver buckle）做成**醒目居中大腰带扣并详细描述其机制**；非人复眼 / 单眼 visor helmet（**不是真兽头**）；命名母题在头盔冠饰 + 胸甲核心可读出；深色分件底衣 + 局部硬甲片叠层（露缝隙）。
- **机甲包裹（Warframe 材质 / 分件，负责"高级感"）**：在身份骨架上叠加——**装甲材质统一为金属 / 陶瓷弹道装甲板（metal / ceramic ballistic plating），这是效果最稳最高级的基底**；ornate ballistic plating（华丽分件，有棱角 / 厚度 / 接缝 / 铆钉）、glowing energy channels（发光能量通道贯穿甲片）、Tennogen ornamental seams（装饰雕花接缝）、Void-light emissive trim（虚空光自发光描边，做三色体系的发光边）。**金 / 水晶 / 彩色等只作小范围装饰**（铆钉、纹章、描边、局部镶嵌），绝不能当成甲片主体——大面积镀金 / 全水晶甲片会显得廉价（low）。**覆盖率**：胸 / 肩 / 臂 / 腰 / 大腿 / 小腿均被甲片包裹，深色分件底衣仅在活动关节（颈、肘、膝、腰折）露出，避免下半身空荡。
- **配色 60/30/10（见 §2.1，本技能风格核心）**：**不要为了"高级"把颜色全换成中性色**——那会抹平辨识度、五个骑士撞成一身。廉价感的真因是**大面积高饱和**，不是"有颜色"。正解：**dominant 60%** 中性色（**每个骑士明度 / 冷暖必须错开**，是第二重辨识度）+ **secondary 30%** 识别色（**沉下去**：降饱和、加深、改哑光，`deep jade-green` 而非 `emerald green`）+ **accent 10%** 金属与自发光；**彩度发光化**——饱和度放在 visor / energy channels 的发光上，不放进大面积甲片材质；**一色原则**——最多 1 识别色 + 1 金属色 + 1 发光色。
- **底衣不局限于黑**：undersuit 可以是白 / 骨白 / 炭黑 / 深灰，跟随 dominant 走；**与甲片保持明度差**，让缝隙里的底衣勾出分件轮廓。
- **禁止完全对称（本技能默认强制）**：至少一处**结构级**不对称——单侧重型肩甲 / 单侧披风 / 冠饰偏置 / 腰带扣偏心 / 双腿甲片不同规格 / 单臂武装。**不是随机色块拼贴**。（DNA 层 D4 仍为可选；本技能产出层强制，见 `design-dna-and-imagination.md` D4 双层口径。）
- **服饰配件：纯织物，禁止轻甲**：围巾 / 披风 / 衣领 / 裙摆 / 臂袖等是骑士传统服饰配件（D10 已放行），**材质必须是 fabric / cloth（布料 / 织物）**——写 `flowing cloth cape`、`woven fabric scarf`、`textile skirt panel`；**禁止写 light armor / 轻甲**（轻甲披风 / 轻甲裙摆观感廉价，且和硬甲片糊在一起失去软硬对比）。用作服装装饰制造动势——**位置限定在衣领、披风、围巾、裙摆、臂袖等服装部位，绝不可写成从臀部 / 脊椎伸出的尾巴**。提示词里禁止出现 `tail`、`energy pennant`、`light armor`。
- **体型（必须描述）**：主体是「变身后的人类骑士」，不是通用机甲块。务必用 humanoid male hero build 描写——`lean athletic humanoid male build, broad shoulders, defined musculature beneath the suit, ~185cm commanding stance`；禁止写成臃肿无分别的 bulky mech blob 或不成比例的怪物体型。体型句放在**身份声明之后、两层结构之前**，与前四项（取景 / 身份 / 体型 / 结构）一起前置，防止模型把主体画成无差别机甲。
- **身份优先级**：`use Warframe as material / lighting quality, NOT as subject identity`——任何一句都不得让主体退化成通用 Warframe 战甲。

## 2.6 提示词描述顺序（越靠前，AI 越遵守）

生图模型对提示词**靠前的指令响应最强、靠后的最弱**——把「最容易跑偏、最该锁死」的指令放到最前。锁定块固定置顶，其后按此顺序排：

1. **取景指令（最前）**：`front-facing full-body character shot, standing upright, arms at sides, pure white seamless studio background, product-shot framing, no environment, no props`。模型极易自行加场景，必须紧接锁块第一句。
2. **身份声明**：`Kamen Rider (仮面ライダー)`、`NOT a generic Warframe / Destiny mech suit`——防止退化成通用战甲。
3. **体型（必须描述）**：`lean athletic humanoid male build, broad shoulders, defined musculature beneath the suit, ~185cm commanding stance`——防止画成臃肿无分别的机甲块或不成比例怪物体型。
4. **配色 60/30/10（前置，模型最容易在颜色上跑偏）**：dominant 中性色（明度 / 冷暖错开）+ secondary 识别色（**沉**：`deep / oxidized / matte [色]`）+ accent 金属与自发光；**彩度发光化**——饱和度写进 `glowing [色] visor and energy channels`，不写进大面积甲片材质；**一色原则**。
5. **两层结构 + 覆盖率 + 非对称**：`[中性色] segmented undersuit with visible seam lines`（**底衣可白可黑**，与甲片保持明度差）+ `deep [识别色] metal / ceramic armored plates` 叠层；**高覆盖率**——胸 / 肩 / 臂 / 腰 / 大腿 / 小腿均被甲片包裹，底衣仅活动关节（颈 / 肘 / 膝 / 腰折）露出，避免下半身空荡；**至少一处结构级不对称**（单侧重甲 / 单侧披风 / 冠饰偏置 / 腰带扣偏心 / 双腿甲片不同规格）。
6. **命名母题**：头盔冠饰 + 胸甲核心可读出母题。
7. **腰带装置**：醒目居中大腰带扣 + 机制描述（D1）。
8. **Warframe 材质包裹**：甲片基底统一 `metal / ceramic ballistic plating`，glowing energy channels / Tennogen ornamental seams / Void-light emissive trim；**金 / 水晶 / 彩色只作铆钉 / 纹章 / 描边级小装饰，绝不作甲片主体**（大面积镀金 / 全水晶 = low）。
9. **织物服饰配件**：围巾 / 披风 / 衣领 / 裙摆 / 臂袖用 **fabric / cloth（纯布料）**——`flowing cloth cape`、`woven fabric scarf`、`textile skirt panel`；**禁用 light armor / 轻甲**，无尾巴、非能量旗。
10. **头部 / 眼部**：非人复眼 / 单眼 visor（非真兽头），发光色 = 识别色的高饱和版本（彩度落点）。
11. **负面词（结尾）**：追加 `generic superhero armor, plain full-face helmet, human eyes, tail, energy pennant, light armor, symmetric design, bulky mech blob`。

> 简记：**取景 → 身份 → 体型 → 配色 → 结构（含非对称）→ 母题 → 腰带 → 材质 → 织物 → 头眼 → 负面**。
> 前五项（取景 / 身份 / 体型 / **配色** / 结构）是「防跑偏五件套」，务必前置——其中**配色**因为模型最容易跑偏，必须紧接体型之后；后几项顺序可调。

---

## 3. 从图片反推提示词（图生提示词解析清单）

用户给了一张骑士图、想为它写变身/战斗提示词时，按这个清单解析：

| 提取项 | 看图看什么 | 映射到 |
|---|---|---|
| 主 / 副色 | 胸甲、左右半身 | base / accent |
| 眼部 | 单眼 / 复眼 / 光色 | visor |
| 不对称 | 左右半身是否异色 | 变身模板 B / C |
| 装甲块感 | 是大块拼装还是流线 | 模板 B（机械）vs D（流体） |
| 头饰 | 兔耳 / 角 / 触角 / 围巾 | 标志元素 |
| 道具 | 腰带 / 手机 / 腕带 / 卡片 | 激活手势 + 模板选择 |
| 武器 | 手 / 腰侧 / 背上有无武器 | 武器类型与打法（见 battle 参考） |
| 气质 | 科技 / 复古 / 双人 | 模板 A–E 选择 |

**解析后**：把结果填进 `references/transformation-prompts.md` 的对应模板，
镜头一律按 `references/transformation-camera-blocking.md` 的四拍 + Cam1–4 写。

---

## 4. 负面词（角色设计专用）

```
extra limbs, extra eyes, unintended asymmetry, deformed proportions, messy seams,
blurry, mutated helmet, visible human face, modern casual clothes, low detail, low-poly,
anime, cel-shading, cartoon, illustration, painting, rubber suit, tokusatsu, plastic toy, chibi
```

---

## 5. 常见问题

| 问题 | 原因 | 修正 |
|---|---|---|
| 出成动画/插画/低模风 | 没带画风锁定块，或负面词没禁 anime/low-poly | 锁定块放最前 + 必禁关键词全带 |
| 装甲像塑料玩具/低模 | 缺「PBR 材质、Nanite 细节、能量纹路、电影布光」描述 | 补 `UE5 real-time render`、`Nanite high-poly detail`、`glowing energy veins`、`cinematic three-point lighting` |
| 左右异色骑士混色 | 没显式写 left / right | 必须写 `left half [A], right half [B]` |
| 复眼变一只眼 | 没写 `twin compound eyes` | 显式写眼部数量与形态 |
| 生成的骑士与参考图不像 | 纯文生图 | 改用图生图，把参考图作为垫图，再套锁定块 |
