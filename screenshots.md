# Screenshot capture standard


**Established — 2026-09-20.** All new screenshots, including review captures,
use native Retina resolution and Display P3. The standard covers reusable
editorial assets, one-off Action Text uploads, Help exports and gallery
examples. Existing lower-quality assets need a fresh capture when revised.

Determine the largest intended display width in CSS pixels before capture.
Render at least two source pixels per displayed CSS pixel; prefer three for
editorial assets. For example, an image displayed at up to 800 CSS pixels wide
needs at least 1600 source pixels and preferably 2400. A 5K display does not
require every image to be 5120 pixels wide: the relevant value is its actual
display size and pixel density. Keep the intended layout and readable text
size while increasing raster density, rather than widening the interface to
fit more content. Resampling or upscaling an existing bitmap does not count as
a higher-resolution capture.

Capture from a color-managed Display P3 surface and save a genuine lossless
PNG with its Display P3 ICC profile embedded. Preserve that profile through
cropping, attachment handling, Help export and any image optimization. A
`.png` extension is not proof that the encoded image is PNG. Avoid JPEG for
interface text and controls. Do not merely assign a P3 profile to sRGB pixel
values: that changes their meaning. A color-managed sRGB-to-P3 conversion can
preserve appearance but cannot recover colors already clipped to sRGB and
must not be described as a native P3 capture. If the capture tool cannot
preserve wide gamut, record the limitation and use a suitable capture route
before treating the asset as compliant.

Wait for fonts and images to finish loading, use deterministic demonstration
data and exclude unrelated UI. Capture only the relevant interface, retaining
the surrounding context necessary to understand it. Keep captions and message
examples as accessible HTML instead of baking them into a screenshot.

Prepare the demonstration data before capturing a report. Populate the actual
source records used by its calculations so the selected period, KPI cards,
chart and breakdown agree with one another. Use enough dated records to show a
readable, plausible trend across the displayed period and enough relevant
categories to make the chosen comparison useful. Avoid empty panels, isolated
spikes caused only by sparse fixtures, repeated identical values, and metrics
cut off by a narrow viewport. Inspect the complete report at its intended
capture size; add only the missing synthetic records or choose a more useful
period before taking the image. Keep the underlying calculations and units
truthful. Do not redraw, smooth or replace chart pixels after capture to make
the results look better.

Verify chart readiness with the exact request made by the interface, including
the date picker's start and end parameters, time zone and filters, through the
backend presenter that renders the report. Ad hoc full-day timestamp queries
can produce different counts and category shares from the visible report. In
the isolated demonstration account, add only the missing fictitious source
records, then recheck the displayed KPI cards, trend and breakdown until they
are consistent and useful at the selected period.

Use an isolated demonstration account and verify the database or account
identity before adding records. Complete only the fictitious profile fields
needed to explain the screen. Keep demonstration contacts non-deliverable and
automations inactive, and never send a campaign or message for a screenshot.
Record the fixture source, selected period, filters and relevant data counts
with the capture provenance so another editor can reproduce the state. Describe
the values as demonstration data in the figure's accessible context; they are
not evidence of real customer outcomes.

For a card or panel, leave a modest, balanced margin of genuine application
background around its complete border and shadow when the interface allows it.
Keep the UI's real internal spacing; text and controls must not touch the image
edge. Judge this margin at the image's intended size in the article, not only
at native pixel size. This space inside the captured image is separate from the
figure stage's outer padding. Do not add a fabricated blank canvas or wide empty
gutters to the PNG to simulate it; adjust the viewport or recapture instead.

Before adding or replacing an asset:

1. Inspect the file signature, actual pixel dimensions and embedded ICC profile
   with an image metadata tool. On macOS, use `file` and
   `sips -g format -g pixelWidth -g pixelHeight -g profile <path>`.
2. Check the source dimensions against the largest intended CSS display size.
   Record the capture route, logical size, source size, density, date and color
   provenance with the asset's documentation.
3. Set catalog `width` and `height` to the actual source dimensions. Preserve
   the aspect ratio, and keep the original PNG with the consuming project for
   provenance. Render screenshots as static images: no image link, new-tab or
   new-window target, or open/enlarge control.
4. Review the rendered figure in Resources and Help at desktop/mobile widths,
   including text sharpness and readability on a Retina display. If essential
   labels become too small inline, improve the crop or adjacent explanation
   instead of relying on an enlargement link. Verify copied/exported assets
   retain their format and color profile.

## Pointers and step annotations

Capture screenshots without a pointer by default, including original and review
captures. Hide the system cursor, move any automation pointer outside the crop,
and inspect the saved pixels: a remote-control pointer overlay can remain even
when the capture API hides the system cursor. Never leave a pointer over a
metric, label, field value or unrelated part of the interface.

Show a pointer only when deliberately highlighting the clickable button or link
that the reader should use. Make it visibly larger than the normal pointer at
the article's display size, and place its tip over that button or link without
covering its label. If it cannot fit clearly on the target, leave it out and
name the control in the prose or a callout. Keep pointer appearance and scale
consistent across the article. Do not imply that a click, save or successful
result occurred merely by showing a pointer.

When a capture route omits the pointer, a separately authored pointer overlay
may be used as an editorial annotation. Preserve the untouched capture, record
the overlay and target coordinates, and check that compositing preserves native
resolution and the genuine color profile. Use this only for the same intentional
button-or-link exception; record pointer absence explicitly otherwise. Never
alter application text, controls, values or results to manufacture evidence. Do
not use generative reconstruction of interface pixels. An annotation cannot
repair an inadequate source capture.

One numbered callout can identify a control when a pointer alone is ambiguous.
Do not add decorative arrows or rely on color alone. The prose must name the
control and action, and alternative text must explain what matters in the image.

## Capture readiness

Before a batch, prove the selected tool produces a compliant file. A browser's
reported device-pixel ratio, filename or attractive preview is not evidence of
actual output density or gamut. Check the bytes and profile of the saved file.
If a tool emits JPEG, downsizes the image or drops its ICC profile, record that
limitation and prepare the article until a supported capture route is available.
Do not repeatedly produce unusable assets or claim visual review is completed
from metadata alone.

Use a designated demonstration account or clearly documented fixture. Account
access details stay in the consuming project's local work record, not this
public guide. A test-account label alone does not establish that every displayed
contact is safe to publish. Exclude contact identifiers, conversations and other
unnecessary records from the crop; use deliberately prepared demonstration data.
Do not modify real records to make a screenshot look cleaner.

## Provenance

Keep an original and any cropped/annotated derivative in the consuming project,
with a record based on [the capture template](templates/capture-record.json).
Record the actual route/state, UI locale, date, tool, logical viewport, source
pixels, intended maximum CSS size, ICC verification, transformations and target
control. Avoid credentials or private record identifiers in publishable records.

Mark a capture verified only after file inspection and article rendering at
both desktop and mobile sizes. Check the built or served file too: image
optimization and publishing must preserve the verified asset. If any check is
pending, record it as pending rather than substituting an estimated value.
