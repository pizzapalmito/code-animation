# HyperFrames requirements check

Use this before HyperFrames production in `code-animation` or `video-guide-html-test`. Check the actual machine and selected project; this file is not evidence that anything is installed.

## Run and interpret the check

1. Confirm `node --version`, `npm --version`, and the selected HyperFrames CLI version from the project directory. Prefer its pinned dependency or wrapper; otherwise use `npx hyperframes`. Read the installed release's engine requirements or error if Node is unsupported; use a compatible supported Node release, not just the oldest version that meets HyperFrames' direct requirement.
2. Run `npx hyperframes doctor --json` (or the equivalent project wrapper). Preserve the result in the task's verification evidence. Check that JSON was returned and inspect `checks[].name`, `ok`, `detail`, and any `hint`. Doctor can exit zero while reporting failed checks. A failed invocation or absent check is unknown, not a pass.
3. Classify the checks against the planned workflow using the table below. Do not equate the top-level `ok` with either production readiness or a blanket blocker: optional tools may be absent, and some packages report success because they install on first use.

| Requirement | When needed | Evidence to inspect |
| --- | --- | --- |
| Node.js, npm/npx, selected HyperFrames CLI | Every HyperFrames workflow | Version commands and doctor; resolve unsupported engines before proceeding |
| FFmpeg and FFprobe | Local rendering, media conversion, and export verification | Both doctor entries pass and point to usable binaries |
| Chrome | Local HTML rendering and browser checks | Doctor reports a discovered browser; a real composition check/render verifies it can launch |
| Memory, disk, frames cache, archive extractor, settings lock | Production readiness | Report resource warnings; resolve blocking failures before the affected work. Low RAM may require closing apps or fewer render workers; do not close the user's apps automatically |
| whisper-cpp | Local transcription from audio/video | Doctor detects `whisper-cli`; check executable help/version and model availability before transcription |
| Python, Kokoro, soundfile | Local Kokoro narration | Doctor plus imports in the Python interpreter HyperFrames actually selects |
| Python, transformers, torch, soundfile, numpy | Local MusicGen generation | Doctor plus imports, including `MusicgenForConditionalGeneration`, in that same interpreter |
| Docker CLI and running engine | Docker rendering | Both doctor checks pass; use `docker info` to confirm engine access |

Transcription, narration, generated music, and Docker are conditional. Check and report their availability, but do not require them for an ordinary local render that does not use them. Existing audio or an original score does not imply a MusicGen requirement. GPU acceleration is separate from package installation; report CPU-only operation when relevant.

Doctor's audio checks establish dependency discovery, not successful synthesis. Model weights, voice assets, credentials for a selected remote provider, and first-use downloads may still be needed. Before relying on a selected audio/transcription provider, run a short smoke test with non-sensitive sample content and inspect its output. Keep installation, import checks, generated-output checks, and human listening as distinct evidence.

## Resolve missing dependencies

Use the installed CLI's hints and the tool's official installation instructions. Honor existing authorization for setup; if installation or a system change is outside it, report the exact missing requirement and proposed fix before making that change. A skill invocation alone does not authorize global upgrades, paid services, or restarting Windows. Recheck only after a relevant change; stop and report a concrete access, restart, or compatibility blocker instead of repeatedly reinstalling.

On Windows:

- Respect `HYPERFRAMES_PYTHON` and `HYPERFRAMES_WHISPER_PATH`. Verify the configured files exist and execute; never hardcode this user's current versioned paths into the workflow.
- A terminal opened before installation may have stale environment variables or PATH. Inspect saved user/machine settings; refresh only the relevant values in the current process or use a new terminal. Preserve deliberate project/process overrides and unrelated PATH entries.
- Prefer a dedicated Python virtual environment for local audio packages, selected through `HYPERFRAMES_PYTHON`. Use that interpreter's `-m pip`, run `pip check`, and verify imports rather than installing into an unrelated Python environment. Preserve working package versions unless a change is necessary.
- Docker Desktop may need WSL and Windows features. Distinguish installed Docker from a running engine. Report any pending restart; do not reboot automatically.

Summarize preflight as ready, blocked, or ready with stated limits for the selected workflow. List missing optional capabilities separately. Continue independent preparation when a dependency blocks only a later step, and never claim a render or provider test passed until it ran.
