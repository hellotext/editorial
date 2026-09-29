# Changelog

## 2026-09-29 — Automatic isolated Chrome capture

Prefer a dedicated headless Chrome profile for fictional local application
screenshots. Capture the real compositor as a Display P3 PNG at 2× or more,
and validate the exact local page, test account, viewport, density and ICC
profile before accepting each image. This route avoids repeated macOS window
selection; the ScreenCaptureKit picker remains a fallback for a concrete
capture failure. Genuine compositor rendering at a verified 2× density also
meets the source-resolution requirement without a physical Retina window.

## 2026-09-28 — Persistent window selection for capture batches

Select one fictional Chrome window with `SCContentSharingPicker` per native
macOS batch, then run planned screenshots from that retained selection. Verify
the window identity, bounds, page and demonstration account for every shot;
stop on a mismatch without enumerating or switching to another window.

## 2026-09-28 — Article-wide visual coverage

Review every significant Help Center step, choice, report panel and result for
a useful interface image. Help guides spanning several views or stages
normally use complementary screenshots; document why one or none is enough.
Keep useful captures that cannot yet be made as pending visual work rather
than marking the article complete. Judge images in the full rendered article
without applying a fixed image quota.

## 2026-09-27 — Capture layout and correction checks

Verify the page's actual viewport, zoom and native captured layout before
treating a large PNG as a desktop screenshot. Inspect the saved figure for the
complete intended KPI row, clean crop, locale, synthetic data and consistent
article-stage presentation. Illustrative demonstration reports require green
KPI comparisons from real calculations over coherent fictitious source data.
Keep neighboring prose below figures and inline icons at an appropriate text
scale. Record reader corrections in the article work log and add reusable
lessons to this shared guide.

## 2026-09-26 — Cursor-free screenshot default

Capture screenshots without a pointer by default. A visibly enlarged pointer
may appear only to highlight the clickable button or link named in the step,
with its tip on the target and no label obscured. Inspect saved pixels because
remote-control overlays may survive system cursor-hiding settings.

## 2026-09-25 — Static screenshot figures

Screenshots now render as non-interactive figures without image links, new-tab
controls or enlargement icons. Authors still retain the native full-resolution
PNG and provenance with the consuming article and verify inline readability at
desktop and mobile widths.

## 2026-09-25 — Shared editorial foundation

Extracted the established Resources authoring and capture guidance into one
consumer-independent source. Added Help-specific step placement, pointer
annotation, capture provenance and a reusable agent entrypoint. The application
continues to own the renderer and Help exporter; each publishing project owns
its articles and assets. Screenshot and message authoring requirements remain
in force. Initial version: v1.0.0.
