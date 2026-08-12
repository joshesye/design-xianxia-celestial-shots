# 仙侠天宫远景运镜

## 项目简介

`design-xianxia-celestial-shots` 是一个面向仙侠、天宫、云海神殿、浮空宫殿等宏大远景的 Codex Skill。它能够从参考图或文字描述中提取构图骨架、空间层次和镜头语言，生成可复用、可修改的图片提示词，并可按需扩展为短视频运镜方案。

## 核心能力

- **拆解参考图构图**：识别画幅、机位、景别、焦段、消失点、主体位置、遮挡关系和光线方向。
- **固定骨架与变量分离**：锁定不应变化的空间关系，把人物、服装、建筑、奇观、环境、光线和情绪整理为可替换属性。
- **16 种构图原型**：覆盖柱廊、天阶、崖边、飞瀑、水庭、悬台、圆月门、云海廊桥、透明锦鲤台等典型场景。
- **完整提示词控制**：同时提供通用模板、完整案例、负面提示词和构图锁定句。
- **人数与队形约束**：支持单人、双人、小群像和 50 人以上大队列的空间组织。
- **可选视频运镜**：在静帧构图成立后，追加缓推、侧移、跟拍、揭示或轻微升降等单一主运动。

## 支持的典型场景

| 编号 | 构图原型 | 编号 | 构图原型 |
|---|---|---|---|
| A | 柱廊独行 | I | 弧形柱廊独行 |
| B | 斜阶群像 | J | 月夜轴线栈道 |
| C | 崖边眺望 | K | 露台三人关系戏 |
| D | 瀑布奇观 | L | 圆月门群像框景 |
| E | S 形水庭 | M | 云海廊桥大队列 |
| F | 悬台终章 | N | 透明锦鲤悬台群像 |
| G | 瀑边横廊独行 | O | 对称圆拱双人对弈 |
| H | 中央云阶双人 | P | 飞瀑天宫双人对峙 |

每种原型的机位、焦段、主体位置、引导线和运镜建议见 [构图原型参考](references/composition-archetypes.md)。

## 安装方法

将仓库克隆到 Codex 的 Skills 目录：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/joshesye/design-xianxia-celestial-shots.git ~/.codex/skills/design-xianxia-celestial-shots
```

安装完成后，在下一轮对话中调用该 Skill。

## 使用示例

### 分析参考图

```text
使用 $design-xianxia-celestial-shots 分析这张参考图，拆解固定构图骨架和可替换属性，并生成完整图片提示词。
```

### 根据文字设计场景

```text
使用 $design-xianxia-celestial-shots 设计一个月夜云海天宫场景：两名成年剑修站在中央栈道尽头，远处巨月位于宫殿之后。
```

### 追加视频运镜

```text
使用 $design-xianxia-celestial-shots 将这个天宫远景扩展为 10 秒一镜到底运镜，保持人物位置、建筑轴线和地平线稳定。
```

## 输出内容

默认按以下顺序交付：

1. 核心构图公式
2. 固定构图骨架表
3. 可替换属性
4. 带变量的通用提示词
5. 完整提示词案例
6. 负面提示词
7. 构图锁定句
8. 可选的 5–15 秒运镜模块

详细模板与控制词见 [输出规范](references/output-contract.md)。

##完整案例

01｜中央云阶·三仙女望天门

一幅宏大的东方仙侠天宫电影大全景。浩瀚云海之上，一条极其宽阔的白玉天阶从画面底部展开，沿唯一中央轴线不断向上收束，通往画面顶部中央一座悬浮于云端的巨型南天门。天门由汉白玉、暗金飞檐、通天巨柱和云龙浮雕构成，规模远超人物，局部建筑超出画框；天门之后隐约显现层叠天宫、悬浮楼阁与垂落云瀑。

正好三名成年仙女位于天阶中远段，集中在画面下方中央，完整背影，共同抬头凝望天门。三人分别穿月白、淡青和浅金色广袖仙裙，前后错开，其中月白仙女领先半步；单个人物高度仅占画面3%–5%，不表现面部，只通过服色、轮廓和飘动衣摆辨认人物。风从左侧吹向右侧，长袖与披帛沿同一方向轻柔飘动。

16:9电影横幅，65mm镜头，轻微高机位，大远景，严格单点透视，f/8深景深。天阶、栏杆、石缝、三名仙女、天门入口与远方主殿完全共轴。建筑、天阶和云海占画面95%以上。清晨暖金阳光从左上方穿透云层，为天门、栏杆与人物轮廓形成柔和逆光；阴影保持冷青灰，真实云海体积、空气透视、电影颗粒。

extreme wide establishing shot, tiny distant adult female figures, people as scale reference only, architecture-dominant composition, monumental celestial gate, deep depth of field, photorealistic Chinese xianxia film still, no prominent character, no portrait framing, 16:9.

02｜悬崖松台·独立仙女望金门

一幅庄严而孤寂的东方仙侠电影大远景。画面左侧是局部超出画框的深色悬崖和一棵枝干虬结的千年古松，粗壮松枝从左上方伸向中央，形成天然框景。一座狭长的白玉悬空平台从悬崖向画面中央延伸，下方完全悬浮于翻涌云海之上。

正好一名成年白衣仙女静立在悬台远端，完全背对镜头，双手自然垂落，仰望对面垂直巨峰中的恢宏天门。人物位于画面下方偏左，高度约占画面4%，只作尺度参照，无其他人物。她身穿层叠月白广袖仙裙，衣摆与披帛被右侧来风轻轻吹向左后方，不回头、不露正脸。

远方天门占据画面中央偏右，由暗红巨柱、鎏金重檐、白玉门壁和巨幅山河浮雕组成，占画面高度约55%；门内流动着克制的暖金天光，门楼两侧各有一道瀑布从天宫边缘连续坠入云海。外围宫殿沿垂直山壁层层向后升高，重复飞檐与巨柱逐渐隐入雾中。

16:9，70mm长焦大远景，平视至轻微高机位，f/8深景深。古松、悬台、仙女、巨门和云海形成明确的前中后景层次。建筑、云海与悬崖占画面96%，人物不得放大。暖金门光与冷青灰山壁形成冷暖对比，真实石材、木构、瀑布重力、体积雾与空气透视。

extreme wide establishing shot, one tiny distant adult fairy seen from behind, people as scale reference only, monumental architecture, architecture-dominant composition, photorealistic, no portrait framing, 16:9.



## 项目结构

```text
.
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── icon.svg
└── references/
    ├── composition-archetypes.md
    ├── latest-scene-cases.md
    └── output-contract.md
```

- [SKILL.md](SKILL.md)：主工作流程、视觉规则、镜头选择与输出要求。
- [composition-archetypes.md](references/composition-archetypes.md)：16 种构图原型及系列统一规则。
- [latest-scene-cases.md](references/latest-scene-cases.md)：M–P 原型的完整场景案例。
- [output-contract.md](references/output-contract.md)：提示词、负面词、构图锁定句与运镜模板。

## 注意事项

- 默认使用平台中立的提示词；只有用户指定生成模型时，才加入模型专属参数。
- 静态图片任务不添加时间轴或镜头移动；只有视频任务才追加运镜模块。
- 默认排除文字、字幕、水印和 Logo。
- 人物默认设定为成年人，并保持自然比例、完整服装和克制姿态。
- 不引用在世艺术家的风格，使用电影摄影、材质、光线和色彩语言描述视觉效果。
