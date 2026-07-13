# Automated Film Previs Skill

A Codex skill for planning consistent AI-generated short films before paid video rendering.

It turns an idea or script into:

- A production bible that locks characters, costumes, props, locations, lighting, and screen direction.
- Vietnamese action and production notes with English spoken dialogue.
- A timed shot list and complete storyboard.
- Three-column graphite action sheets using wooden mannequins, motion arrows, and camera notes.
- GPT Image 2 character, environment, and keyframe guidance.
- A continuity-checked Seedance 2.0 Mini render manifest.
- Explicit approval gates before image generation, paid video renders, retries, and final mastering.

## Install

Copy the skill folder into your Codex skills directory:

```bash
cp -R skills/automated-film-previs "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then invoke it with:

```text
Use $automated-film-previs to turn my film idea into a production bible,
English-dialogue script, storyboard, action sheets, and an approved render plan.
```

## Review-first workflow

The skill stops after storyboard and action-sheet creation unless the user approves the previs. It then creates keyframes, performs continuity checks, and prepares shot-level Seedance requests. Paid rendering and retries require approval.

## Included example

`examples/dustfall/` contains a 12-panel trailer storyboard and two nine-panel fight choreography action sheets.

## Skill package

The installable package is located at [`skills/automated-film-previs`](skills/automated-film-previs).

