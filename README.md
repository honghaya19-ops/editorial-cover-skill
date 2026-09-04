# Editorial Cover Skill

一个用于生成高级杂志封面、社媒主图和电商 editorial 主视觉提示词的 skill。

它会把主题、人物、产品、品牌概念、场景或上传图片，转译成有观点、有视觉隐喻、有真实摄影感、有强 typography 和大面积留白的封面提示词。

## 适合场景

- 杂志封面、社媒封面、作品集封面、品牌主视觉。
- 产品广告、电商高级感主图、护肤/美妆/生活方式视觉。
- 科技、AI、身份、数字生活、社媒平台、消费主义、城市、建筑、旅行等概念型视觉。
- 用户提供人物、产品或场景参考图，希望保留主体锚点并重构封面风格。

## 主要能力

- 从用户输入中提取主题、用途、情绪、标题、副标题、比例、参考图和限制条件。
- 先提炼 editorial concept，再写图片生成 prompt。
- 选择封面配方、版式原型、字体角色和色彩方向。
- 使用历史效果较好的社媒封面图作为审美校准样例。
- 避免廉价促销海报、信息堆满、通用照片加字、霓虹赛博和 Y2K 拼贴，除非用户明确要求。

## 目录结构

```text
editorial-cover-skill/
├── README.md
└── editorial-cover/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   ├── icon.svg
    │   ├── quiet-structures.png
    │   ├── readme-hero.webp
    │   ├── still-morning.png
    │   └── examples/
    │       ├── generational-media.png
    │       ├── synthetic-skin.png
    │       ├── unfinished-architecture.png
    │       └── unboxed-commerce.png
    └── references/
        ├── art-direction.md
        ├── cover-recipes.md
        ├── examples.md
        ├── image-generation.md
        ├── layout.md
        ├── palette-and-range.md
        └── typography.md
```

## 安装方式

把里面真正的 skill 文件夹复制到 Codex skills 目录：

```bash
cp -R editorial-cover ~/.codex/skills/
```

## 使用示例

```text
Use $editorial-cover to turn "digital sabbath" into a premium social-media editorial cover prompt.
```

```text
Use $editorial-cover to create a magazine cover prompt for a skincare product launch, quiet and premium.
```

## 使用建议

- 每张封面只保留一个主要观点和一个核心视觉装置。
- Typography 要成为构图的一部分，不是后贴字幕。
- `assets/examples/` 是审美参考，不是固定模板，不要逐字照搬。
- 发布到 GitHub 前，请确认示例图片资产是你自己生成或有权公开使用的。
