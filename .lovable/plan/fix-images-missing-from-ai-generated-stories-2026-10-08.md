# Fix: images missing from AI-generated stories

## Root cause (confirmed)
The built-in demo story ships with bundled images, so it always shows pictures. AI-generated stories create their illustrations on the fly and save them to a backend storage area called `story-images` — but that storage area was never created in this project's backend (the original repo had it; the import didn't bring it over). Every image save fails, so new stories fall back to the styled placeholder.

## Fix
1. **Create the image storage area** in the backend (private bucket `story-images`, with access rules so the app can save images and read them back via secure links — matching how the code already works).
2. **Verify live**: generate a new AI story in the preview and confirm each chapter gets a real illustration, and that the demo story still shows its images.
3. **Check the failure display**: make sure that if image generation ever fails, the chapter shows the friendly placeholder instead of a broken image (the `ChapterImage` component already does this — will confirm).

## Technical details
- One database migration: `insert into storage.buckets` for `story-images` (private), plus `storage.objects` policies permitting authenticated inserts/reads scoped to the bucket.
- No changes to image-generation code needed — it already uses signed URLs and the correct bucket name.
- Verified gap via `storage.buckets` query (returned zero rows).
