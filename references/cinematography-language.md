# Cinematography language for still-image prompts

Use this reference to turn narrative intent into visible photographic decisions. Select a small, coherent set of choices. Do not stack every cinematic term into one prompt.

## 1. Start with narrative function

Decide what the frame must accomplish before choosing a camera term:

- establish place, scale, or isolation
- reveal a relationship between people or objects
- show a person's action or state
- direct attention to a clue or detail
- create intimacy, distance, tension, instability, awe, surveillance, or documentary realism
- preserve directional continuity across a series

Apply `show, don't tell`: express emotion and relationships through visible pose, distance, gaze, blocking, light, environment, and objects. Avoid abstract labels when a physical cue can show the same idea.

Every major element should serve at least one function: establish space, advance an event, reveal character, imply psychology, or supply information.

## 2. Choose one primary shot size

| Shot size | Prompt term | Visible use |
| --- | --- | --- |
| Extreme long shot | `extreme long shot (EWS)` | Environment dominates; subject appears small; useful for scale, isolation, or world-building. |
| Wide shot | `wide shot (WS)` | Shows setting and subject relationship clearly. |
| Full shot | `full shot (FS)` | Frames the complete body with head and feet visible; useful for pose and silhouette. |
| Medium long shot | `medium long shot (MLS)` or `three-quarter shot` | Usually frames from knees or mid-thigh upward; balances body language and context. |
| Medium shot | `medium shot (MS)` | Usually waist-up; balances gesture, face, and nearby setting. |
| Medium close-up | `medium close-up (MCU)` | Upper torso and head; prioritises expression while retaining some posture. |
| Close-up | `close-up (CU)` | Face or small subject area dominates; useful for intimacy, reaction, or evidence. |
| Extreme close-up | `extreme close-up (ECU)` | Isolates a feature such as eyes, fingertips, or an object detail; useful for pressure or clues. |
| Macro | `macro shot` | Shows very small surface detail, texture, or mechanism at magnified scale. |

Do not combine contradictory shot sizes. State crop boundaries when hands, feet, hair, or held objects must remain visible.

## 3. Choose angle and viewpoint for meaning

- `eye-level`: neutral, direct, observational, conversational
- `low angle`: gives the subject visual dominance, scale, or threat
- `high angle`: makes spatial relationships clear or reduces the subject's dominance
- `worm's-eye view`: extreme ground-level scale and distortion
- `bird's-eye view`: overhead spatial pattern while retaining a human observational feel
- `top-down / God's-eye view`: near-perpendicular overhead organisation or detachment
- `Dutch angle`: controlled instability or disorientation; use sparingly
- `point-of-view (POV)`: the camera occupies a character's visual position
- `over-the-shoulder (OTS)`: establishes an interpersonal or viewing relationship
- `two-shot`: shows two subjects and their relational distance in the same frame
- `isometric view`: diagrammatic spatial clarity with reduced natural perspective
- `drone view`: large-scale geography or architecture from above
- `CCTV view`: fixed surveillance placement, wide coverage, observational distance
- `selfie view`: close arm-length perspective and informal immediacy
- `action-camera view`: very wide perspective, proximity, and immersive distortion

Use `fisheye` only when obvious barrel distortion is intended. Use `telephoto compression` when background layers should appear closer together; pair it with a longer-lens look, distant camera position, and shallow spatial compression rather than using the phrase alone.

## 4. Build composition and screen logic

Define subject position, gaze, action direction, and negative space:

- Give look room in front of the gaze and lead room in front of movement unless deliberate tension requires crowding.
- Use foreground framing, leading lines, contrast, focus, or light to guide attention.
- Use left/centre/right and foreground/midground/background anchors instead of vague central placement.
- Keep major overlaps readable; avoid tangencies where limbs or props merge confusingly with background edges.
- State whether the frame is balanced, symmetrical, deliberately off-centre, layered, compressed, or open.

For a series or storyboard, preserve:

- line of action and the 180-degree side
- screen direction of people and moving objects
- eyeline direction and the object being viewed
- established left/right character positions
- lighting direction and time-of-day logic

For one still image, apply these as internal spatial logic: a subject's gaze must point towards the visible target, and interactions must share a plausible axis.

## 5. Translate motion language into a still image

Camera movement is temporal. For a still-image prompt, describe its visible consequence rather than pretending the frame moves.

| Motion term or intent | Still-image translation |
| --- | --- |
| Slow dolly in / intimacy | Tighter framing, reduced personal distance, shallow depth, subject-dominant scale. |
| Slow dolly out / reveal | Wider framing with environment and contextual objects visible around a smaller subject. |
| Fast push-in / shock | Tight perspective, strong centre emphasis, converging lines, optional directional blur in the environment. |
| Dolly zoom / unease | Subject holds similar apparent size while the background shows exaggerated perspective expansion or compression; use only for deliberately surreal tension. |
| Handheld / urgency | Slightly imperfect framing, small horizon tilt, close observational distance, restrained motion cues. |
| Whip pan / speed | Lateral directional motion blur while preserving the focal subject sufficiently clearly. |
| Rack focus / attention shift | Place the intended focal subject sharply in focus while the competing plane falls visibly out of focus. Do not describe an actual focus transition in one still. |
| Orbit / dimensional reveal | Use a three-quarter viewpoint with layered foreground and background to reveal subject volume and surrounding space. |
| Crane or drone reveal | Use a high, wide viewpoint that simultaneously shows subject and environment. |
| POV walk / following shot | Use first-person or rear-follow composition, near-body foreground cues, and forward lead room. |

Omit movement terminology when it adds no visible information.

## 6. Add camera and lens character only when useful

When camera or lens behaviour matters, follow [camera-and-lens-looks.md](camera-and-lens-looks.md). Express the visible rendering first, then optionally name the corresponding body or lens. Do not use unspecified `cinematic lens` filler or combine incompatible optical personalities.

## 7. Design one coherent lighting system

Describe light physically:

1. motivation or source: window, skylight, sun, overcast sky, practical lamp, candle, fluorescent ceiling light, neon sign, stage fixture
2. direction: front, side, three-quarter, back, top, or under
3. size and quality: broad and diffused, narrow and hard, bounced, dappled, hazy
4. colour temperature and colour relationship
5. effects on faces, surfaces, shadows, reflections, and separation

Useful lighting structures:

- naturalistic practical lighting: believable sources inside the scene, restrained contrast
- high-key lighting: bright exposure, low shadow ratio, open and clean mood
- low-key lighting: limited illumination, deep but intentional shadows, tension or secrecy
- backlighting: rim separation, translucency, haze, or silhouette
- underlighting: unnatural upward shadows; use for deliberate unease
- golden hour: low warm sunlight, long shadows, gentle atmospheric depth
- blue hour: cool ambient sky with low warm practical lights
- candlelight: small warm source, rapid falloff, soft flicker implied through uneven highlights
- sodium-vapour look: narrow amber-orange cast and reduced colour separation
- neon / cyberpunk: motivated coloured signage, reflective wet or glossy surfaces, controlled colour contrast
- silhouette: expose for the brighter background while retaining a readable subject outline

Avoid mixing golden hour, blue hour, candlelight, fluorescent light, neon, and moonlight without explaining which source dominates and why.

## 8. Choose colour and image finish

Use a look only when it supports the concept:

- restrained teal-orange: warm skin against cooler environment; keep saturation controlled
- bleach-bypass character: reduced saturation, higher contrast, metallic or gritty texture
- Technicolor-inspired: separated, saturated primary colours and polished classic production design
- film noir: monochrome or near-monochrome, hard directional light, deep shadows, geometric patterns
- Nordic noir: cool muted palette, overcast softness, restrained saturation
- Kodachrome-inspired: warm, dense colour with crisp separation and nostalgic daylight character
- CineStill 800T-inspired: tungsten-night palette, cool shadows, red halation around bright practical lights
- sepia: warm monochrome with aged print character
- cross-processed look: unconventional colour crossover and stronger contrast
- duotone: image deliberately built from two dominant colour families
- selective colour: mostly desaturated image with one controlled colour accent
- infrared, ultraviolet, thermal, night-vision, or surveillance: use only when the image is explicitly technical, experimental, or diegetic

Translate broad mood words into palette, contrast, saturation, black level, highlight roll-off, grain, halation, and texture. Do not add every finish at once.

## 9. Assemble a mature photographic clause

Use this order, including only relevant modules:

`narrative subject and action → shot size and crop → angle and viewpoint → spatial composition → lens behaviour → focus and depth → motivated lighting → palette and finish → optional camera identity`

Example pattern:

`A medium close-up at eye level frames the subject on the centre-right, leaving the left third open toward the object of her gaze. A natural-perspective cinema lens keeps facial proportions neutral while the background falls into smooth, restrained blur. Broad window light enters from camera-left, producing soft cheek highlights, gentle tabletop shadows, and a cool daylight-to-warm-practical colour contrast. The finish uses muted blue-grey shadows, warm natural skin, fine grain, and controlled highlight roll-off.`

Before using the clause, verify that the shot size, crop, lens behaviour, lighting, and depth-of-field instructions do not contradict each other.
