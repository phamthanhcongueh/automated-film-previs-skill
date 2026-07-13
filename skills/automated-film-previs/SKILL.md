---
name: automated-film-previs
description: Plan consistent AI-generated short films and trailers from an idea or script. Use when Codex needs to create a production bible, Vietnamese production script with English character dialogue, shot list, three-column graphite storyboard, wooden-mannequin action sheets, continuity review, GPT Image 2 keyframe prompts, or a Seedance 2.0 Mini render package. Require storyboard and action-sheet approval before paid video rendering.
---

# Automated Film Previs

Convert an idea into reviewable production artifacts before generating video. Treat approved JSON and images as the source of truth; never rely only on conversation memory.

## Language contract

- Write scene action and production notes in Vietnamese.
- Write spoken character dialogue in English.
- Create Vietnamese subtitles only as translations of locked English dialogue.
- Write generation prompts and in-panel camera annotations in English.
- Do not create two independent bilingual scripts.

## Workflow

1. Normalize the brief: duration, aspect ratio, genre, rating, visual style, dialogue density, references, providers, and delivery resolution.
2. Create `production_bible.json` before individual shots. Lock character identity, costume, props, environment geography, lighting, palette, screen axis, and forbidden drift.
3. Write `script.json` with Vietnamese action, sparse English dialogue, Vietnamese subtitle translations, and explicit scene timing.
4. Create `storyboard.json`. Give every shot a duration, lens impression, shot size, angle, action, camera movement, entry state, exit state, and asset IDs.
5. Create a storyboard sheet for the complete edit. Use the visual system in [storyboard-system.md](references/storyboard-system.md).
6. Create action sheets only for complex motion: fights, stunts, chases, transformations, crowds, or interaction with moving vehicles.
7. Stop at the previs approval gate. Present the storyboard and action sheets; do not render video until the user approves them.
8. After approval, create consistent character sheets, environment plates, and shot keyframes with GPT Image 2 or the available built-in image generator.
9. Run continuity checks on every keyframe. Reject identity, costume, prop, geography, screen-direction, or entry/exit mismatches.
10. Build a Seedance 2.0 Mini shot package. Follow [render-handoff.md](references/render-handoff.md). Render shots sequentially when continuity chains them.
11. Assemble picture, English dialogue, ambience, music, sound effects, and Vietnamese subtitles; then run visual, audio, timing, and resolution QC.

## Required approval gates

Do not silently skip these gates:

- Gate A: brief and production bible.
- Gate B: script and timing.
- Gate C: storyboard and action sheets.
- Gate D: character/environment assets and keyframes.
- Gate E: paid video render and retries.
- Gate F: final master.

User approval of a later gate implies approval of earlier unchanged gates. A revised artifact returns only affected downstream stages to review.

## Action design

Break complex choreography into anticipation, initiation, contact, reaction, recovery, and outcome. Use one readable action per panel. Establish geography before close impacts. Preserve the 180-degree axis unless an axis-crossing shot is explicitly shown.

For team combat, design cause-and-effect cooperation instead of isolated attacks. Track who creates the opening, who exploits it, where each weapon ends, and how both characters recover.

## Deliverables

Use the schemas and file layout in [production-schema.md](references/production-schema.md). At minimum produce:

```text
outputs/{project_id}/
  production_bible.json
  script.json
  storyboard.json
  action_sheets/
  keyframes/
  render_manifest.json
  subtitles_vi.srt
  final_master.mp4
```

For a previs-only request, stop after `storyboard.json` and `action_sheets/`.

## Quality rules

- Make every action drawable and physically legible.
- Keep character and location IDs stable across all artifacts.
- Ensure shot durations sum to the requested runtime.
- Treat output resolution as a verified property, not a prompt wish.
- Record model, settings, prompt, reference hashes, provider task ID, output path, and retry lineage.
- Never treat placeholder media as a successful production asset.
- Never retry a paid render without approval when the retry changes cost.
- Report uncertainty or provider limitations plainly.

