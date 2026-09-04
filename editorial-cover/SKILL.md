---
name: editorial-cover
description: Create refined editorial magazine covers, social-media cover images, and premium e-commerce editorial posters from a topic, person, product, brand idea, scene, or uploaded image. Use for concept-driven covers, lifestyle editorials, portraits, architecture, fashion, product visuals, social issues, travel, tech, beauty, and abstract ideas that need strong typography, real photography, visual metaphor, and negative space. Avoid dense news covers, low-end promo posters, neon cyberpunk, Y2K collage, and generic photo-with-text unless explicitly requested.
---

# Editorial Cover · 编辑封面

把用户的主题、人物、场景、产品或品牌概念，转译成一张有观点、有视觉隐喻、有真实摄影感、有强 typography 和大面积留白的编辑封面或社媒主视觉。

核心方向：**Western Editorial × Concept Photography × Typography × Quiet Minimalism**。

## 核心合同

- 先做艺术指导，再写生成提示词。不要直接堆叠“高级、欧美、杂志感、电影感”等风格词。
- 一张封面只保留一个主要观点和一个核心视觉装置。不要同时塞入多个创意点。
- 默认生成概念型杂志封面、社媒封面或高级电商 editorial 主视觉，不生成信息密集型传统杂志封面。
- 画面必须有留白、呼吸感和清晰阅读顺序。不要把主体、标题、装饰全部塞满画面。
- 标题、主体、产品、环境之间必须产生视觉关系：遮挡、共边、贴近、穿插、共享轴线或负形咬合。避免“标题一块、主体一块、副标题一块”的两座孤岛。
- 摄影质感优先真实、自然、克制。避免廉价 CG 感、塑料皮肤、过度磨皮、模板化 AI 海报感。
- Typography 是构图的一部分，不是后贴字幕。字体选择必须服务主题情绪。
- 用户上传人物或产品照片时，保留身份锚点和主体真实感；可重构环境、光线、留白和图文关系。
- 只生成用户要求的数量。生成后读图一次，指出最明显的问题，不自动重生成；用户反馈后再定向修改。

## 输入提取

从用户消息中提取：

- Topic：主题 / 产品 / 人物 / 场景
- Intent：杂志封面、产品广告、品牌视觉、社媒主图或个人作品封面
- Mood：默认安静、克制、松弛、有思考感
- Text：标题、副标题；如果用户未给出，可自动生成短标题和一句 tagline
- Image：用户是否上传了人物、产品或场景照片
- Ratio：默认 3:4 竖版；用户指定时遵循指定比例
- Constraints：必须保留、必须避免、品牌调性、文案语言

信息足够时直接执行；只有缺少必要主体或文案会导致误解时才提问。

## 工作流

### 1. 提炼 Editorial Concept

先把用户主题转成一句有观点的封面命题。格式：

```text
主题：用户输入
观点：这张封面真正想表达什么
视觉隐喻：用什么画面动作承载观点
情绪：安静 / 克制 / 疏离 / 温柔 / 坚定 / 希望 / 摩擦等
```

示例：

```text
主题：城市更新
观点：进步与旧世界之间的摩擦
视觉隐喻：新建筑和旧街区在同一空间里发生压迫关系
情绪：冷静、张力、克制
```

### 2. 选择 Cover Recipe

根据主题选择一个主 Recipe，不混用太多方向。详见 `references/cover-recipes.md`。

默认优先级：

1. Quiet Lifestyle Portrait：生活方式、人像、独处、慢生活
2. Architectural Solitude：建筑、空间、城市、结构
3. Minimal Product Editorial：电商广告、产品主视觉、品牌概念
4. Social Issue Editorial：环保、城市、社会议题
5. Futurist Beauty / Tech：科技、身份、身体、未来
6. Motion / Drift：运动、速度、变化、流动
7. Social Platform Editorial：社媒、平台、代际、信息流、数字生活
8. Beauty / Wellness Cover：美妆、护肤、身体照护、柔和商业视觉

### 3. 设计 Layout

选择一个清晰的版式原型：

- Top Giant Title：超大标题占上方，主体进入标题下沿或侧边
- Negative Space Cover：大面积留白，标题进入空区
- Portrait + Type Lockup：人像主体和标题形成贴近、压叠或错位
- Product Still Life：产品居中或偏置，标题与产品轮廓发生关系
- Architecture Frame：建筑结构作为文字和人物的框架
- Motion Field：运动轨迹或光影成为主体周围的视觉场

具体规则见 `references/layout.md`。

### 4. 选择 Typography

根据主题选择字体角色，不要机械规定“全用衬线体”。

- Editorial Serif：时尚、文化、生活方式、安静、高级
- Bold Sans：运动、城市、社会议题、力量、直接
- Thin / Futurist Sans：科技、未来、实验、身体编码
- Italic / Script：诗意、私人情绪、柔软、旁白感

常用组合：

```text
Large Editorial Serif + Small Clean Sans
Bold Sans Headline + Serif / Italic Tagline
Thin Futurist Title + Clean Sans Subtitle
```

细则见 `references/typography.md`。

### 5. 选择色彩与题材边界

不要让所有作品都落入同一套奶油、灰、棕、女性人像、大 serif 标题。根据主题从 `references/palette-and-range.md` 选择色彩和题材边界。

### 6. 生成提示词

最终提示词只表达一个艺术方向，结构为：

```text
Create a vertical editorial magazine cover / premium e-commerce editorial poster...
Concept...
Visual device...
Subject and environment...
Layout and typography...
Text-image interaction...
Photography, light, color, mood...
Avoid...
```

不要输出长篇规则清单给图像模型。把门控规则内化为一段清晰、可执行的艺术指导。

### 7. 读图检查

生成后检查 5 点：

- 观点是否能被看见
- 是否只有一个核心视觉装置
- 留白是否足够
- 字体是否高级且可读
- 标题、主体、环境是否发生关系

只指出 0–3 个最明显问题。不要自动重生成。

## 默认视觉参数

- Ratio：3:4 vertical cover
- Style：contemporary Western editorial, independent magazine, lifestyle/fashion supplement
- Photography：realistic editorial photography, cinematic natural light, subtle film grain
- Color：根据主题选择，不固定为奶油色或暖灰；可用 quiet neutral、cool technology、high-contrast social issue、warm lifestyle、clean beauty 等不同方向
- Mood：quiet, calm, restrained, contemplative, poetic, intimate
- Text density：one headline + one short tagline by default

## 示例资产

`assets/examples/` 中放了历史效果较好的社媒封面样例，用来校准审美边界。需要判断风格时读 `references/examples.md`，不要把示例逐字复制成新 prompt。

## 反向约束

默认避免：

- dense cover lines, barcode, issue clutter
- low-end sales poster, red discount banner, noisy e-commerce layout
- neon cyberpunk, Y2K collage, sticker overload
- generic AI fashion poster, plastic skin, over-polished render
- random font mixing, cartoon fonts, default boring fonts
- title and subject separated with no relationship
- too many visual devices competing in one cover
