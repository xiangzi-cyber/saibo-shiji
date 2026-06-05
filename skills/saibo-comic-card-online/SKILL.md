---
name: saibo-comic-card-online
description: Use when turning Saibo Shiji four-panel comics into online website cards, adding or polishing comic cards in index.html, creating web cover assets, writing episode summaries, checking online image quality, or applying the comic-to-card SOP. Excludes A5/PDF print export unless the user explicitly asks for print.
metadata:
  short-description: Build Saibo Shiji online comic cards
---

# Saibo Shiji Online Comic Cards

Use this skill to convert a finished four-panel comic into a web-facing card for the Saibo Shiji site.

## Scope

Do:

- Update online comic cards in `index.html`.
- Maintain web assets under `comics/` and `comics/covers/`.
- Write concise episode summaries from user story prompts.
- Preserve the original four-panel comic as the authoritative artwork.
- Validate web loading, readability, color fidelity, and watermark removal.

Do not:

- Export PDFs or modify A5 print output unless explicitly requested.
- Regenerate the comic itself when the user already provided the finished image.
- Bake title/date/story/signature text into generated background images.
- Replace original comic files with lower-resolution cover crops.
- Put essential Chinese text inside generated images; keep text in HTML, Markdown, or SVG.

For the full project SOP and diagrams, read `docs/comic-card-online-sop.md` when working inside this repository. For GPT image-model illustration prompts, read `docs/comic-card-online-sop/gpt-image-briefs.md`.

## Artifact Map

- Website entry: `index.html`
- Site styles: `style.css`
- Full comic images: `comics/epXX_comic.jpg`
- Web cover images: `comics/covers/epXX_cover.jpg`
- Lightbox source: `openLightbox('comics/epXX_comic.jpg')`

## Workflow

### 1. Intake

Collect:

- Finished comic image.
- Episode number and title.
- Creation date.
- User prompt, story notes, or emotional intent.

Convert rough notes into three working lines:

- What happened?
- What emotion should the card carry?
- What should readers remember?

### 2. Distill Card DNA

Before editing HTML, define:

- Story core: one plain sentence.
- Mood: 2-5 words.
- Visual anchors: 3-5 concrete objects/scenes from the comic.
- Point sentence: the remembered line or emotional turn.
- Series role: newest issue, origin issue, holiday issue, transition issue, etc.

This prevents generic descriptions and random decoration.

### 3. Prepare Images

Use the user-provided full comic as source of truth.

Rules:

- Full image goes to `comics/epXX_comic.jpg`.
- Cover goes to `comics/covers/epXX_cover.jpg`.
- Cover should be around `640 x 640` when practical.
- Cover may crop for grid readability; full image must remain uncropped.
- Do not alter hue/saturation unless the user asks.
- Do not recompress repeatedly from already compressed previews.
- Check corners for watermarks before declaring success.

### 4. Update Card HTML

Add or update one `article.comic-card` in `.comic-grid`.

Required fields:

- `openLightbox('comics/epXX_comic.jpg')`
- Cover `img src="comics/covers/epXX_cover.jpg"`
- `alt="赛博史记第XX期"`
- `date-badge`
- `episode-badge`
- `card-title`
- `card-desc`
- View button

Newest issue normally appears first. Give only the first visible card `loading="eager"` and `fetchpriority="high"`; use lazy loading for the rest.

### 5. Write Summary Copy

Summary style:

- 45-90 Chinese characters.
- First describe the visible event.
- Then name the emotional or conceptual turn.
- Keep creator voice warm, specific, and lightly humorous when the episode supports it.
- Do not dump the full prompt into the card.

Good pattern:

```text
猫咪大老板窝在 AGI Bar 茶杯里，机器人秘书端来发光鸡尾酒。额度会重置，快乐不重置，愿你永远有心中的游乐园。
```

### 6. Validate Online Behavior

Use browser verification for meaningful changes.

Check:

- Card grid renders.
- Cover appears and is not blurry.
- Cover and button open the full comic.
- Full comic is not cropped.
- Text fits desktop and mobile.
- No old watermarked/cached image remains.
- Colors match the supplied source closely enough that the user would recognize the image.

When color looks wrong, compare current full image against the original user source or the pre-edit asset before changing CSS.

### 7. Commit and Push

Stage only relevant web/SOP files. Avoid accidental temporary artifacts such as PDFs, QA screenshots, `.DS_Store`, and browser cache directories.

Before push:

- Run `git status --short`.
- Confirm the diff does not include unrelated user work.
- Commit with a message that names the card/SOP update.
- Push `main` when the user has asked for direct publication.

## Quality Bar

A card update is done only when:

- The original comic remains intact.
- The cover is clean, fast, and recognizable.
- The card explains the story without over-explaining.
- The online page works on desktop and mobile.
- No print/PDF-only work is mixed into the online flow.
