# Code Animation

A Codex skill for code-authored videos and narrated, task-based application guides. It brings together real-app workflow capture, storyboarding, visual direction, narration-led timing, independent review, and verified delivery.

## Download and install

[Download code-animation 0.1.0-alpha.6](https://github.com/pizzapalmito/code-animation/releases/download/v0.1.0-alpha.6/code-animation-0.1.0-alpha.6.zip).

Extract the `code-animation` folder into your Codex skills directory, usually `~/.codex/skills/` (Windows: `%USERPROFILE%\.codex\skills\`). Back up an existing installation before replacing it, then open a new chat.

The skill is also available as readable source in [code-animation/](code-animation/). See [SHARING.md](SHARING.md) for dependency and installation notes. Rendering tools, companion skills, voice models, and application files are not bundled.

## Use

> Use $code-animation to create a task-based guide for my app using the approved SBM walkthrough preset, with narration and an offline video library.

The preset provides a polished 2D real-app walkthrough at 1080p30, calm narration, focused camera and pointer movement, and short typing sequences when requested. It adapts to your app's actual branding, roles, and verified workflows.

For another kind of video, specify your subject, visual style, 2D/3D choice, frame rate, duration, and audio preference. The skill preserves your choices and uses a representative 20-second approval sample before expanding a longer film. An unchanged approved sample can be reused.

## Included

- [Skill entrypoint](code-animation/SKILL.md)
- [Task-based app-guide workflow](code-animation/references/task-based-app-guides.md)
- [Approved walkthrough preset](code-animation/references/approved-walkthrough-preset.md)
- [Planning worksheet](code-animation/assets/task-guide-plan.md)
- [Production and packaging checks](code-animation/references/app-guide-production-checks.md)
- Dependency preflight, shot planning, and independent film review references

The workflow uses real application states and persisted results where available. It labels unverified steps rather than inventing successful behavior. Offline libraries can include search, filters, steps, transcripts, captions, and playback controls.

## Dependencies and scope

HyperFrames is the default renderer; existing project engines and explicit alternatives are respected. Production requires the selected engine and its runtime dependencies. Read [the preflight guide](code-animation/references/hyperframes-preflight.md) before rendering. Install the relevant companion skills described in the entrypoint; they are referenced, not included in this repository. Creative methods reference [Barty-Bart motion-graphics](https://github.com/Barty-Bart/motion-graphics) and the separately installed Huashu art-motion library.

The SBM workflow is a documented accepted reference, not a bundled app or video. New applications require their own authorized access, real workflow verification, and asset licensing checks. No app database, credentials, private captures, or voice models are included.

## Version and verification

Current version: **0.1.0-alpha.6**. [Version policy](VERSIONING.md) and [changes](CHANGELOG.md).

The skill passed its structural validator, local-reference checks, and an independent scenario review. The release ZIP passed integrity and byte-comparison checks. These checks do not certify rendering dependencies or workflows on another machine.
