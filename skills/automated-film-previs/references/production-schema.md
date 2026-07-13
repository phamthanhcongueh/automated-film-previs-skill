# Production Schema

## Production bible

```json
{
  "project": {
    "project_id": "slug",
    "title": "Title",
    "target_duration_sec": 60,
    "aspect_ratio": "16:9",
    "delivery_resolution": "720p",
    "dialogue_language": "en",
    "production_notes_language": "vi"
  },
  "characters": [{
    "character_id": "CHAR_A",
    "identity_lock": "stable visible traits",
    "costume_lock": "garments and colors",
    "prop_ids": ["PROP_SWORD_A"],
    "voice_profile": "English voice and accent",
    "forbidden_drift": ["hair", "costume", "body proportions"]
  }],
  "locations": [{
    "location_id": "LOC_01",
    "geography": "doors, landmarks and spatial relations",
    "lighting": "direction and quality",
    "screen_axis": "A to B",
    "reference_asset_ids": []
  }],
  "props": [{
    "prop_id": "PROP_SWORD_A",
    "owner_id": "CHAR_A",
    "hand": "right",
    "state_timeline": []
  }]
}
```

## Script scene

```json
{
  "scene_id": "SC01",
  "slugline": "EXT. DESERT PLANET - DAY",
  "location_id": "LOC_01",
  "time_range_sec": [0, 15],
  "action_vi": ["Mô tả hành động bằng tiếng Việt."],
  "dialogue_en": [{
    "dialogue_id": "D001",
    "speaker_id": "CHAR_A",
    "text": "Contact. Three o'clock.",
    "emotion": "controlled"
  }],
  "subtitle_vi": [{"dialogue_id": "D001", "text": "Có địch. Hướng ba giờ."}]
}
```

## Storyboard shot

```json
{
  "shot_id": "SH010",
  "scene_id": "SC01",
  "duration_sec": 5,
  "character_ids": ["CHAR_A", "CHAR_B"],
  "location_id": "LOC_01",
  "prop_ids": ["PROP_SWORD_A"],
  "shot_size": "MEDIUM WIDE",
  "angle": "LOW ANGLE",
  "lens_impression": "28mm",
  "action_vi": "Hành động cụ thể, có thể vẽ được.",
  "camera_movement": "TRACK RIGHT",
  "dialogue_ids": [],
  "entry_state": "positions, poses, prop states",
  "exit_state": "positions, poses, prop states",
  "needs_action_sheet": true,
  "reference_asset_ids": []
}
```

## Render manifest shot

```json
{
  "shot_id": "SH010",
  "provider": "byteplus",
  "model": "dreamina-seedance-2-0-mini-260615",
  "duration_sec": 5,
  "resolution": "720p",
  "ratio": "16:9",
  "first_frame": "keyframes/SH010-first.png",
  "last_frame": null,
  "prompt_file": "prompts/SH010.txt",
  "status": "awaiting_approval",
  "task_id": null,
  "retry_of": null
}
```

