# 变身镜头调度（Camera Blocking）· 深度方案

> 本文件是 `domn-film-kamen-raider` 的重点参考。
> 变身戏观感 **70% 靠调度**：同样的动作，固定机位 vs 四拍切换 + slow-mo，差别是「PPT」和「正片」的区别。
> **任何变身提示词都不允许只写一句「镜头推进」**，必须走完下面的四拍与 Cam1–4。

---

## 1. 为什么变身需要专门调度

变身 = **单一主体 + 强特效 + 节拍极明确**。调度只服务三件事：

- **hero 感** — 低角 + 定格，让角色看起来不可战胜。
- **速度感** — 环绕 + 粒子 + 速度线，让「包裹→拼装」有冲击力。
- **完成感** — 骤停定格 + slow-mo，给观众一个「变身完成」的仪式点。

核心矛盾：特写保细节 ↔ 全景保气势；固定保连贯 ↔ 运动保动感。
**解法：按四拍分配机位**——该静就静，该动就动。

---

## 2. 四拍 Coverage Plan（标准方案）

| 节拍 | 景别 | 角度 | 机位 | 运镜 | 时长 | 目的 |
|---|---|---|---|---|---|---|
| **T0 激活** | 中景 MS | 平视 / 微低 | Cam1 | 固定或缓推向腰 | 0.8s | 交代道具与手势启动 |
| **T1 包裹** | 近景 CU | 固定 | Cam1 | 锁定焦点，不晃 | 1.4s | 看光线沿躯干布线 |
| **T2 拼装** | 全景 FS | 低角 | Cam2 | 侧环绕 15–30° | 2.0s | 看装甲分件飞入拼合 |
| **T3 定格** | 英雄低角 LA | 低角 | Cam4 | 推近 + 定格 + slow-mo | 1.5s | 完成感、定格 pose |

> 一句话记：**中景起手 → 近景看光 → 全景看装 → 低角英雄收**。

### 各拍的拍摄要点

- **T0**：人物完整入画，道具是视觉焦点。机位稳定，给观众「看清他要做什么」。
- **T1**：切到腰带动光 / 光线沿身体上升。**这一拍必须静**，动了一分就丢细节。
- **T2**：唯一允许大幅运动的一拍。装甲分件从画面四周飞入，环绕展示体积与拼合。
- **T3**：定格 0.4–0.6s 静止帧，再以 30–50% 速度慢放 0.5–1s。给一个收束点。

---

## 3. 多机位摆位（Cam1–4）

```
              [Cam3] 顶拍 / 俯视（护盾墙闭合、粒子环、光流编织）
                    |
 [Cam1] 正面 MS ── rider ── [Cam2] 侧 45° 环绕（装甲飞入主视角）
                    |
              [Cam4] 低角 LA（hero 定格，slow-mo 专用）
```

| 机位 | 位置 | 职责 | 使用节拍 |
|---|---|---|---|
| **Cam1 正面** | 正前方，眼高 | 起手 + 看光 + 正面定格 | T0、T1 |
| **Cam2 侧环绕** | 侧面 45° | 装甲飞入拼合的主视角 | T2 |
| **Cam3 顶拍** | 正上方俯视 | 护盾墙闭合、粒子环、光流体积 | T2（仅部分类型） |
| **Cam4 低角** | 前方，膝高仰拍 | 英雄定格 + slow-mo | T3 |

**切换点**：T0→T1 切 Cam1 近景；T1→T2 切 Cam2；T2→T3 切 Cam4。
**始终在骑士同一侧 180° 内**，禁止正反翻轴。

---

## 4. 运镜参数建议

| 项目 | 建议值 | 说明 |
|---|---|---|
| T0 推入速度 | 缓慢，画面位移小 | 只做「注意力引导」，不做冲击 |
| T2 环绕角速度 | 8–15°/s（2s 走完 15–30°） | 太快看不清拼装，太慢没有速度感 |
| Cam4 机位高度 | 膝高（约 0.4–0.6m）仰拍 | 越低越有压迫感 |
| T3 定格时长 | 0.4–0.6s 完全静止 | 静止帧是「完成感」的来源 |
| T3 slow-mo | 30–50% 速度，0.5–1s | 定格之后才慢放，不要全程慢 |
| 焦距感 | T1 近景长焦压缩（约 85mm），T2 全景广角（24–35mm） | 近景压缩突出细节，广角放大空间与飞入的分件 |

---

## 5. 五类变身的调度变体

### A. 通用插卡型（腰带 + 插入式道具）
标准四拍，不特殊。
```
T0 Cam1 中景缓推向腰（拔/插道具）→ T1 Cam1 近景看光线沿躯干上升
→ T2 Cam2 侧环绕 20° 看装甲飞入吸附 → T3 Cam4 低角推近 + 定格 + slow-mo
```
保持腰带光源方向一致，不跳轴。

### B. Build 型（交叉臂 + 护盾墙）· 机械拼装
强调「块感」与「内外双层」。
```
T0 Cam1 中景微低，锁定（摇瓶、插瓶）
T1 Cam1 推近：交叉双臂、猛然展开的 Best Match pose
T2 Cam2 侧环绕 25° 看装甲分件飞入锁合 ＋ Cam3 顶拍护盾墙从前后闭合
T3 Cam4 低角：match-cut 切在护盾墙裂开的瞬间，白光爆出 + 定格 + slow-mo
```
**关键**：match-cut 必须切在「墙裂开」那一帧，用碎片遮住形变，观感最干净。

### C. W 型（双人融合）· 合体
强调「二人一体」。
```
T0 Cam1 双人中景，两人背靠背
T1 Cam1 近景：两人同步把记忆体拍进驱动器
T2 Cam2 侧环绕：绿/黑半身从两侧滑过、覆盖、融合；围巾在数字风里抽动
T3 Cam4 低角：跨步英雄站姿，围巾落定，定格 + slow-mo
```
合体前两人保持在画面同一侧，避免翻轴。

### D. Faiz 型（光子血液）· 流体光
强调「光织装甲」而非「块装」。
```
T0 Cam1 特写：手机翻盖、按键输入代码
T1 Cam1 近景锁定：腰带处红光点燃
T2 Cam2 侧机位拉远到全景：红色光流沿身体向上编织出银甲（Cam3 顶拍可选，看光织体积）
T3 Cam4 低角：面罩红光一闪，握拳蓄力，定格 + slow-mo
```
冷调、少环绕——**强调液态光，不强调运动**。建议 30fps（流体光更顺）。

### E. 昭和 / Decade 型（举手定格）· 复古传奇
强调 pose，不强调变形。
```
T0 Cam4 低角静态：举卡 / 握拳向天
T1 Cam1 中景：一道光洗过全身，装甲一次成型
T2 Cam4 低角英雄机位，一次缓慢推近到指天/持卡 pose
T3 保持 pose：围巾扬起，定格 + slow-mo 收尾
```
**不环绕、不甩镜**——静态英雄构图才是昭和味。

---

## 6. 转场技法

| 技法 | 用在哪 | 作用 |
|---|---|---|
| **Match cut** | 护盾墙「闭合→裂开」瞬间切全景（Build 类） | 用碎片遮住形变跳变，最干净的藏拙手法 |
| **Speed ramp** | T2 加速段加重动态模糊 → T3 骤停接 slow-mo | 制造速度落差，让定格更有分量 |
| **Freeze frame** | T3 定格 0.4–0.6s 静止帧 | 变身完成的仪式点 |
| **Flash cut / whip pan** | 跨形态切换（Lv.1→Lv.2 等） | 白闪或甩镜过渡，省掉中间形变 |

---

## 7. 拆 3 clip 生成的连贯性三规则

若生成器连贯性差，把变身拆成 3 个 clip 分别生成再剪辑。**必须守住三条**：

1. **首帧一致**：每个 clip 的起始姿势 = 上一个 clip 的结束姿势。最稳的做法是用同一张首帧图。
2. **光向一致**：腰带光源方向、主光色温全程不变（避免上一 clip 左光、下一 clip 右光）。
3. **不跳轴**：Cam1→Cam2→Cam4 始终在骑士同一侧 180° 内，禁止正反翻轴。

拆分建议：Clip1 激活（0–1.5s）、Clip2 拼装（1.5–4s）、Clip3 定格（4–6.5s）。

---

## 8. 常见失败与修正

| 症状 | 原因 | 修正 |
|---|---|---|
| 变身看着像 PPT | 全程一个固定机位 | 强制走四拍，至少切 3 次（MS→CU→FS→LA） |
| 装甲拼装看不清 | 全程全景，或环绕太快 | T2 用侧环绕 15–30°、2s 走完；角速度 8–15°/s |
| 变身没有完成感 | 没有定格帧 | T3 加 0.4–0.6s 静止帧 + slow-mo |
| 首尾不像同一个人 | 没守同一性 | 负面词加 `identity mismatch between start and end frame`；T0 起于人类图 |
| 镜头自己乱动 | 没写死机位 | 提示词里点名 Cam1–4 与切换点，并加镜头负面词 |
| 拼接处跳戏 | 违反拆 clip 三规则 | 检查首帧、光向、轴线 |
| 出成动画风 | 忘画风锁定 | 开头带锁定块 + 禁 anime/cel-shading（见 visual-style 参考） |

---

## 9. 镜头负面词（通用）

```
shaky cam, handheld drift, jump cut, axis flip, lens distortion, fisheye,
whip without reason, random zoom, static single shot throughout
```

> 把这段追加进每套变身模板的 `② CAMERA` 字段，可显著降低生成器「自己乱动镜头」的概率。

---

## 10. 可直接套用的 ② CAMERA 模板串

**标准型（A / 通用）**
```
② CAMERA: [Coverage Plan] T0 MS eye-level, Cam1 locked tripod, slow push-in to waist as he
draws the device (0–0.8s); T1 CU on the Driver, Cam1 locked focus, energy lines trace up torso
(0.8–2.2s); T2 FS + low angle, Cam2 side orbit 20° as armor plates fly in and snap on
(2.2–4.0s); T3 Cam4 low-angle hero, push-in + freeze 0.5s then slow-mo on the pose (4.0–6.5s).
Keep belt light source consistent; no axis flip.
```

**机械型（B / Build）**
```
② CAMERA: T0 MS, Cam1 eye-level slight low, locked (0–0.7s); T1 CU on belt + cross-arm
"Best Match", Cam1 push-in (0.7–1.4s); T2 FS, Cam2 side orbit 25° showing armor plates fly in
and lock, Cam3 top-down for shield-wall close-in (1.4–4.2s); T3 Cam4 low-angle hero, match-cut
on wall shatter, white burst, freeze 0.5s + slow-mo (4.2–6.5s).
```

**融合型（C / W）**
```
② CAMERA: T0 two-shot MS, Cam1, partners back-to-back (0–0.9s); T1 CU on driver insert, Cam1
(0.9–1.8s); T2 Cam2 side orbit as halves sweep across and fuse over the body (1.8–4.8s);
T3 Cam4 low-angle hero crossed-leg stance, freeze + slow-mo (4.8–6.5s). Keep both users on the
same screen side pre-merge.
```

**流体型（D / Faiz）**
```
② CAMERA: T0 CU on phone flip + keypad, Cam1 (0–1.0s); T1 CU on belt ignite, Cam1 locked
(1.0–2.2s); T2 Cam2 side, pull back to FS as light streams weave the armor (2.2–4.0s);
T3 Cam4 low-angle, visor flash + fist power-up, freeze + slow-mo (4.0–6.0s). Minimal orbit.
```

**复古型（E / 昭和-Decade）**
```
② CAMERA: T0 low-angle LA, Cam4, static (0–0.8s); T1 MS, Cam1, light-wash down the body
(0.8–2.5s); T2 Cam4 low-angle hero, one slow push-in on the pose (2.5–4.0s); T3 hold pose,
freeze + slow-mo tail (4.0–5.5s). No orbit, no whip.
```
