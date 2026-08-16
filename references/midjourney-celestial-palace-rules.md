# Midjourney 天宫提示词规则

本文件把上传的“天宫提示性 MJ”案例沉淀成 Midjourney 专用写法。目标不是照抄案例，而是保留它们稳定出图的结构：一个强空间事件、明确机位、可量化尺度、低噪声材质、原生参数后缀。

## 1. MJ 与 ChatGPT-image2 的区别

- **MJ 更吃前 1–2 句的视觉主语。** 开头必须先写画幅、镜头、核心空间事件和主体尺度，不要先写大量抽象风格词。
- **MJ 不适合长行政式分层。** 可以写长 prompt，但要像电影美术设定一样连续描述；少用“参数锁定、五层空间”这类内部术语。
- **MJ 需要少量硬约束反复出现。** 人物大小、人数、栏杆/西式建筑/文字水印等错误要放在末尾 `--no` 或一条 avoid 句里。
- **MJ 参数必须集中在结尾。** `--ar`、`--chaos`、`--raw`、`--stylize`、`--hd`、`--v`、`--profile`、`--seed` 不要夹在句中。
- **MJ 的“华丽”来自尺度和材质，不是堆词。** 先写透视、遮挡、反射、云层体积、建筑比例，再写 cinematic、photorealistic、Unreal/CG 等风格。

## 2. 推荐输出结构

用户指定 MJ / Midjourney / `--ar` / `--v` / `--profile` 时，默认只输出以下四段：

1. `MJ升级思路`：3–5 条，指出如何从当前需求转成 MJ 稳定结构。
2. `Midjourney完整提示词`：一个可直接复制的英文或中英混合 prompt。
3. `可选负面词`：一行 compact negative 或原生 `--no`。
4. `如果还糊`：给一个具体调参建议，不泛泛而谈。

如果用户说“只要 MJ 提示词”，只输出完整提示词和可选负面词。

## 3. MJ Prompt 组装顺序

按这个顺序写，不要平均堆元素：

```text
[画幅与镜头] + [一个核心空间事件] + [主体/人物尺度] +
[前景遮挡或地面] + [中景建筑/奇观] + [远景云海/天体/城市] +
[光线方向] + [色彩预算] + [材质证据] + [风格质量] +
[硬性排除] + [MJ参数]
```

### 开头句公式

```text
16:9 cinematic Chinese xianxia film still, low eye-level 24mm wide lens, [one dominant spatial event], [tiny adult immortal figures under X% of frame] used only for scale, ...
```

竖图可改为：

```text
9:16 vertical cinematic Chinese xianxia establishing shot, ultra-wide low-angle view, [dominant vertical event], [one tiny rear-facing adult immortal under X% of frame], ...
```

## 4. 从上传 MJ 案例提炼出的稳定模块

### A. 极简圆门 / 仙人指路

- 核心事件：从巨大圆形开口或月亮门内看见云海、低太阳、远山宫阙。
- 构图：正面框中框，圆形占画面 60%–90%，人物集中右下三分之一，松枝横穿上右或一侧。
- 色彩：象牙白、淡金、软灰蓝、深松绿，巨大留白。
- 关键词：`monumental circular opening`, `huge negative space`, `tiny robed figures for scale`, `subtle asymmetry`, `no clutter`。

### B. 天宫柱廊 / 长廊 / 云巅

- 核心事件：巨柱、屋檐、台阶或弧形长廊把人压成极小尺度。
- 构图：低机位或平视，一点透视；近处柱体/墙体局部超框；右侧或远方保留云海负空间。
- 材质：白玉、朱红木、暗金浮雕、湿润石面、漆木地板，不写塑料亮面。
- 关键词：`monumental columns receding to vanishing point`, `architecture occupying 60%`, `open cloud sea negative space`。

### C. 水上 / 海阁 / 天河

- 核心事件：低水线看白玉宫池，或高角度俯看蓬莱飞廊和东海。
- 构图：水面占下半部；极小人物在中远景；远处云海、浮岛、亭台被雾切开。
- 反射：`soft broken clarity`, `subtle ripples`, `wet jade`, 避免完美镜像和塑料水。
- 色彩：云白、浅玉、天青、象牙，最多一处珊瑚红衣角。

### D. 宗门 / 雨后桥 / 山林岩盖

- 核心事件：雨后白玉桥、天然石灰岩穹、山体宫台形成可居住仙境。
- 构图：桥或岩盖作为主结构；人物小于 3%；远方宫区、瀑布、飞舟、白鹤只作层次。
- 光线：雨后冷白天光 + 窄暖阳破口；湿石有破碎反射。
- 排除：`flat fog`, `muddy colors`, `railings`, `oversized figures`。

### E. 落霞 / 青鸾 / 空中鸟类

- 核心事件：两侧宫亭夹出开阔云隙，青鸾横飞而过。
- 构图：三分之二以上给天空、云谷和远方亮面；建筑只做两侧框景。
- 生物控制：鸟要“一头一身、两翼、两条收腿、一条连续长尾”，分离且大小有别。
- 排除：不要落在屋脊，不要变多头多翅，不要贴近镜头抢主体。

### F. 火山 / 洪荒能量瀑布

- 核心事件：熔金神性能量瀑布从裂天垂直坠入赤云海，建筑和生物都不出现。
- 构图：远距离压缩长焦，强垂直消失方向；人物小于 0.8% 仅作尺度。
- 色彩：古铜、暗红、焦黑、熔金、白热核心。
- 排除：`No architecture, creatures, or constructed objects` 必须写在前段。

### G. 天梯 / 阶梯 / 竖向奔赴

- 核心事件：白玉阶梯或近乎垂直天梯向星河、云海或古城坠落/上升。
- 构图：要么轴线远景，要么贴背跟拍越肩俯瞰；不能同时要完整城市总览和人物特写。
- 控制：人物背影，阶梯连续，强高空压迫感，星雾或云雾只服务引导线。

### H. 月宫 / 现代城市对照

- 核心事件：仙宫露台上的背影女神俯瞰现代城市或地球弧线。
- 构图：仙界前景与城市远景形成层级对照；月光、城市灯、极光不能互相抢。
- 色彩：冷蓝夜色 + 低饱和金色边缘；避免霓虹赛博感。

### I. 神兽托城 / 东方巨龙 / 玄武 / 鲲城

- 核心事件：神兽本身就是巨构，背负宫殿或穿越云海。
- 构图：神兽占半个天空或画面绝对中心；人物极小；建筑在兽背上必须扎根，不漂浮。
- 材质：鳞片、龟甲、云雾、金瓦、白玉桥各自清晰。
- 排除：西方龙、怪兽攻击、卡通宠物感、人物近景抢主体。

### J. 沙海蓬莱 / 废墟天宫 / 飞天巨门

- 核心事件：沙漠、废墟或超巨城墙中出现悬浮天宫。
- 构图：荒原或云海作大面积负空间；人物 tiny as dust；城墙/天宫如山脉一样延展。
- 光线：金色清晨或柔和逆光；不要科幻光束、荧光粒子。

## 5. 画幅策略

- `--ar 16:9`：默认电影横幅。适合水庭、宗门、长廊、云海、神兽、火山、蓬莱海阁。
- `--ar 9:16`：竖版压迫。适合云宫大门、阶梯俯冲、仙境飞瀑、沙漠天宫、人物背影眺望。
- `--ar 21:9` 或 `--ar 2:1`：超宽建立镜头。适合桥、长廊、两侧宫亭夹云隙、横向飞瀑。
- 画幅不是结尾标签而已。提示词第一句要同步改变构图，例如竖版写“vertical depth / low-angle compression”，横版写“wide negative space / layered horizon”。

## 6. 参数建议

- 写实天宫：`--chaos 5-15 --raw --stylize 180-350 --hd`。
- 极简圣境：`--chaos 4-6 --raw --stylize 180-220`。
- 洪荒/神兽/高能奇观：`--chaos 15-40 --stylize 300-500 --hd`。
- 需要稳定复现：保留用户给的 `--seed`、`--profile`、`--sref`；不要凭空添加未知 profile。
- 如果画面太乱：降低 `--chaos`，把主事件缩成一个，并增加 `minimal elements, no clutter, clean foreground-midground-background separation`。
- 如果建筑西化：在正向写 `strictly oriental Chinese xianxia palace architecture, layered flying eaves and dougong brackets`，在负向写 `--no European palace western dome cathedral fantasy castle`。

## 7. MJ 负面词基线

```text
--no text logo watermark signature neon cyberpunk western castle European palace western dome cathedral sci-fi spaceship anime cartoon plastic water plastic CGI overexposed white buildings muddy colors flat fog oversized figures character close-up extra characters distorted perspective
```

按场景追加：

- 水体：`perfect mirror reflection, swimming pool, aquarium, artificial water`。
- 圆门：`portal glow, ellipse, broken ring, thin flat circle`。
- 神兽：`western dragon, monster attack, cute pet, toy look`。
- 鸟类：`extra heads, extra wings, fused birds, landing on roof`。
- 火山能量瀑布：`buildings, creatures, constructed objects, lava river horizontal flow`。

## 8. MJ 完整示例

```text
16:9 cinematic Chinese xianxia film still, low eye-level 24mm wide lens from beneath a colossal traditional wooden pavilion, a vast white-jade celestial palace terrace floating above an endless cloud ocean, massive carved timber beams and layered glazed tile eaves cropping the top of frame, tall vermilion columns on both sides receding toward one vanishing point, mirror-polished pale jade floor with soft broken reflections, open central vista toward floating karst peaks and gigantic white stone ring-shaped heavenly arches rising through distant clouds, one tiny rear-facing adult immortal in moon-white hanfu under 3% of frame height standing near the terrace edge for scale, ancient windswept pine branch in upper right, warm sunrise side light, golden rim on eaves and figure, cool blue-gray shadows, restrained ivory, pale jade, teal and gold palette, realistic carved wood, weathered bronze, polished stone, translucent silk, volumetric mist, deep atmospheric perspective, serene sacred monumental atmosphere, high-end photorealistic fantasy environment concept art --chaos 6 --ar 16:9 --raw --stylize 220 --hd --no text logo watermark signature neon cyberpunk western castle European palace western dome cathedral plastic water flat fog oversized figures character close-up
```
