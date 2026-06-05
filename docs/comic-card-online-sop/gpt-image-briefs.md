# GPT 生图配图 Brief

这些 prompt 用于给《赛博史记线上卡片化 SOP》和 `saibo-comic-card-online` Skill 生成配图。配图只承担“概念与气质表达”，不要把关键中文、字段名、步骤说明交给模型生成；文字由 Markdown/SVG/HTML 承载。

## 通用约束

- 画面不出现可读文字、中文、英文、Logo、水印。
- 不直接复制任何一期漫画，不改变猫咪 IP 的具体原作形象。
- 画面要像“创作者工作流说明图”的封面插画，而不是单纯装饰背景。
- 色彩明亮、清晰、温暖，不压暗、不灰化。
- 构图保留足够呼吸感，便于文档中作为横幅或章节配图。

## 01 总流程配图

```text
Use case: infographic-diagram
Asset type: SOP hero illustration for a workflow skill
Primary request: Create a polished horizontal editorial illustration showing the transformation from a finished four-panel comic into an online collectible website card.
Scene/backdrop: A warm creator desk with a laptop showing a clean comic card grid, a finished four-panel comic sheet, small cover thumbnails, sticky notes, a color palette strip, and a browser lightbox preview.
Subject: The process of turning a comic into a web card, represented visually with arrows, thumbnail frames, folders, and clean UI panels.
Style/medium: refined digital illustration, soft 3D-paper-craft mixed with editorial design, premium creative tool documentation style.
Composition/framing: horizontal 16:9, left-to-right workflow, spacious, clear focal path, no crowded text.
Lighting/mood: warm studio light, optimistic, thoughtful, creative.
Color palette: cream paper, soft gold, gentle teal, coral pink, ink brown, clean white UI panels.
Constraints: no readable text, no Chinese characters, no English words, no logos, no watermark. Use abstract blocks and icons instead of text labels.
Avoid: dark cyberpunk look, blurry tiny text, fake UI letters, dirty texture, over-saturated neon.
```

## 02 卡片骨架配图

```text
Use case: infographic-diagram
Asset type: explanatory illustration for online comic card anatomy
Primary request: Create a beautiful conceptual diagram of a web comic card made from modular layers.
Scene/backdrop: One central vertical website card floating above a soft paper background; around it are separated translucent layers for cover image, metadata chips, title area, short story summary area, and full-image button.
Subject: The idea that an online card is a stable structure plus episode-specific mood.
Style/medium: elegant UI illustration, clean editorial product-design diagram, soft shadows, subtle paper and glass layers.
Composition/framing: horizontal 16:9, central card with surrounding modular pieces, balanced margins.
Lighting/mood: calm, precise, design-system thinking, friendly.
Color palette: warm cream, midnight blue card, golden highlights, soft aqua, muted rose.
Constraints: no readable text, no Chinese characters, no English words, no logos, no watermark. UI fields should be blank or represented by simple lines.
Avoid: complex charts, tiny unreadable letters, harsh gradients, generic SaaS dashboard.
```

## 03 质量闸门配图

```text
Use case: infographic-diagram
Asset type: quality checklist illustration for an online publishing SOP
Primary request: Create a polished illustration of four quality gates for publishing an online comic card: story accuracy, visual readability, clean assets, stable release.
Scene/backdrop: Four warm paper checkpoint stations connected by a gentle path; each station uses abstract symbols such as a story spark, magnifying glass, clean image tile, and upload cloud.
Subject: A final QA process that protects color fidelity, no-watermark assets, readable text, and clickable full comic.
Style/medium: charming editorial infographic illustration, soft paper cutout, gentle shadows, clean design documentation aesthetic.
Composition/framing: horizontal 16:9, four checkpoints in a row, strong clarity without text labels.
Lighting/mood: reassuring, careful, completion-focused.
Color palette: cream, soft gold, teal, clay orange, warm brown, small coral accents.
Constraints: no readable text, no Chinese characters, no English words, no logos, no watermark. Use icons and abstract shapes only.
Avoid: warning-heavy red alarm style, dark mood, fake tiny text, clutter, low contrast.
```

