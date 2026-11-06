# App-guide production checks and demonstrated failure fixes

Read when implementing the [task-guide workflow](task-based-app-guides.md). Apply checks to the actual requested outputs. These notes preserve failures and fixes observed in the accepted SBM production; app-specific details and numerical tolerances are examples, not global quality rules.

## Preflight and project boundaries

- Run the current renderer's dependency preflight and inspect each result. Use installed CLI help for commands/flags. A prior working setup is not current proof.
- Separate guide source, synthetic app runtime/data, source captures, generated lessons, candidate QA, and final delivery. Keep app source and approved samples unchanged; hash them before/after when preservation matters.
- Identify local font, voice/model, vendor library, and music provenance/licenses. Use relevant tools; skip installed media/3D/cloud capabilities that the brief does not require.
- Keep guide version authoritative in one manifest; record the target app version independently. Keep planned duration separate from computed duration to avoid cumulative rounding on repeated builds.

## Capture and workflow assertions

- Scope selectors to the intended navigation/control; a similarly named root container can satisfy a broad selector without activating the requested tab.
- Wait for actual mutation/refresh completion before capture. Assert useful result content, reopen/reload saved data, and verify receiving-role state for handoffs.
- Inspect boolean DOM attributes correctly: an open `<details>` may have `open=""`; check attribute presence rather than truthiness, or automation can close it unintentionally.
- Store screenshot dimensions, device scale, target bounds in source coordinates, and state hashes. Keep coordinate transforms explicit when moving into output/camera space.
- A workbook render is evidence of workbook content, not a screenshot of Excel. Label its provenance. Controlled network failures can demonstrate real recovery UI; document the intervention and verify restoration.
- Empty history and deterministic assistant starter responses must stay accurately described. A "local AI ready" indicator is neither proof of arbitrary model responses nor proof that a model is absent.

## Deterministic timeline and speech

- Give every camera/pointer tween an explicit absolute start time and from-state. Use `fromTo` with appropriate `immediateRender:false`. Initialize hidden states with CSS or immediate `gsap.set` outside a paused timeline when necessary; a time-zero timeline set may not establish the first captured frame in every renderer.
- Never append an initialization `tl.set` without its intended position. In the sample this placed a pointer reset mid-typing rather than at initialization.
- Seek to times repeatedly and out of order. Compare rendered state, and separately assert expected pointer coordinates. Two equally wrong previews can match perfectly.
- Cache voice takes by content hash including text, voice, language, and speed. Batch local generation efficiently. Read actual WAV duration and align captions/holds from it. Whole-film transcription may stretch words across silence or beyond the film; use it as a text cross-check unless its timestamps are independently validated.
- Keep a fixed audio master per lesson, with separate voice/music/cue stems. Match sample rate, final duration, fades, and frame-aligned visual boundaries. Check voice starts/ends and caption non-overlap against the exact final timeline.
- Use explicit UTF-8 for JSON/Markdown/text reads and writes on Windows. Default CP1252 decoding corrupted a middle dot in guide metadata. Don't depend on ASCII-only content to conceal encoding errors.

## Encoded-media verification

For every exported lesson, record exact path/hash and PASS, FAIL, BLOCKED, or NOT RUN with evidence paths:

1. ffprobe or equivalent: dimensions, fps, frame count, codec, color metadata, and video/audio/container durations.
2. Full decode of the MP4; not just probing its header.
3. Measured loudness, true peak/clipping, silence and voice timing. Whole-mix silence results can be masked by music. Claim listening only when actually performed.
4. Decoded first/last frames, each shot interior, transition start/mid/end, and full-size dense/weak frames. Inspect consecutive-frame motion strips or playback for important movement; contact sheets alone are insufficient.
5. Native renderer checks, including layout/contrast, motion, audio, and craft sections when available. Keep raw logs. Combined stdout/stderr may contain text around JSON; extract the actual envelope instead of assuming the whole log is parseable JSON.
6. Out-of-order/repeated seeks and expected target assertions. Compare actual encoded pointer regions, not only source DOM or preview-to-preview equality.

Investigate warnings by consequence. Screenshot-track density and deliberate speech/reading holds may be valid; record why. Don't add meaningless movement to satisfy a motion metric, and don't blanket-ignore all warnings because some holds are intentional.

Calibrate pixel tolerances to the renderer, encoding, and a known failure. The SBM review isolated tiny GPU differences around the rounded window border and used a separate JPEG/H.264 cursor comparison tolerance. Do not reuse those thresholds as an excuse to accept movement of text or the wrong control. For FFmpeg JPEG extraction, explicitly selecting `yuvj420p` can resolve limited-range MJPEG encoding rejection; verify the installed encoder before treating it as required everywhere.

## Candidate identity and independent review

Follow [the shared independent review protocol](independent-film-review.md). Give the reviewer exact hashes, decoded artifacts, motion evidence, storyboard, and source ledger. Review the artifact before the producer's assessment. The reviewer has a bounded report-writing scope and does not edit the app or production source.

On re-render, archive the previous candidate and its evidence, then regenerate current QA in a clean candidate directory. Never leave stale old-timestamp frames beside fresh ones as though they describe one MP4. The SBM re-review initially encountered a leftover frame from the old timeline; archiving it and decoding the new candidate restored trustworthy evidence. Preserve the original finding and add the correction result.

A significant finding in the template lesson was a mismatch between the selected template and the app's stale summary. The correction showed a real Back/Continue refresh, then checked the summary and copied tasks. This is the model for handling quirks: verified procedure and truthful result, not a fabricated UI or an unauthorized app fix.

After a local fix, re-render/recheck the affected lesson and adjacent transitions, then request targeted review of the changed hash. Shared template/audio changes require coverage of affected lessons. Report unresolved findings; do not repeatedly render unchanged media or imply subjective playback approval from stills.

## Preview process lifecycle

Background preview termination can return before its port is released. Prefer a unique port per sequential preview or positively verify port/process cleanup. On Windows launch background helpers hidden. Keep waits bounded so progress can be communicated. Use permitted execution mechanisms; report a concrete access failure rather than treating an untested launch assumption as a blocker.

## Offline library and source package

When the library is in scope, test it using its actual delivery mode, including `file://` if promised:

- Each video's metadata and real playback time advancement; steps seek/pause correctly and speed changes work.
- Caption cues actually load. Blob URLs can support packaged VTT content where local-file cross-origin loading fails; don't weaken browser security to make it work.
- Search, role/workflow filters, prerequisites, transcript display, deep links, next lesson, and mobile overflow.
- No JavaScript errors, missing fonts/assets, or unintentional network dependencies. Recheck the final relocated delivery folder rather than only the development server.

Package the agreed MP4s/VTTs/player, manifest, storyboard, review reports, and editable source. Use relative assets and self-contained lesson projects. Exclude databases, secrets, dependencies/caches, private raw captures, and irrelevant workspace files. Include only sanitized evidence needed to understand/rebuild the guide.

Verify ZIP integrity/CRC, required contents and hashes; extract into a new directory and run documented build steps to regenerate compositions, timelines, captions, and audio masters. Compare generated outputs where deterministic. Distinguish this source rebuild from a second full MP4 render; never imply the latter ran if it did not. Verify approved sample/prior release preservation separately.

Final handoff states scope delivered, direct entry point, version, total duration/fps, verification evidence, and meaningful limits. Do not claim production-server or human listening acceptance from local fixture/media checks.
