# Direction and shot planning

Adapted from the installed [huashu-art-motion skill](../../huashu-art-motion/SKILL.md), especially its shot table, camera language, explanation grammars, style-transfer research, and evidence-backed lessons. These are creative methods for the selected renderer, not a requirement to replace HyperFrames with Huashu's engine.

## One concrete example, visible cause and effect

Write a compact `STORYBOARD.md` (or extend the project's existing SPEC/beat sheet) before implementation:

- Brief: audience, takeaway, duration, dimensions, fps, language, audio choice, and illustrative versus observed content.
- Visual language: materials, typography, light, palette relationships, and character/asset method. Preserve real UI and brand colours even when the framing has its own palette.
- Continuity: the object, person, task, or example the viewer follows, and what changes by the end.

| Time / frames | Visible subject | Action and resulting change | Framing / camera purpose | Exact on-screen words | Source / evidence | Audio cue | Implementation |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Start–end | A specific object, interface control, or data view | What it does, not just “appears” | Where attention moves and why | Include labels and units | Asset or factual source; mark illustrative content | Event, music beat, spoken phrase, or silence | Scene / layer / asset |

Check contiguous coverage, frame-aligned boundaries, readable holds, factual numbers/units, and continuity. Aim to open on a relevant situation and finish on its visible result. Titles and explanatory text are allowed when they help; do not turn every shot into a heading plus cards. Brief words should support what the picture explains. Reading time depends on language, complexity, and audience, not a universal character quota. Tutorials may need long holds and exact UI labels.

Choose visual methods by purpose: real captures for interface procedures; a growing diagram for mechanisms; evidence/photo collage for sourced investigation; axes and units for quantitative comparisons; pose changes for character stories; material and brushwork for artistic scenes. Build only the machinery the story needs.

## Validate one frame before hundreds

Render a representative frame containing the hardest subject, key labels, and proposed framing. Check recognizability, hierarchy, legibility at output size and a small preview, contrast, clipping, UI fidelity, and style consistency. For a new uncertain direction, compare two or three different compositions of the same beat; changing only colour is not a new direction. Choose from the existing brief or ask only when a material creative choice remains unresolved. Reuse approved references; do not force new choices for every job.

For an art reference, separate its visual language (material, light, shape, space, colour relationships) from its subject and composition. Study multiple relevant references when the style is unfamiliar; cite those actually inspected. Make an original scene for the current story. A style-card title or archived sample is not proof that a reusable implementation exists or that it works in another aspect ratio.

Use supplied/verified imagery when it is the subject. Code can annotate and composite it, but should not replace meaningful evidence with a fictional interface. Generated imagery is appropriate to illustrative content when authorized and useful. If characters are needed, use a consistent asset/pose method, preserve anatomy and identity across shots, and check silhouettes, joints, eye lines, and occlusion. Do not insert mascots or anthropomorphic props merely as decoration.

## Camera and motion

- Keep the camera still while the viewer reads or an object already explains the action. Move to reveal detail, follow causality, establish geography, or resolve the scene.
- Use slow pushes, pans, and pullbacks for transitions; reserve fast moves for a meaningful reveal or emphasis. Avoid repeating the same push on every shot. Vary framing without changing visual identity.
- Give entrances time to settle and hold the result before moving on. Stage one principal change at a time; supporting motion should not compete with it.
- Tie transition shapes to objects or concepts in the film when useful. A simple cut or fade is preferable when a decorative transition obscures the explanation.
- For continuous journeys, maintain positions, poses, and trajectory across boundaries using absolute time. Keep seeded randomness and deterministic seeking; never regenerate random texture independently on every frame.
- Art scenes can contain purposeful internal motion in their materials and subjects. Tutorials should not acquire ambient loops, simulated typing, or camera movement that the brief did not request.

## Audio and timing

Preserve the audio choice in the brief: this skill defaults to original sound without narration. If narration is requested, existing speech/transcript timing sets the pace; do not stretch speech or cut words to fit a visual template. If a music track is supplied, measure its beat grid before aligning cues. Place the visible event (contact, reveal, number settling) on the cue, not merely the start of its transition. Use a small coherent family of sound motifs; leave room for speech. Share a fixed audio master across exports and verify sync from the encoded file.

## Selective Huashu library routes

Read only the route needed, then adapt the technique into HyperFrames HTML/GSAP or the project's chosen renderer. Paths below refer to the installed library and may contain engine-specific code; inspect compatibility and asset/font licences before reusing code or files.

| Need | Source |
| --- | --- |
| Shot planning and camera decisions | [Shot-table template](../../huashu-art-motion/references/镜头表模板.md), [camera language](../../huashu-art-motion/references/镜头语言.md) |
| Choosing explanation methods and motion primitives | [Animation grammars](../../huashu-art-motion/references/09-视频动画语法.md), then only the chosen grammar card it links |
| Art style, materials, or a new style transfer | [Style index](../../huashu-art-motion/references/风格配方/INDEX.md), [cross-scene style research](../../huashu-art-motion/references/15-跨场景风格提炼.md), then the relevant style card |
| A difficult visual before full rendering | [Frame-first methods](../../huashu-art-motion/references/03-一帧先行四条路线.md) |
| Character assets and performance | [Characters](../../huashu-art-motion/references/10-角色.md), [character detail](../../huashu-art-motion/references/角色精细度.md) |
| User-supplied speech or generated images | [Voice capability guide](../../huashu-art-motion/references/capabilities.md), [image capability guide](../../huashu-art-motion/references/images.md); use only capabilities actually requested |
| Proven techniques and their limits | [Positive lessons](../../huashu-art-motion/references/07-正面经验.md) |

For a reference-video recreation, first break down the supplied clip into subjects, camera, timing, motion, transitions, and audio relationships; reproduce mechanisms in the new context rather than copying unrelated sample content. Inspect the library's analysis tools only if they materially help and their dependencies and inputs are available.

Huashu's `qa.py` and storyboard linter assume its own engine/spec or Chinese table conventions. Its delivery gate also encodes stylistic thresholds. Do not run them against an arbitrary HyperFrames project and claim equivalent coverage. Use HyperFrames checks plus encoded-media verification and independent review. Avoid blanket palette bans, minimum motion quotas, mandatory AI characters, forced direction approvals, or automatic shared-skill edits; those choices are contextual, not universal quality tests.
