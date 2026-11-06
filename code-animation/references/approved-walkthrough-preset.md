# Approved SBM walkthrough preset

Use this as a concrete starting point when the user requests the accepted SBM guide style for another app. It is a presentation preset, not permission to reuse SBM branding or skip verification of the new application. User choices override these defaults.

## Accepted brief

Polished real-app walkthrough; 2D; 1920 x 1080 at 30 fps; separate task films, generally 60–120 seconds but as long as the task needs; calm female North American English narration; short typing for names/titles and field reveals for long inputs; quiet original music and subtle interaction cues. Delivery includes individual MP4s and an offline HTML library with search, role/workflow filters, step seeking, transcripts, captions, and speed controls.

The user approved the short style/narration sample before full production, then explicitly said the completed guide was precisely the expected output and asked to preserve the method. This establishes an accepted creative reference. It does not establish that every future application or voice has been tested.

## Layout and motion recipe

These are measured values from the reference implementation. Scale/recompose for another aspect ratio; do not blindly crop it.

| Element | Reference value | Adaptation rule |
| --- | --- | --- |
| Canvas | 1920 x 1080, 30 fps; paper `#faf9f6` | Preserve chosen output format |
| Typography | Local Inter; dark text `#24282b` | Use an available, licensed local font |
| Title | x96, y32; 32 px, weight 650; 6 px accent strip | Fit real lesson titles; test longest |
| Brand label | right 96, y36; 28 px | Replace with actual product name/brand |
| App window | x96, y100; 1728 x 864; radius 14; subtle border/shadow | Keep instructional UI readable |
| Capture | Viewport 1600 x 800 at device scale 2, PNG 3200 x 1600 | Preserve real layout; adjust for app responsiveness |
| Camera | Initial x32, y16, scale 1.04 in app-window coordinates | Based on capture size and viewport |
| Detail framing | Control bounds plus context; scale capped at 1.42 | Include necessary labels, summary, and action buttons |
| Pointer | 24 x 32 dark SVG with white outline | Point at actual control; avoid covering its label |
| Focus | 2 px brand outline with thin white outer edge | Derive geometry from actual target bounds |
| Instruction | y995; 29 px; centered; 120 px side margins | One short action phrase; prevent clipping |
| Camera/pointer | About 0.8–0.9 seconds, `power2.inOut` | Purposeful moves; settle before reading |
| Typing | About 0.12–0.16 seconds per captured character/group | Only when requested; preserve authentic input states |

The reference used SBM's authoritative red `#AA1E2E`. Retrieve the new app's real design token/logo instead of carrying this red into unrelated products. Avoid decorative dashboards, fake browser controls, chapter counters, debug labels, and encoded timecodes. Player navigation belongs outside the exported picture.

The control-centered camera in the reference used a scale bounded by the available width/height and control bounds, then clamped translation to the captured image. That is a starting calculation, not proof of good framing: inspect the resulting frame, especially footer actions and summary values.

## Narration and audio recipe

The accepted voice was local Kokoro `af_nova`, `en-us`, speed 0.96. Reuse it when available and requested; check installed voices/model licensing rather than assuming a model path or acquiring a paid service. If unavailable, surface the material voice substitution before committing to a long render. Never claim another voice is the approved recording.

Generate one take per instructional step. The reference scheduled speech about 0.7 seconds into each shot, used `max(6 seconds, voice duration + 2.4 seconds)` as a starting shot length, and rounded boundaries to frames. Adjust for screen complexity and typed input; these are starting values, not mandatory minimums for every app.

Keep speech intelligible over a quiet original bed. The accepted implementation used softly synthesized Am/F/C/G chords changing about every 5 seconds, short fades, and a light interaction cue. These motifs are optional; don't add external music merely because a generator is installed. Preserve voice, music, and cue stems alongside the fixed mix and record their provenance/licensing.

Normalize and measure the actual export. The SBM films measured approximately -21.4 to -19.2 LUFS integrated and maximum -4.7 dBTP, but these are observed results, not universal targets. Music can conceal silent narration from whole-mix silence detection, so verify speech takes, timing, and intelligibility separately. Measurement is not a human listening review.

## Reference implementation and evidence

Reference guide: SBM Workstream task guide `0.3.0-beta.1`, targeting app `0.3.1-beta.6`. It contains 15 films, about 18m45s total, and 102 narrated real-app states. These counts describe this completed example, not the required size of a new guide.

Optional local implementation reference, if still present:

`<your-animation-workspace>/src/sbm-workstream-guide-full`

Useful files: `guide.json`, `STORYBOARD.md`, `REVIEW.md`, `scripts/capture-full.cjs`, `scripts/build-series.py`, `scripts/build-library.py`, `scripts/verify-series.py`, `scripts/verify-seeks.cjs`, `scripts/verify-library.cjs`, and `scripts/package-series.py`. Inspect only relevant files. Treat paths/tool versions as historical examples; this skill must remain usable without that directory. Do not copy fixtures, credentials, app-specific selectors, or hardcoded local model paths into another project.

The accepted series verified full media decode, metadata, audio measurements, out-of-order seeks, pointer positions, 56 actual offline-player checks, source extraction/regeneration, and independent visual review. Production reports explicitly did not claim human listening, office deployment, populated historical reports, or arbitrary model-answer validation. Preserve that distinction even though the user accepted the overall result.
