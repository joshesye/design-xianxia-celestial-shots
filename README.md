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
