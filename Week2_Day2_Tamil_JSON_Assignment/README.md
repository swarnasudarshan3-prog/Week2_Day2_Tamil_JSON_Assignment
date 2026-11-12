# Week 2 Day 2 — Tamil Visuals with JSON Prompting

## Scene
Margazhi kolam in a Karaikudi Chettinad courtyard, Tamil Nadu. The home has early-20th-century Chettinad architectural features, and the scene is set in the present day. The subject wears a Kanchipuram silk sari and makes a rice-flour kolam on Athangudi-style tiles.

## Comparison of generated outputs

| File | Template source | Deliberately edited fields | What to observe |
| --- | --- | --- | --- |
| `image_1_base_dawn.png` | `tamil_prompt.json` | None | Wide courtyard scene in cool dawn light |
| `image_2_golden_hour.png` | `image_2_golden_hour.json` | `setting.time_of_day`, `lighting` | Warmer light and longer shadows |
| `image_3_close_up.png` | `image_3_close_up.json` | `camera.shot` | Tighter emphasis on hand and kolam |
| `video_5s_camera_push.mp4` | `video_prompt.json` | Added `motion` | Five-second digital camera push-in on base image |

The JSON files keep all other intended fields unchanged. Image-generation models can still change incidental details (such as the precise sari shade, person or architecture) even when fields are held constant. These images therefore demonstrate prompt controls, **not** exact pixel-level subject consistency.

## Video production note
This MP4 is a five-second **camera-motion video made from the base generated image** using a digital slow zoom. It is not a fully AI-generated moving-subject video. Its `motion.subject_motion` specifies near-stillness to avoid misrepresenting subject animation. To make a fully generated video later, paste `video_prompt.json` into a video-generation tool.

## Validate JSON (Python)
```bash
python -m json.tool tamil_prompt.json > nul
python -m json.tool image_2_golden_hour.json > nul
python -m json.tool image_3_close_up.json > nul
python -m json.tool video_prompt.json > nul
```
On macOS/Linux, substitute `/dev/null` for `nul`.

## Submission
Upload this folder to a **new** GitHub repository (for example `Week2_Day2_Tamil_JSON_Prompting`). Include the images, video and JSON files. Share the repository URL in WhatsApp and post the set in the training community. This work is separate from the Day 1 Meal Plan repository.
