# Task-based application guides

Use for an instructional series showing people how to complete tasks in a real app. This workflow comes from the SBM Workstream guide that the user explicitly accepted on 2026-11-06 and asked to reproduce for other applications. Preserve the decisions and production methods below; derive the actual lesson list, branding, roles, and evidence from the new app.

Read [the approved preset](approved-walkthrough-preset.md) when selecting this visual style. Read [production checks](app-guide-production-checks.md) before implementing capture, timelines, verification, and packaging. Copy [the planning worksheet](../assets/task-guide-plan.md) into the project when useful. The existing short-film approval and independent film review rules remain authoritative.

## 1. Recover context and ask only what changes the work

First inspect the supplied app, current project materials, earlier answers, approved sample, and relevant connected sources. Resolve the exact app checkout/runtime/version; a familiar project name is not enough. Preserve dirty worktrees and keep the guide separate from application source. Record decisions once in the brief/manifest and reuse them after interruptions.

Ask missing creative choices together, in the entrypoint's order: style/reference, actual 3D versus 2D/2.5D, then 30 versus 60 fps. The remaining questions can be grouped around the deliverable:

| Missing decision | Useful question | Decision it changes |
| --- | --- | --- |
| Audience and coverage | Who will use this, which tasks/roles should it cover, and what is excluded? | Lesson inventory, vocabulary, prerequisites, role handoffs |
| Format and length | Individual task videos, a combined film, or both; target length and aspect ratio? | Independent lesson structure and framing |
| Speech and sound | Narration language, voice/tone, and music preference? | Voice selection, timing, captions, mix |
| Input animation | Short typing for names/titles, or immediate field reveals? | Capture states and pacing |
| Delivery | MP4s only, or an offline library with steps, transcripts, captions, and source? | Packaging and player acceptance checks |
| Safe app access | Which authorized demo/disposable environment is available? | Real runtime evidence without unintended production changes |

Offer the approved preset when the user wants this result again: polished real-app 2D, 1080p30, calm narration, short typing, separate task videos and offline library. Say which defaults are being carried forward. Do not ask the user to reapprove known choices, and do not silently replace a supplied voice, aspect ratio, or style. A request to use the approved narrated preset already establishes narration; the generic no-narration default does not override it.

Use session authorization for reversible local preparation and disposable fixtures. Do not turn fixture preparation into another approval ceremony. Obtain missing authorization before mutating a production/shared system. If only production read access exists, capture authorized reads and identify what cannot yet be demonstrated; do not invent saved results. "Use all tools" means choose the tools that improve the outcome, not invoke every installed tool or acquire paid/cloud media without need.

If a required write workflow cannot be demonstrated within the available access, finish useful authorized inspection and mark that lesson BLOCKED or NOT VERIFIED in the coverage matrix. State the specific safe access/evidence needed. Deliver any permitted partial material with that label; do not call the full guide complete or repeatedly attempt forbidden writes. Resume the missing workflow when its blocker is resolved.

## 2. Map outcomes before shots

Build a capability/coverage matrix from real navigation, supported roles, source/help material, and observed runtime behavior. For each candidate task record audience, prerequisite, entry point, action sequence, observable completion, and verification status. Full-app scope means covering the agreed workflows, including projects/tasks where applicable, not stopping at the first attractive feature. Explicit exclusions remain exclusions.

Name lessons by an outcome: "Create a project and its first task", not merely "Projects tab". Each lesson must work independently while contributing to a coherent story. Follow one sanitized example across relevant roles. Give the viewer enough starting context to enter any lesson without watching the preceding films.

The SBM series covered sign-in, project creation, tasks/contributions, Excel import, finding records, assignment, submission, request changes, resubmission, approval, timeline, workload rating/history/export, templates, and sourced assistant answers. This is an example of coverage depth, not a universal 15-lesson requirement. Deployment, administration, and backup were outside that brief.

## 3. Establish real workflow evidence

Use the actual application with a disposable data store and synthetic people/projects when possible. Disable scheduled jobs, notifications, mail, and other external effects in the isolated training setup. Record the exact app version/source hashes, fixture setup, runtime boundary, and local endpoints. Do not edit the product just to make filming easier unless a separate app change is requested.

For each lesson, execute the full path through the UI and verify the result. Reopen/reload saved records; check the receiving role's account for a handoff. Source/DOM inspection can locate controls but cannot prove authentication, backend persistence, or permissions. A frontend clone is not equivalent to the real app. Reuse HTML/CSS only where it faithfully represents an observed state, and label explanatory reconstruction as such.

Capture stable states and the real target's bounding rectangle after async work settles. Maintain an evidence ledger connecting step ID, role, action, before/after state, screenshot, target geometry, expected result, observed result, and verification status. Use real screenshots as the visual base; add camera, pointer, focus outline, and instructional text as separate layers. Generated art must not replace evidence of application behavior.

Include useful error/correction paths when they teach a real task: missing required input, incomplete submission, reviewer feedback, stale-data recovery. Record any deliberately induced failure in evidence. Preserve actual quirks: show a verified workaround and resulting state, or disclose the blocker. Never fabricate successful results, populated history, model answers, or a cleaner summary screen.

## 4. Design and storyboard

Create a brief, lesson manifest, coverage matrix, and storyboard before full production. Each shot specifies time/frames, visible state, action, target, camera purpose, concise on-screen instruction, exact narration, audio cue, and evidence source. Start with the task context, demonstrate actions in order, and finish on a visible verified result. Avoid a long promotional introduction to every short lesson.

Keep the real control legible alongside enough context to understand it. Pan/zoom to guide attention; hold while the viewer reads. Critical summary values, Save/Create buttons, and error messages must remain visible when taught. A still reading hold is intentional instruction, not an automatic motion defect. Labels and pointer positions must refer to the control actually shown.

Write narration in calm, direct steps: action, relevant choice, then what the result means. Use the app's actual labels; explain unfamiliar terminology briefly. Avoid implementation jargon, exaggerated claims, and reading every screen label aloud. Describe role transitions and whether a result is partial or complete. Draft narration with the storyboard, then revise it against live evidence before generating voices.

Inspect the densest representative frame at output size. For a new unapproved direction, produce a real 20-second sample with representative task content, pointer/camera movement, typing if requested, and the chosen narration/sound. Preserve sample source/audio/MP4/archive and wait for explicit acceptance before expansion. Reuse an already approved test when the direction has not materially changed; new-app workflow validation still applies. Do not add repeated approval gates after the user authorizes expansion.

## 5. Produce from measured timing

Generate narration per step and cache it by text, voice, locale, and speed. Use measured take durations to place captions, motion, reading holds, and scene boundaries. Do not force speech into an arbitrary template or estimate final timings from word count. Keep planned target length separate from the computed frame-aligned duration.

Build one independently seekable composition and fixed audio master per lesson. Keep local assets/fonts and deterministic timelines. Start with one complete lesson to establish capture-to-render correctness, then reuse the pipeline across the scoped inventory. Re-render only affected lessons after localized corrections, while checking shared changes across affected outputs.

## 6. Review and deliver the whole agreed scope

Apply the [production checks](app-guide-production-checks.md) and [independent film review](independent-film-review.md). Review actual encoded outputs, including dense frames and motion, rather than relying on source markup or attractive contact sheets. Tie every report to an exact candidate hash. A fresh reviewer may discover an app/UI contradiction the producer overlooked; verify it and fix the guide with truthful evidence.

For the agreed offline library, provide search, role/workflow filters, lesson prerequisites, steps with seeking, transcripts, captions, playback speed, deep links, and next-lesson navigation. Keep these controls in the player, not burned into the film. Validate actual playback from the final delivery location, including local-file caption loading and responsive layout.

Deliver versioned MP4s, captions, the offline library if requested, storyboard, review/evidence summary, and rebuildable source. Keep guide version independent of app version and document one authority. Record exclusions and unverified environments; local disposable runtime proof does not certify a deployed office system. State which checks ran and what was actually watched or heard. The user's acceptance of the resulting film is distinct from automated verification.

## Why this workflow produced the accepted result

- Outcome-based lessons give viewers a usable procedure and a clear finish.
- One realistic example makes cross-role transitions and cumulative changes understandable.
- Actual UI plus persisted results keeps the instruction trustworthy.
- Narration-led timing provides room to follow actions and read important values.
- Restrained camera/focus layers make a real interface feel polished without obscuring it.
- A representative approved sample settles creative choices before scaling production.
- Independent encoded-output review catches both visual defects and misleading UI states.
- An offline library makes a long series searchable and useful at the moment of work.

Preserve these decision criteria and observable evidence in project notes. They are reusable rationale, not a requirement to store an internal reasoning transcript.
