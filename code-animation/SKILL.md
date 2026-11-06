---
name: code-animation
description: Create HyperFrames videos and narrated task-based app guides using real workflows, shot planning, approved visual presets, independent film review, and media verification. Preserve the user's brief and 20-second review point. Use for video production; not ordinary website animation or slide decks.
metadata:
  version: 0.1.0-alpha.6
---

# Code Animation

Use **HyperFrames as the default authoring and rendering engine** for new videos. Use the installed [Barty-Bart motion-graphics skills](https://github.com/Barty-Bart/motion-graphics) for creative methods and staging. Preserve an existing project's established renderer unless a migration is requested, and honor an explicitly requested engine such as Remotion. Its version authority is `metadata.version` above.

## Choose the production skill

- For task-based app tutorials, full application guides, or requests to repeat the approved SBM guide style, use [the app-guide workflow](references/task-based-app-guides.md). It covers intake, scope, live evidence, lesson planning, narration, production, and offline delivery. Load its preset and production checks only for that mode. When available, use `video-guide-html-test` for HTML/Electron capture mechanics and `illustrated-project-guide` when an illustrated manual is also requested; neither expands the requested deliverables.
- `explainer-engaging`: one continuous story following a hero object through a sequence. Use its staging and camera ideas for non-product stories when they fit the brief.
- `explainer-high-energy`: a short, beat-driven promo when the user wants that energy.
- `explainer-default`: a calm software product demo or feature walkthrough.
- `motion-broll`: cutaways or overlays timed to existing footage and a transcript.
- `object-separation`: isolate a subject in footage when masking is part of the request.
- `sound-effects`: a recorded-effects pass when the user wants it. Its recorded-sound method is optional; do not replace an agreed original score merely because the skill is installed.

Load only the selected creative skill and its relevant supporting files. Follow its creative method while honoring the user's brief and the rules below; its engine defaults do not override the engine selected here. For HyperFrames, also load the installed `hyperframes` and `hyperframes-cli` skills (plain or plugin-prefixed names), and the relevant GSAP skill when authoring GSAP motion. For Remotion, load `remotion:remotion-best-practices`. Check the current tool inventory and project-local CLI before claiming an app tool was used. If both engines are requested, share an absolute-time scene and fixed audio master where practical, then deliver a separate MP4 from each engine.

## Check requirements before production

Before building or rendering with HyperFrames, follow [references/hyperframes-preflight.md](references/hyperframes-preflight.md). Run the installed CLI's `doctor --json`, inspect individual results, and report which requirements are ready, missing, or not needed for the selected workflow. Repeat after environment changes or a dependency-related failure. Do not assume a previous installation still works.

Use the selected HyperFrames version's authoring, check, snapshot, preview, and render commands. Verify command flags with its help rather than copying commands from a different release. Keep the review point below and the user's existing authorization when following third-party workflows.

## Resolve the brief before building

Ask only for choices that are still missing, together and in this order:

1. Visual style or reference.
2. Actual 3D or 2D/isometric 2.5D. Actual 3D adds camera orbits, lighting, and depth; 2.5D communicates depth with simpler graphics.
3. 30 fps or 60 fps. Recommend 30 fps for most explainers and 60 fps when very fluid motion matters.

Also establish the subject, audience or message, duration, and required aspect ratio. Combine these with a selected skill's own brief questions; do not ask for the same fact twice. A stated practical default is 1920×1080, 16:9. Default to original sound design with no narration unless the user asks otherwise. Do not choose paid media, external music, voice, or a 3D engine merely because a selected skill offers it. Record the agreed choices in the project. The user's selected fps, duration, style, and audio take precedence over a third-party skill's defaults.

For instructional videos, favor real screenshots, labelled rectangles, pointing arrows, and short fades. Animate typing, sliders, or automatic loops only when the user requests them. Keep playback controls, debug labels, chapter counts, and timecodes out of the encoded frame unless they serve the requested visual style.

## Direct the film before rendering

Use [references/direction-and-storyboard.md](references/direction-and-storyboard.md) to establish one concrete example, a shot table, a consistent visual language, a representative style frame, and purposeful camera/audio cues. Adapt these methods from `huashu-art-motion` to the selected engine. For art, reference-video analysis, characters, or specialized explanatory graphics, use the selective library routes in that reference; do not load or copy the entire source engine.

Inspect the representative frame at output size before rendering the film. Compare alternative compositions when the direction is materially uncertain; preserve an already selected or approved direction. This preparation does not create an extra approval gate or replace the required 20-second MP4.

## Review the short film before expansion

For a requested film longer than 20 seconds, first deliver a real **20-second MP4** with representative artwork, a substantive story beat, transitions, framing, and synchronized sound. Include editable source or a preview. Wait for explicit acceptance before implementing or exporting the longer film; explain that this skill requires the review point. Revise the test if rejected. A requested video of 20 seconds or less is itself the deliverable. Reuse an already approved test unless the visual direction materially changes.

Preserve the approved source, soundtrack, MP4, and archive. Use a new entry point and versioned filename for the longer film. Approval of a test authorizes the requested expansion, not publication or changes to unrelated projects.

## Verify and deliver

Use [references/independent-film-review.md](references/independent-film-review.md) for the two-part acceptance process: technical evidence from the actual export, then a fresh reviewer who did not produce it. Request one bounded, read-only reviewer subagent for a new review MP4, first final film, or material visual/audio change; scope follow-up review to changed content and adjacent transitions. Reuse prior review for an unchanged encoded artifact or a metadata/source-only edit that does not change the film. The primary agent owns fixes, verification, and the final verdict. Review the finished media independently of the producer's self-assessment. If required independent review cannot run, disclose that limit and label the artifact an unreviewed draft, not independently approved.

- Inspect encoded frames from each scene and transition for legibility, clipping, unintended overlays, and blank intervals. Check repeated out-of-order seeks and actual motion.
- Verify dimensions, fps, frame count, codec, color metadata, and video, audio, and container durations. Fully decode each MP4 and measure audio for silence and clipping. Distinguish measurement from human listening.
- For dual-engine work, verify both exports independently and compare representative frames so they tell the same story.
- Confirm approved artifacts remain unchanged and any source archive opens and contains rebuildable files.

Tie checks and reviewer findings to the exact artifact hash. Record accepted warnings, unresolved findings, and evidence limits in the project's `REVIEW.md`; distinguish intentional reading holds from accidental freezes. Keep useful lessons in the project's review record with evidence and applicability. Do not silently rewrite shared skills or user memory after a production task.

Deliver direct links to the MP4 and editable source, with duration, fps, checks actually run, and remaining limits. Do not claim aesthetic acceptance or listening review that did not occur.

## Change record

- `0.1.0-alpha.6`: Preserve the user-approved SBM task-guide workflow as a reusable app-guide mode: concise intake, verified live workflows, visual/narration preset, production and packaging checks, and a copyable planning worksheet. Retain the existing short-film approval rule and other video modes. User acceptance covers the SBM result; portability to other apps still requires app-specific verification.
- `0.1.0-alpha.5`: Adapt Huashu's shot planning, style-frame validation, camera and audio direction, selective art library, independent reviewer, and artifact-specific evidence process for HyperFrames.
- `0.1.0-alpha.4`: Default new videos to HyperFrames; add workflow-specific dependency checks and shared setup guidance. Preserve existing renderer choices, brief requirements, and the 20-second review point.
