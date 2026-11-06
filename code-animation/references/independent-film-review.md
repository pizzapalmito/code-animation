# Independent film review and delivery evidence

This adapts Huashu's separate reviewer and evidence-backed delivery process to HyperFrames. It is a workflow for a fresh subagent, not a claim that a dedicated reviewer tool or human viewer is installed.

## Prepare the exact artifact

Before delegating, render the review candidate and record its absolute path and SHA-256. Create the project's `reviews/` directory if absent. Assemble:

- Encoded MP4, representative decoded frames, transition strips, and short consecutive-frame sequences for key movement. Keep frame numbers/timecodes outside the actual film.
- Native HyperFrames check results, export metadata, decode and audio measurements, deterministic out-of-order seek comparisons, and relevant source/evidence ledger.
- The brief and storyboard, available for the reviewer after its initial artifact-only observation.

Check the complete film: scene interiors, first/last frames, transition start/middle/end, and the weakest or densest section. Averages and attractive contact sheets can hide a blank interval, unreadable label, frozen shot, or late pacing collapse. Measure performance only when render time or dropped frames is a concern. Stress long labels, alternate aspect ratios, or localization when those are supported deliverables; do not test hypothetical variants indiscriminately.

Automated checks must identify actual output, command, outcome, and limitation. Treat black/blank detection, frame-difference spikes, motion amount, and palette analyses as cues to inspect, not universal aesthetic pass/fail rules. Intentional holds and cuts can be correct. Missing required media, a broken decode, wrong duration, illegible essential content, a false depicted result, or accidental blank sections must be fixed.

## Request a fresh reviewer

Use one agent that did not implement the candidate. Start a fresh, bounded context with `fork_turns="none"` where supported; follow the user's model-routing policy and choose the least expensive available model capable of examining the artifacts. Routine visual review does not justify an Astra implementation agent. Do not invoke Claude CLI unless the user explicitly requests Claude delegation.

The reviewer is read-only except for its assigned report under `<project>/reviews/`. It does not edit production files, install packages, publish, approve releases, or overwrite earlier reports. Give paths to only the needed media, evidence, and brief; exclude unrelated conversation and producer praise or self-ratings.

Example assignment:

> Independently review this candidate: `<MP4 absolute path>`, SHA-256 `<hash>`. You did not produce it. First examine the media/decoded frames without reading the producer's evaluation; state what the viewer can understand and flag ambiguity. Then compare against `<brief/storyboard>` and `<evidence ledger>` for factual accuracy and requested behavior. Inspect scene interiors, transitions, label reading time, consistency, clipping/occlusion, chronology, numerical units, and the final payoff. Use consecutive frames or playback if available for motion; stills alone do not prove smoothness. Do not claim playback or human listening unless actually performed. You are not alone in the workspace: do not change or revert production files. Write only `<project>/reviews/<candidate>-independent.md`. Include artifact hash, inspected times/frames, methods actually used, P0/P1/P2 findings with evidence and proposed corrections, checks NOT RUN/BLOCKED, and verdict `changes requested`, `no blocking findings in inspected evidence`, or `insufficient evidence`. Stop after reporting. The primary agent retains final approval.

P0: materially wrong, missing, or unusable content. P1: a significant clarity, continuity, readability, pacing, or brief mismatch. P2: optional polish. Each finding names a timestamp/element, observed problem, viewer consequence, specific fix, and what should remain. Avoid numeric beauty scores or conclusions based on the producer's assertion that checks passed.

If video playback is unavailable, the reviewer can inspect decoded images and movement sequences, but must mark playback NOT RUN. If no image-capable independent agent can inspect the artifacts, record that review is unavailable; a text-only report is not visual review. Never impersonate a second agent. An unavailable reviewer does not prevent delivering a clearly marked unreviewed draft, but cannot count as an independent pass.

## Fix, recheck, and report honestly

The primary agent verifies each finding against the output and brief, fixes blockers, and documents any disagreement with evidence. Run relevant technical checks again on changed output. Request one targeted re-review for material fixes, using the new artifact hash and exact affected intervals. Preserve findings; do not silently rewrite the first report to look clean. If important problems survive two review/fix cycles, report the concrete unresolved issue and choose a bounded correction or marked draft instead of looping indefinitely. Small unrelated metadata edits do not invalidate visual evidence; changed encoded media does require renewed evidence for the affected content.

Write `REVIEW.md` with:

1. Artifact name, hash, version, and brief/renderer choices.
2. Measured results: dimensions/fps/frame count, video/audio/container duration, codec/colour metadata, full decode, audio levels/silence/clipping, asset/font loading, native checks, and repeated/out-of-order seek evidence. Use PASS, FAIL, BLOCKED, or NOT RUN; include actual command/report paths. Do not manually invent or improve machine results.
3. Independent review report path and coverage; unresolved findings and explicitly accepted warnings.
4. What was visually inspected, played, heard by a person, or not checked; the weakest shot and meaningful limitations.
5. Reusable project lessons as method + evidence + why it worked + where it applies. Shared skills/memory change only when requested.

Hash the source archive and verify its contents can rebuild the film; exclude caches, secrets, and private raw captures. Retain the approved sample intact. A technical pass and an independent review are not user acceptance, permission to publish, engineering certification, or approval to skip the 20-second review point.
