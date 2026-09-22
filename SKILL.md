---
name: qwen-image-2-1-prompt
description: Convert a basic visual concept into a production-ready English prompt for Qwen Image 2.1 through visual planning and prompt compilation. Use when the user asks to write, rewrite, enhance, optimize, or compile a Qwen Image 2.1 prompt from (1) text only or (2) text plus one or more reference images, including identity, character/IP, clothing, pose, composition, environment, object/product, style, image-edit, poster, sticker, transparent-background, or multi-reference tasks.
---

# Qwen Image 2.1 Prompt

Turn sparse user intent into an explicit visual specification that Qwen Image 2.1 can execute. Plan the image before writing the final prompt. Preserve all explicit user constraints and avoid decorative detail that does not serve the concept.

## Route the task

1. If the user provides no reference image, read and follow [references/text-to-image.md](references/text-to-image.md).
2. If the user provides one or more reference images, read and follow [references/reference-image.md](references/reference-image.md).
3. If the task benefits from photographic, cinematic, narrative, lighting, or series-continuity decisions, also read [references/cinematography-language.md](references/cinematography-language.md). Skip it for flat graphics, UI, diagrams, and simple transparent stickers unless the user requests a photographic or cinematic treatment.
4. If the user names a camera or lens, asks for a cinematic/film/vintage optical look, or the planned photographic scene would materially benefit from a defined capture character, also read [references/camera-and-lens-looks.md](references/camera-and-lens-looks.md).
5. Treat a request to edit an uploaded image as the reference-image route.
6. Do not generate an image unless the user explicitly asks for image generation in addition to prompt writing.

## Compile in two stages

Perform these stages internally; do not expose chain-of-thought or intermediate reasoning.

### Stage 1: Visual planning

- Extract hard constraints: subject count, identity, character design, age/life stage, appearance, clothing, expression, action, pose, held objects, setting, time, weather, aspect ratio, spatial placement, colour, style, required text, forbidden elements, and preservation requirements.
- Resolve the scene: purpose, focal subject, visual hierarchy, foreground/midground/background, left/centre/right and top/bottom relationships, scale, perspective, occlusion, materials, lighting, camera, depth of field, and negative space.
- For reference images, assign each image a single or combined role and define what may change versus what must remain locked.
- Prefer the user's latest and most explicit instruction when constraints conflict.
- Ask one concise question only if a missing or contradictory fact would materially change the result. Otherwise make a reasonable visual decision.

### Stage 2: Prompt compilation

- Write the final prompt as a coherent description of the completed image, not a list of vague commands.
- Use precise, natural English for the image prompt. Keep any required in-image text in its original language and enclose it in straight double quotation marks.
- Use concrete spatial anchors and physical relationships.
- Include only camera, lighting, colour, material, texture, and rendering details that visibly affect the result.
- Avoid empty quality tags such as `masterpiece`, `best quality`, `8K`, `ultra detailed`, `award-winning`, and `high quality`.
- Avoid command filler such as `Create`, `Generate`, `Make`, `Please`, `Ensure`, and `The AI should`.
- Do not invent logos, watermarks, captions, signs, names, professions, ethnicities, backstories, or branded elements unless requested or visually necessary.
- Do not add a negative prompt section unless the user asks for one.

## Shared invariants

- Preserve every explicit hard constraint without translation, softening, or reinterpretation.
- Maintain the requested subject count, left/right placement, body orientation, hand-object contact, and aspect ratio.
- Keep lighting direction, shadows, reflections, perspective, scale, ground contact, and occlusion physically coherent.
- If text must appear in the image, preserve it character-for-character and specify its position, size, weight, colour, and alignment.
- If no text is requested, explicitly prevent unintended text only when the scene is likely to introduce it; otherwise simply omit textual elements.
- For transparent assets, specify `RGBA image with a fully transparent background and alpha channel` and do not introduce a wall, floor, environment, or external drop shadow.
- Use the reference image's aspect ratio only when no ratio is supplied and its composition is meant to be preserved. Otherwise choose a ratio appropriate to the stated use.

## Output contract

Do not explain the analysis or add usage advice. Do not place the final prompt in a code fence.

For text-only tasks, output exactly:

```text
【Qwen Image 2.1 Prompt】

<complete English prompt>

【Aspect Ratio】

<ratio>
```

For tasks with reference images, output exactly:

```text
【Reference Roles】

<image1>: <role>
<image2>: <role>

【Qwen Image 2.1 Prompt】

<complete English prompt>

【Aspect Ratio】

<ratio>
```

List only images that actually exist. Use `<image1>`, `<image2>`, and so on in upload order. Keep role labels concise and in English.
