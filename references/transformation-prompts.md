# 假面骑士变身 · AI 视频生成提示词体系

> 面向 Seedance / Kling / Gen-3·Gen-4 / Hailuo 等文生视频 / 图生视频工具的
> **可直接使用**的变身动作提示词库 + 角色设计提示词写法。
> 所有「动作提示词」为正文英文（生成器优先英文），配中文结构与节拍注解。

---

## 〇、通用参数与适配说明

| 项目 | 推荐值 | 说明 |
|---|---|---|
| 单条成片时长 | **5–7s**（完整变身）；1.5–3s（片段） | 变身是「激活→包裹→拼装→定格」四拍，5s 以上才完整 |
| 帧率 | **24fps**（电影感）/ 30fps（流畅） | 24fps 更接近特摄质感 |
| 镜头 | 优先中景→特写→全景的 2–3 段运镜 | 定格瞬间给一个 slow-mo 或静止帧 |
| 一致性 | 用**图生视频**（先出角色设计图再驱动）远优于纯文生 | 见第三节 |
| 负面词（通用） | `morphing face, extra limbs, floating armor, flickering, lowres, watermark, multiple riders overlapping` | 防止装甲穿模/肢体乱变 |

**四拍结构（所有骑士通用）**
```
T0 激活  道具发光、手势启动          慢（0.0–0.8s）
T1 包裹  光线沿身体布线 / 粒子涌动     加速（0.8–2.2s）
T2 拼装  装甲板从四周飞入拼合          高潮（2.2–4.0s）
T3 定格  爆闪 + 标志性 pose + slow-mo  骤停（4.0–6.5s）
```

---

---

## 〇·一、画风锁定（全片强制 · UE5 / Warframe）

> 所有变身 / 战斗提示词必须在开头带上下面这段「画风锁定」，
> 否则模型极易产出动画、插画、橡皮套特摄或低模画面。

```
画风锁定：UE5（Unreal Engine 5）实时渲染引擎的电影级画质。写实 PBR 材质与 Nanite 超高模
几何细节、Lumen 全局光照与体积雾、电影级三点布光与浅景深；Warframe 风格高科技生物机械
装甲——流线型能量装甲、发光能量纹路（energy veins）、能量护目（glowing visor）、动态
战斗姿态。禁止卡通描边、赛璐璐上色、二次元渲染、橡皮套特摄塑料感、低多边形与粗糙贴图。
整体观感等同 Warframe 宣传 CG 与 UE5 技术演示（如《黑客帝国：觉醒》）。
```

- **必写关键词**：`UE5 real-time render, Nanite high-poly detail, Lumen global illumination, volumetric fog, physically-based materials, subsurface scattering, Warframe-style biomechanical armor, glowing energy veins, energy visor, dynamic combat pose, cinematic three-point lighting, rim light, film grain, shallow depth of field, motion blur`
- **必禁关键词**：`anime, cel-shading, cartoon, illustration, painting, comic outline, rubber suit, tokusatsu practical suit, low-poly, low detail, flat shading, plastic toy, chibi`

---

## 〇·五、双参考图 → 变身提示词 解析工作流（含专业人设元提示词）

> 直接用法：把下面【元提示词】整段复制进对话，再 **@ 两张参考图**——① 人类状态图、② 变身状态图，
> 即可一键得到可直接用于 Seedance / Kling / Gen 的英文变身提示词（带中文节拍与适配说明）。
> 这是本体系从「静态模板」升级为「图生提示词」的关键能力，且明确走「人类 → 骑士」的变身链路。

### 双参考图规范（务必 @ 两张）
- **[HUMAN_IMG] 人类状态图**：变身前的真人 / 素体姿态，作为视频**起始帧**与动作起点。
- **[RIDER_IMG] 变身状态图**：成型的骑士装甲设计，作为**角色外观参考 / 终帧目标**。
- 生成时写法：`@[HUMAN_IMG] 作为起始帧（人类形态），@[RIDER_IMG] 作为骑士外观与终帧参考`；
  提示词内用 `[HUMAN]` / `[RIDER]` 指代，便于模型对照衔接两态。

### 元提示词（复制即用）
```
你是一名专业的特摄变身分镜师兼 AI 视频提示词工程师，精通假面骑士（Kamen Rider）等
日本特摄的变身演出语言：变身手势、道具激活、身体律动、光粒子特效触发时机、定格 pose，
以及多机位镜头调度（Cam1–4 覆盖方案）。

任务：当用户 @ 两张参考图——① 人类状态图 [HUMAN_IMG]、② 变身状态图 [RIDER_IMG]——时，
先分别解析两张图，再输出一套可直接用于 Seedance / Kling / Gen-3·Gen-4 的英文变身视频
提示词，描述从人类形态变身（henshin）为骑士形态的完整过程，并附中文节拍注解。

【解析步骤】
1. 解析 [HUMAN_IMG]：体型、发型 / 面容、日常服装、随身道具、姿态气质。
2. 解析 [RIDER_IMG]：配色（主色 base / 副色 accent / 眼部光色 visor）、装甲分件
   （胸甲核心、肩甲、靴手、是否左右不对称）、头部（单眼 or 复眼、拟态元素、围巾 / 触角）、
   变身道具（腰带 / 手机 / 腕带 / USB / 卡片）、整体气质（科技 / 魔法 / 双人共体 / 复古传奇）。
3. 建立映射：人类图的姿态 / 体型 → 变身起点；骑士图外观 → 终态目标。依骑士气质匹配模板
   A 通用插卡 / B 双素材融合 / C 双人共体 / D 科技流体光 / E 复古传奇，或混合。
4. 用解析结果替换模板占位符，生成最终提示词。

【镜头调度规范】四拍：T0 激活(中景 Cam1) → T1 包裹(近景 Cam1) →
T2 拼装(全景 + 侧环绕 Cam2，Build 类加 Cam3 顶拍护盾墙) →
T3 定格(低角 Cam4 + freeze 0.5s + slow-mo)。全程不跳轴、光向一致。

【参考图指令】提示词开头写明：以 [HUMAN_IMG] 为起始帧（人类形态），[RIDER_IMG] 为骑士
外观与终帧参考；变身过程须从人类姿态平滑过渡到骑士终态，保持人物同一性（脸型 / 体型一致）。

【输出格式】严格 6 字段：
① 角色外观与设定（英文，分别写人类态与骑士态，并说明二者同一性）
② 镜头调度（英文，含 Cam1–4 与四拍切换点，首帧锁定人类）
③ 动作序列分步（英文，带 T0–T3 时间码，T0 起于人类、T3 止于骑士定格）
④ 特效与节奏控制（英文）
⑤ 建议时长与帧率（如 6.5s / 24fps）
⑥ 适配角色设定（中文，说明该角色为何适配此模板）
并附：负面词（negative prompt，须含 `identity mismatch between start and end frame`）。

【约束】提示词正文用英文（生成器优先）；节拍与适配用中文。只输出可直接使用的提示词，不写多余解释。
```

### 双图解析清单（喂图前自查）
| 参考图 | 提取项 | 映射到 |
|---|---|---|
| 人类图 | 体型 / 发型 / 日常服 / 姿态 | ③ T0 起点、④ 同一性 |
| 骑士图 | 主 / 副色 | ① base / accent |
| 骑士图 | 眼部 | ① visor |
| 骑士图 | 不对称半身 | 模板 B / C |
| 骑士图 | 头饰 / 围巾 / 触角 | ① 标志元素 |
| 骑士图 | 道具 | ② 激活手势 + 模板选择 |
| 双图 | 气质一致性 | 模板 A–E 选择 |

### 示例（输入：@ 人类图（黑发青年便装）+ @ 骑士图（红蓝不对称、兔耳、双瓶罐））
元提示词判定 → **模板 B**（双素材融合 + 机械拼装）。输出提示词开头写明：
`@[HUMAN_IMG] 起始帧（便装青年）→ @[RIDER_IMG] 终态参考`；① 分别描述两态并声明同一人；
② 套用 B 的 Cam1–4；③ T0 从青年拔瓶罐起手、T3 兔耳骑士定格；⑥ 写明「双素材融合型主角」，
并自动带上护盾墙顶拍（Cam3）与 match-cut 裂墙镜头。

---

## 一、变身核心机制调研（拆解）

### 1. 变身手势（Transformation Gestures）
- **持道具启动**：将瓶罐 / 记忆体 / 卡带举至腰侧或胸前，再插入驱动器。
- **交叉双臂**：Build 的「Best Match」——双臂在胸前交叉后大幅展开（重复两次），喊「ベストマッチ！」。
- **双指前推 / 合体**：W 的「二人一体」——两人各持记忆体，同步向腰带插入，半身全息叠合。
- **转钥匙 / 拉操纵杆 / 掰卡带**：Drive 拧 `Advanced Ignition` 车钥匙；Build 拉曲柄；Ex-Aid 拉 `Action Lever`（音效「Gacchan!」）。
- **拍按钮 / 拍胸**：Faiz 翻盖手机输入代码；W 拍 `Maximum Slot` 按钮触发必杀。
- **招牌举手定格**：Decade 持卡前推「Kamen Ride！」；昭和骑士单手叉腰 / 指天。

### 2. 道具激活方式（Prop Activation）
| 类型 | 代表 | 激活动作 |
|---|---|---|
| 腰带状 Driver | Build / W / Drive / Ex-Aid / OOO | 插入瓶罐·记忆体·卡带 → 转曲柄 / 拉拉杆 / 按按钮 |
| 手机型 | Faiz（555） | 翻盖输入变身代码，光子血液生成 |
| 腕带型 | Drive `Shift Brace` | 插入联动道具，无线信号触发 |
| USB 记忆体 | W `Gaia Memory` | 插入腰带左右双槽（Soul 右 / Body 左） |
| 纯手势 / 戒指 | 部分形态 | 戴指环念咒，装甲凭空浮现 |

### 3. 身体律动节奏（Body Rhythm）
- **三段式张弛**：激活段「慢而克制」→ 包裹段「加速旋转 / 粒子涌动」→ 定格段「骤停定帧」。
- **Build 节拍**：摇瓶（蓄能）→ 插瓶（Best Match 音效）→ 交叉臂展开 → 拉曲柄至满 → 护盾墙闭合。
- **W 节拍**：两人背靠背同步 → 记忆体插入 → 半身全息从一侧滑过覆盖 → 合体完成。
- **参考 BPM**：包裹段约 120–140 BPM 的脉冲感，定格前留 1 拍静默。

### 4. 光线与粒子特效触发时机（FX Timing）
- **T0**：道具核心冷光/暖光点亮（蓝白 / 橙红）。
- **T1**：光线从腰带沿躯干向上「布线」（Faiz 的 `Photon Stream` 红流；Build 的流道生成）。
- **T2**：数据碎片 / 火花粒子环包裹全身，形成能量茧。
- **T3**：装甲分件从画面四周飞入、吸附拼合（armor assembly）。
- **T4**：全身爆闪（white flash）+ 烟尘环 + 定格 pose。
- **特殊**：Build 在 T2 阶段生成「护盾墙」从前后闭合包住身体。

### 5. 变身完成定格动作（Final Pose）
- 跨步站姿 / 单膝微曲，重心压低。
- 指天、指敌、或 weapon ignite（武器展开发光）。
- 标志性手势：Build 双臂展开的 Best Match；Decade 持卡前推；W 双人交错跨步。
- 定格后**静止 0.4–0.6s** 再接 slow-mo 收尾，强化「完成感」。

---

## 二、结构化 AI 视频生成提示词（可直接使用）

> 每条均含 5 要素：① 角色外观与设定 ② 镜头景别与运镜 ③ 动作序列分步 ④ 特效与节奏 ⑤ 时长与帧率。

### ▍模板 A — 通用腰带插卡变身（参数化，可替换骑士名）
```
① CHARACTER: A tokusatsu Kamen Rider in sleek armored suit, [COLOR A] and [COLOR B]
   two-tone plating, insectoid single-eye visor, [MOTIF] chest emblem, standing in a
   dim sci-fi lab, volumetric rim light.
② CAMERA: [Coverage Plan] T0 MS eye-level, Cam1 locked tripod, slow push-in to waist as
   he draws the device (0–0.8s); T1 CU on the Driver, Cam1 locked focus, energy lines
   trace up torso (0.8–2.2s); T2 FS + low angle, Cam2 side orbit 20° as armor plates fly
   in and snap on (2.2–4.0s); T3 Cam4 low-angle hero, push-in + freeze 0.5s then slow-mo
   on the pose (4.0–6.5s). Keep belt light source consistent; no axis flip.
③ SEQUENCE:
   0.0-0.8s  Rider pulls [PROP] from belt, raises it to chest, glow ignites.
   0.8-2.2s  Inserts prop into Driver; energy lines trace up torso (Photon Stream style).
   2.2-4.0s  Armor plates fly in from off-screen and snap onto body piece by piece.
   4.0-6.5s  White flash; Rider strikes [POSE]; freeze 0.5s, slow-mo tail.
④ FX/RHYTHM: Cool blue build glow at T0, shift to [COLOR] at T2; particle ring at
   T1; impact flash + dust ring at T4. Pace: slow-open, accelerate mid, hard stop.
⑤ FORMAT: 6.5s, 24fps, image-to-video preferred.
⑥ 适配角色设定（SUITABLE FOR）：通用母版，适合任意「腰带 + 插入式道具（瓶罐 / 记忆体 /
   卡带 / 钥匙）」的单人原创骑士。配色、头部、动机 [MOTIF] 全参数化，建议先定稿本模板，再按
   B–E 风格二次改造。不挑角色性格，科技 / 近未来 / 通用特摄英雄皆可。
```

### ▍模板 B — Build 风格（交叉臂 + 护盾墙拼装）
```
① CHARACTER: Kamen Rider Build RabbitTank form — white base suit, left half red
   (Rabbit) wild armor, right half blue (Tank) panzer armor, asymmetric rabbit+tank
   head with twin compound eyes, Build Driver belt at waist. Urban night rooftop.
② CAMERA: [Build = 机械拼装 + 护盾墙] T0 MS, Cam1 eye-level slight low, locked as he
   shakes & slots bottles (0–0.7s); T1 CU on belt + cross-arm "Best Match", Cam1 push-in
   (0.7–1.4s); T2 FS, Cam2 side orbit 25° showing armor plates fly in and lock, Cam3
   top-down for the shield-wall close-in (1.4–4.2s); T3 Cam4 low-angle hero, match-cut on
   wall shatter, white burst, freeze 0.5s + slow-mo (4.2–6.5s).
③ SEQUENCE:
   0.0-0.7s  Draws two Fullbottles, shakes them, slots left (Rabbit) + right (Tank).
   0.7-1.4s  Crosses both arms at chest, snaps them open wide — "Best Match!" pose.
   1.4-2.6s  Cranks the belt lever to max; belt asks "Are you ready?", rider nods.
   2.6-4.2s  Translucent energy walls close in from front/back; suit materializes
             inside the shell, armor panels lock with mechanical clicks.
   4.2-6.5s  Walls shatter outward, white burst; rider throws open arms in final
             Best Match pose, freeze + slow-mo.
④ FX/RHYTHM: Red+blue dual glow from bottles; geometric light trails from belt;
   shard particles during wall phase; hard white pop at T4. Beat: restrained →
   explosive cross-arm → mechanical assemble → freeze.
⑤ FORMAT: 6.5s, 24fps.
⑥ 适配角色设定（SUITABLE FOR）：适合「最佳搭配 / 双素材融合」型主角——两人或两物合体、左右
   不对称双色、科学家 / 发明家 / 天才人设、机械拼装美学。角色需有明确「组合技」概念（如兔子+坦克），
   强调理性、实验、变身如组装。不适合纯魔法 / 灵能设定。
```

### ▍模板 C — W 风格（双记忆体半身合体）
```
① CHARACTER: Kamen Rider W CycloneJoker — left half matte black (Joker) body armor,
   right half translucent green (Cyclone) wind armor, shared central W crest, long
   flowing green scarf, twin-eye helmet. Futo city street at dusk.
② CAMERA: [W = 双人融合] T0 two-shot MS, Cam1, partners back-to-back as they draw
   memories (0–0.9s); T1 CU on Double Driver insert, Cam1 (0.9–1.8s); T2 Cam2 side orbit
   as green/black halves sweep across and fuse over the body, scarf whips (1.8–4.8s);
   T3 Cam4 low-angle hero crossed-leg stance, scarf settles, freeze + slow-mo (4.8–6.5s).
   Keep both users on the same screen side pre-merge to avoid axis flip.
③ SEQUENCE:
   0.0-0.9s  Two partners draw Gaia Memories (Cyclone right / Joker left), sync nod.
   0.9-1.8s  Simultaneously slam memories into Double Driver — "Cyclone! Joker!".
   1.8-3.4s  Green holographic half slides from right, black half from left, fuse
             over the body; scarf whips in digital wind.
   3.4-4.8s  Chest W-crest lights; full suit locks in with a soft chime.
   4.8-6.5s  Rider lands crossed-leg hero stance, scarf settles, freeze + slow-mo.
④ FX/RHYTHM: Green wind streaks + black data flakes; split-screen fusion glow;
   no hard flash — smoother merge than Build. Beat: tandem calm → snap insert →
   glide fuse → settle.
⑤ FORMAT: 6.5s, 24fps.
⑥ 适配角色设定（SUITABLE FOR）：适合「二人一体 / 双魂共体」型角色——两名搭档共享一具身体，
   典型侦探搭档 / 阴阳二元：一方提供元素与精神（Soul），一方提供肉体与格斗（Body）。需围巾、
   双色半身、合体仪式感。适合 buddy-cop、双主角、duality 主题。
```

### ▍模板 D — Faiz 风格（光子血液流线）
```
① CHARACTER: Kamen Rider Faiz — black Sol Foam undersuit, silver Sol Metal armor,
   red Photon Stream lines running shoulder to gauntlet, red single visor (Ultimate
   Finder), Fullmetal Lung chest. Night highway.
② CAMERA: [Faiz = 科技流体光] T0 CU on Faiz Phone flip + keypad, Cam1 (0–1.0s); T1 CU on
   belt ignite, Cam1 locked (1.0–2.2s); T2 Cam2 side, pull back to FS as red Photon
   Streams weave the armor on the fly, Cam3 top-down optional for light-weave volume
   (2.2–4.0s); T3 Cam4 low-angle, visor flash + fist power-up, freeze + slow-mo
   (4.0–6.0s). Cool tone, minimal orbit — emphasize liquid light not motion.
③ SEQUENCE:
   0.0-1.0s  Rider flips open Faiz Phone, types 5-digit code on keypad.
   1.0-2.2s  Phone slots into Faiz Driver; red Photon Blood ignites at belt.
   2.2-4.0s  Glowing red streams race up the body, weaving the silver armor on the
             fly (suit "knits" itself from light).
   4.0-6.0s  Visor flashes red, "Complete!"; rider powers up fist, freeze + slow-mo.
④ FX/RHYTHM: Red bioluminescent fluid-light, no plates flying — armor forms FROM
   the streams. Subtle electric crackle. Beat: techy input → surge → weave → ready.
⑤ FORMAT: 6.0s, 30fps (smoother for liquid light).
⑥ 适配角色设定（SUITABLE FOR）：适合「科技孤狼 / 秘密组织特工」型角色——手机或数码道具激活、
   光子血液式「光编织装甲」、冷峻近未来美学。角色宜带孤独感、组织背景、数据 / 网络母题。
   适合赛博、agent、反英雄设定，强调液态光而非块装。
```

### ▍模板 E — 昭和 / Decade 风格（举手定格）
```
① CHARACTER: A classic Kamen Rider — emerald-green torso, silver riveted belt,
   red scarf, single horned cicada-eye helmet, white gloves & boots. Open plaza.
② CAMERA: [Showa/Decade = 重 pose 轻运动] T0 low-angle LA, Cam4, mostly static as he
   raises the card/fist (0–0.8s); T1 MS, Cam1, single light-wash down the body (0.8–2.5s);
   T2 Cam4 low-angle hero, one slow push-in on the pointing pose (2.5–4.0s); T3 hold pose,
   scarf flares, freeze + slow-mo tail (4.0–5.5s). No orbit, no whip — static hero framing.
③ SEQUENCE:
   0.0-0.8s  Rider raises a Rider Card / clenches fist toward sky, calls the name.
   0.8-2.5s  Brief light wash sweeps down the body, suit appears in one clean pass.
   2.5-4.0s  Rider strikes the iconic pointing pose (card forward / finger to sky).
   4.0-5.5s  Holds pose, scarf flares, freeze + slow-mo tail.
④ FX/RHYTHM: Minimal particles, strong single-color flash, emphasis on the POSE
   not the assembly. Beat: declarative → instant suit → hold.
⑤ FORMAT: 5.5s, 24fps.
⑥ 适配角色设定（SUITABLE FOR）：适合「经典 / 传奇骑士」型角色——卡片或简易腰带激活、重 pose
   轻拼装、昭和怀旧或「传说骑士」致敬。设计宜极简（绿 / 银 / 红 + 围巾 + 单眼），适合客串、
   legend rider、复古 tribute，不追求复杂变形。
```

> **拆分建议**：若生成器连贯性差，把每条拆成 3 个 clip——
> Clip1 激活（0–1.5s）、Clip2 拼装（1.5–4s）、Clip3 定格（4–6.5s），后期拼接。

---

## 三、如何写「角色设计」提示词（装甲 / 配色 / 造型）

先出**静态设计图**（图生视频的前置），再驱动变身。设计提示词写法：

### 3.1 配色系统描述法
- 用「base + accent + visor」三段式：`white base suit, red left armor, blue right armor, glowing cyan visor`。
- 双色半身要显式写左右：`left half [A], right half [B]`（W / Build 关键）。
- 金属感：`metallic silver plating, matte black undersuit, glossy enamel finish`。

### 3.2 装甲材质与分件
- 胸甲：`central chest core with [MOTIF] emblem, raised collar guards`。
- 肩甲：`asymmetric shoulder pauldrons, one spiked one smooth`。
- 靴/手：`reinforced greaves, articulated finger gloves`。
- 分件感：`segmented plate armor with visible seam lines, mechanical rivets`。

### 3.3 头部与标志元素
- 单眼：`single horizontal visor slit` / 复眼：`twin compound eyes`。
- 拟态：`insectoid / bat-wing / rabbit-ear crest on helmet`。
- 招牌件：`flowing scarf, antenna feeler, horned crest`。

### 3.4 角色设计范例提示词
```
Character design sheet of an original Kamen Rider: sleek biomechanical armored suit,
white base undersuit, left half crimson wild armor (rabbit motif, jagged edges),
right half cobalt-blue tank armor (flat riveted plates), asymmetrical helmet with
twin compound eyes and a rabbit-ear crest, central chest core glowing amber,
Build-style driver belt at waist, metallic highlights, UE5 cinematic render, film grain,
full body, front view, clean background, highly detailed, Warframe aesthetic.
Negative: extra eyes, deformed proportions, messy seams, low detail.
```

### 3.5 负面词（角色设计）
`extra limbs, extra eyes, asymmetric mismatch unintended, blurry, mutated helmet,
visible human face, modern casual clothes, low-poly, rubber suit, anime, cel-shading`。

---

## 四、速查表（汇总）

| 骑士 / 风格 | 道具 | 标志手势 | 主配色 | 定格动作 |
|---|---|---|---|---|
| Build | Build Driver + 满装瓶罐 | 交叉双臂展开（Best Match） | 白 / 红 / 蓝 | 双臂展开的 Best Match pose |
| W | Double Driver + Gaia Memory | 双人同步插记忆体 | 黑 / 绿 | 跨步 + 围巾飘 |
| Faiz | Faiz Phone + Driver | 翻盖输代码 | 黑 / 银 / 红 | 握拳蓄力 |
| Drive | Drive Driver + 变档战车 | 拧车钥匙 | 红 / 银 | 指前「Hissatsu」 |
| Ex-Aid | Gamer Driver + 卡带 | 拉拉杆「Gacchan!」 | 红 / 白 / 蓝 | Level Up 叉腰 |
| Decade / 昭和 | 卡片 / 腰带 | 持卡前推 / 指天 | 绿 / 银 / 红 | 指天或持卡定格 |

---

---

## 五、镜头调度系统（Camera Blocking）

> 变身戏观感 70% 靠调度：同样的动作，固定机位 vs 环绕+slow-mo 差别巨大。
> 本节把「镜头」从单条提示词里抽出来，作为可复用的覆盖方案（Coverage Plan）。

### 5.1 为什么变身需要专门调度
- 变身 = **单一主体 + 强特效 + 节拍极明确**，调度只服务三件事：**hero 感、速度感、完成感**。
- 核心矛盾：特写保细节 ↔ 全景保气势；固定保连贯 ↔ 运动保动感。按四拍分配机位即可化解。

### 5.2 标准四拍覆盖方案（Coverage Plan）
| 节拍 | 景别 | 角度 | 运镜 | 时长 | 目的 |
|---|---|---|---|---|---|
| T0 激活 | 中景 MS | 平视/微低 | 固定或缓推入腰 | 0.8s | 交代道具与手势启动 |
| T1 包裹 | 近景 CU（切腰带动光）+ 过肩 | 固定 | 固定锁焦 | 1.4s | 看光线沿躯干布线 |
| T2 拼装 | 全景 FS + 低角 | 环绕 orbit 15–30° | 弧移 | 2.0s | 展装甲分件飞入拼合 |
| T3 定格 | 英雄低角 LA | 推近 + slow-mo | 0.4s 静止帧→慢放 | 1.5s | 完成感、定格 pose |

> 一句话：中景起手 → 近景看光 → 全景看装 → 低角英雄收。

### 5.3 多机位摆位（ASCII）
```
              [Cam3] 顶拍 / 俯视（看护盾墙闭合、粒子环）
                    |
 [Cam1] 正面 MS ── rider ── [Cam2] 侧 45° 环绕（装甲飞入主视角）
                    |
              [Cam4] 低角 LA（hero 定格，slow-mo 专用）
```
- **Cam1 正面**：T0 起手 + T3 正面定格，全程最稳。
- **Cam2 侧环绕**：T2 拼装主力，绕 15–30° 展示分件吸附。
- **Cam3 顶拍**：仅 Build 类「护盾墙内外」、Faiz 类「光流编织」用，强调体积。
- **Cam4 低角**：T3 英雄收尾 + slow-mo，制造压迫感与完成感。
- 切换点：T0→T1 切 Cam1 近景；T1→T2 切 Cam2；T2→T3 切 Cam4。

### 5.4 转场与节奏衔接
- **Match cut**：护盾墙「闭合→裂开」瞬间切到全景（Build 专用），遮住形变跳变。
- **Speed ramp**：T2 加速段升帧感（motion blur 加重），T3 骤停接 slow-mo（光流拖尾）。
- **Freeze frame**：定格帧静止 0.4–0.6s 再 slow-mo，强化「变身完成」的仪式感。
- **Flash cut / whip pan**：跨形态切换（如 Lv.1→Lv.2）用白闪或甩镜过渡。

### 5.5 拆 3 clip 的连贯性规则（关键）
若按「激活/拼装/定格」拆 clip 分别生成再剪辑，必须守住三条，否则拼接处跳戏：
1. **首帧一致**：每 clip 起始姿势 = 上一 clip 结束姿势（用同一张首帧图最稳）。
2. **光向一致**：腰带光源方向、主光色温全程不变（避免左光切右光）。
3. **不跳轴**：Cam1→Cam2→Cam4 的机位始终在骑士**同一侧 180° 内**，禁止正反翻轴。

### 5.6 各骑士的镜头性格
| 骑士 / 风格 | 调度重点 |
|---|---|
| Build | 环绕 + 护盾墙内外双机位（Cam3 顶拍），强调机械拼装的「块感」 |
| W | 双人背靠背分镜 → 合体推近（Cam1 主），强调「二人一体」的融合 |
| Faiz | 特写手机输码 → 拉远光流编织（Cam2 侧），科技冷感、流体光 |
| 昭和 / Decade | 固定低角 hero（Cam4），突出 pose 而非运动，几乎无环绕 |

### 5.7 镜头负面词（通用）
`shaky cam, handheld drift, jump cut, axis flip, lens distortion, fisheye, whip without reason`

> 在每套模板的 `② CAMERA` 后追加上述约束，可显著降低生成器「自己乱动镜头」的概率。

---

### 六、使用流程建议
1. **双参考图生提示词（推荐）**：复制「〇·五」的元提示词 → **@ 两张图（人类状态图 + 变身状态图）**
   → 让它解析两态并输出带专业人设、含 Cam1–4 机位脚本的英文变身提示词（自动填好 ①–⑥，
   且 T0 起于人类、T3 止于骑士，保持同一性）。只给文字设定也可，但双图效果最稳。
2. 若想手动控制：用第三节写**角色设计图**（文生图或图生图），再套用第二节对应模板驱动变身（图生视频）。
3. 镜头按第五节 Coverage Plan 取景；连贯性差时按「激活 / 拼装 / 定格」拆 3 clip（守住 5.5 三条规则）再剪辑。
4. 定格帧单独出一帧高清图，slow-mo 收尾增强完成感。
