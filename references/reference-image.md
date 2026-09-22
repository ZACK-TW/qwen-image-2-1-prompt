# Reference-image prompt compilation

Use this workflow when the user provides one or more images or asks to edit an image.

## 1. Inspect and assign reference roles

Inspect every uploaded image. Represent them in upload order as `<image1>`, `<image2>`, `<image3>`, and so on. Assign one or more explicit roles:

- Identity Reference: facial identity and recognisable appearance
- Character Reference: fixed IP design, silhouette, proportions, palette, costume, markings, or signature accessories
- Style Reference: palette, line quality, brushwork, rendering, material treatment, texture, lighting language, or visual density
- Clothing Reference: garment, footwear, and accessory design
- Pose Reference: posture, gesture, body orientation, and limb placement
- Composition Reference: framing, placement, negative space, camera relationship, and layout
- Environment Reference: architecture, furniture, spatial layout, and background objects
- Object / Product Reference: product form, packaging, surface, logo, or object identity
- Base Canvas: image whose framing and spatial structure are directly edited
- Multi-Reference Composition: distinct elements drawn from different images

Never use vague phrases such as `the references`, `the images above`, or `the uploaded photos` when images provide different information.

Examples:

- `Use <image1> as the primary identity reference for the woman.`
- `Use <image2> as the clothing and accessory reference.`
- `Use <image3> only as a lighting and colour reference; do not copy its people or composition.`
- `Use <image1> as the base canvas and preserve its framing and spatial structure.`

## 2. Set priority and boundaries

Apply this priority order:

1. The user's latest, clearest text instruction
2. The role explicitly assigned by the user to a reference image
3. Identity or character consistency
4. Composition and pose
5. Environment and objects
6. Lighting and colour
7. Style

Define internally:

- TARGET: features to add, remove, replace, or redesign
- LOCKED: features that must not drift

Common locked features include facial identity, facial structure, hairstyle, apparent age, skin tone, body build, character proportions, silhouette, eye and mouth design, signature clothing, signature accessories, markings, logo, product shape, and IP-specific palette.

Only modify what the user requests. Do not beautify a person, alter the face, change age, remove accessories, redesign clothing, or change proportions as collateral effects.

## 3. Prevent reference leakage

Each image contributes only the information assigned to it.

- If `<image2>` supplies pose, do not copy its face, hair, clothing, background, camera, or colour grade.
- If `<image3>` supplies clothing, do not copy its person, identity, pose, scene, or framing.
- If an image supplies style, extract only palette, rendering method, brushwork, line quality, lighting language, material treatment, texture, visual density, and graphic hierarchy. Do not copy its subject or composition.
- If an image supplies environment, preserve relevant architecture, furniture, layout, palette, and major objects without importing unrelated people.

When references conflict, select one coherent lighting and camera system based on user intent or the base canvas. Do not merge incompatible light directions.

## 4. Preserve identity and character correctly

For a real person's identity, avoid re-describing detailed facial geometry unless it is the target of the edit. Prefer:

- `Maintain the same facial identity and recognisable appearance as <image1>.`
- `Preserve the subject's facial identity from <image1>.`
- `Identity should remain clearly recognisable as the person shown in <image1>.`

For a fixed character or IP, lock head shape, body proportions, silhouette, facial design, eye design, mouth design, signature clothing, accessories, markings, and palette. A new expression, action, prop, or background must not redesign the character.

## 5. Build the new scene

Unless the task is a conservative edit to a base canvas, construct the requested new image fully:

- environment
- foreground, midground, and background
- subject placement and scale
- pose and interaction
- spatial anchors and negative space
- camera distance, angle, framing, and depth
- key, fill, shadow, reflection, rim light, and colour temperature
- visual hierarchy and style

For a base-canvas edit, state what remains unchanged and localise the edit. Do not unnecessarily regenerate unrelated areas.

## 6. Specify pose, clothing, composition, and environment

### Pose

State torso direction, shoulder angle, head angle, gaze, hand position, arm position, seated or standing posture, weight distribution, and object interaction when relevant.

Use: `Use the body pose and arm position from <image2> while retaining the identity from <image1>.`

If the user specifies a new pose, the text instruction overrides the reference pose.

### Clothing

State: `Use the clothing design, colour, material and accessory arrangement shown in <image2>.`

For a partial change: `Keep the original clothing design from <image2>, but change the jacket colour to charcoal grey.` Do not redesign the rest.

### Composition

Translate layout requests into measurable spatial relationships. Example: `The subject stands on the centre-right side of the vertical frame, occupying approximately the right 45 percent of the image, while the left third remains visually open.`

Use anchors such as left third, centre-left, centre, centre-right, right third, foreground, midground, background, upper third, lower third, top edge, and bottom edge.

### Environment

When placing a referenced person or object into a new environment, match ground level, perspective, spatial scale, contact shadows, reflections, lighting direction, depth of field, and occlusion so all elements belong to the same scene.

## 7. Handle text and transparent assets

If text must appear:

- preserve it character-for-character and keep its original language
- enclose it in straight double quotation marks
- do not translate, shorten, rewrite, correct, or add secondary copy
- specify position, size, weight, colour, and alignment

If transparent background, cutout, LINE sticker, sticker, isolated asset, or RGBA is requested, include:

`RGBA image with a fully transparent background and alpha channel.`

Do not introduce a background, wall, floor, environment, or external drop shadow unless requested.

## 8. Compile the final prompt

Use this order when applicable:

1. Reference roles
2. Completed scene and image type
3. Subject and identity/character preservation
4. Pose and action
5. Clothing and accessories
6. Environment and objects
7. Spatial composition
8. Lighting and physical integration
9. Camera and depth of field
10. Style, palette, and texture
11. One concise preservation clause

The prompt may include direct reference instructions, then should describe the completed image coherently. End with a concise clause such as:

`Preserve the facial identity from <image1>, the clothing design from <image2>, and all explicitly specified character features without alteration.`

Avoid repeating the full prompt in the preservation clause.

## 9. Validate before output

Confirm that:

- every actual image has a clear role
- identity, clothing, pose, composition, environment, object, and style sources are unambiguous
- unrelated reference content has not leaked across roles
- locked features are preserved and target changes are prominent
- subject count, hands, contact, scale, perspective, occlusion, lighting, shadows, reflections, and depth are coherent
- exact text, aspect ratio, placement, and left/right direction match the request
- no unintended feature drift or contradictory instruction remains

Then return only the output required by `SKILL.md`.

