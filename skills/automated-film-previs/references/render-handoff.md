# GPT Image and Seedance Render Handoff

## Image stage

1. Generate one neutral character sheet per character: front, profile, rear three-quarter, full body, and face close-up.
2. Generate an establishing plate, reverse angle, and clean plate per location.
3. Generate each shot's first frame from all relevant character and environment references. Create a last frame for complex continuity or transformation shots.
4. Save the prompt, model, response identifier, reference hashes, and output path.
5. Compare each result with the production bible and entry/exit state. Regenerate failed keyframes before video.

## Seedance prompt order

Write one English prompt per shot in this order:

```text
IDENTITY LOCK
ENVIRONMENT LOCK
SHOT AND CAMERA
ACTION TIMELINE
DIALOGUE AND AUDIO
CONTINUITY ENTRY/EXIT STATE
NEGATIVE CONSTRAINTS
```

Use concrete time phases such as `0.0–1.0s`, `1.0–3.5s`, and `3.5–5.0s`. Describe one choreography chain per short clip. Avoid asking the model to invent edits inside one shot.

## Rendering

- Use model `dreamina-seedance-2-0-mini-260615` when it is available to the BytePlus account.
- Use 4–15 seconds per provider task and the project aspect ratio.
- Request 720p for drafts unless the user specifies another supported resolution.
- Render linked continuity shots sequentially. Independent locations may use limited parallelism.
- Download outputs before signed URLs expire.
- Extract the last frame and validate it against the shot exit state and next shot entry state.
- Record provider task ID, model, settings, request time, result URL, local path, and retry lineage.

## Audio and final QC

Prefer post-produced audio when dialogue accuracy matters. Lock English dialogue before generating Vietnamese subtitles. Verify final duration, frame size, frame rate, audio channels, subtitle timing, black frames, frozen frames, duplicate shots, and abrupt continuity breaks.

