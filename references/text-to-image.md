# Text-only prompt compilation

Use this workflow when the user provides text but no reference image.

## 1. Lock explicit requirements

Treat all user-specified details as immutable unless the user explicitly permits interpretation. Extract:

- image type and intended use
- subject count, apparent age or life stage, body build, appearance, hairstyle, clothing, accessories
- expression, gaze, action, pose, body and shoulder orientation, hand position, held objects
- setting, time, weather, key objects, required or forbidden elements
- aspect ratio, framing, subject placement, negative space
- colour palette, medium, style, texture, rendering treatment
- exact in-image text and typography requirements
- transparent-background or isolation requirements

Do not invent a person's name, profession, ethnicity, biography, or story context unless the image needs it or the user supplied it.

## 2. Complete the visual plan

Fill only missing information necessary for a coherent image:

- visual focal point and hierarchy
- foreground, midground, and background
- left, centre, right, upper, and lower relationships
- camera distance, angle, perspective, and depth of field
- key light, fill, direction, softness, colour temperature, shadow, and highlight behaviour
- scale, contact, occlusion, reflection, and material response
- intentional negative space and cropping

Every added detail must support the original concept. Avoid random props and over-designed environments.

## 3. Build a spatial map

Use concrete anchors when relevant:

- upper left / upper right / across the top / upper third
- left side / left third / centre-left / centre / centre-right / right third / right side
- foreground / midground / background / behind the subject
- lower third / along the bottom edge

For complex scenes, establish enough anchors to remove ambiguity. Do not force every element into the centre.

## 4. Choose the description order

### People, characters, or photographic scenes

Describe in this order when applicable:

1. Image type, orientation, and overall scene
2. Environment and spatial structure
3. Subject placement and scale
4. Pose, action, and body orientation
5. Face, gaze, and expression
6. Hair
7. Clothing and accessories
8. Hands and object interactions
9. Foreground and surrounding objects
10. Lighting and physical effects
11. Camera, framing, perspective, and depth of field
12. Palette, medium, texture, and final visual mood

### Posters, information graphics, social cards, or UI

Describe background, top, left, centre, right, bottom, then typography, materials, light, and overall layout. State the reading order and visual hierarchy.

### Isolated objects or stickers

Describe the subject, silhouette, pose or object angle, internal details, edge treatment, transparency, and crop safety. Exclude environmental elements unless requested.

## 5. Describe concrete visual properties

### People

Prioritise visible traits:

- apparent age or life stage
- body build and proportions
- pose and body orientation
- gaze and expression
- hairstyle
- clothing colour, cut, and material
- accessories
- interaction with objects

### Objects

Name objects precisely. When useful, state count, size, orientation, material, surface finish, condition, transparency, distance from the subject, and front/behind relationship. Avoid `various objects`, `some decorations`, and `miscellaneous items`.

### Colour

Use specific colour descriptions such as `deep navy`, `muted blue-grey`, `warm cream`, `dusty rose`, `soft olive`, `charcoal grey`, `warm terracotta`, or `pale beige`. Preserve any supplied HEX or RGB value exactly.

### Material

Use material terms that change light behaviour, such as `matte plastic`, `glossy ceramic`, `brushed metal`, `frosted glass`, `weathered wood`, `coarse linen`, `soft leather`, `rough paper`, or `polished stone`.

### Lighting

Specify source, direction, softness, colour temperature, and resulting shadows/highlights. Example: `Soft diffused daylight enters from the left, creating gentle highlights along the subject's face and subtle shadows across the tabletop.` Avoid `cinematic lighting` or `beautiful lighting` without physical detail.

### Camera and composition

Use only terms that matter: `close-up`, `medium shot`, `medium-wide shot`, `full-body`, `eye-level`, `low angle`, `high angle`, `three-quarter view`, `shallow depth of field`, `deep focus`, `foreground separation`, `negative space`, or `soft background bokeh`. Do not add camera brands unless requested.

## 6. Handle text and transparency

If text must appear:

- preserve it character-for-character
- do not translate, rewrite, summarise, spell-correct, or add a subtitle
- enclose it in straight double quotation marks
- specify position, scale, weight, colour, alignment, and relationship to the subject

If transparent background, cutout, LINE sticker, sticker, isolated asset, or RGBA is requested, include:

`RGBA image with a fully transparent background and alpha channel.`

Do not add a white or black backdrop, wall, floor, environment, or shadow outside the isolated asset unless requested.

## 7. Scale prompt length to complexity

- simple isolated subject: about 100–180 English words
- one person or ordinary scene: about 180–280 words
- complex scene: about 250–400 words
- multi-person scene, poster, information graphic, or dense specified layout: about 350–550 words

Treat these as ranges, not quotas. Prefer complete and non-redundant over long.

## 8. Validate before output

Check subject count, identity-independent appearance, action, pose, hands, objects, placement, left/right, environment, text accuracy, ratio, physical consistency, forbidden elements, and contradictions. Then return only the output required by `SKILL.md`.

