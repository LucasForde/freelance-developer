# Inga Forde Photography Website Development Plan

This document tracks implementation order, verification and approval gates. The product requirements remain authoritative in `brief.md`; the website repository's `README.md` documents operational commands and repository-specific workflow.

Last updated: 18 August 2026

## Milestone 1: Foundation

Status: Complete

Completed on 18 August 2026.

Deliverables:

- Scaffold the Astro and TypeScript project in `C:\GitHub\ingaforde.co.uk`.
- Establish typed gallery content schemas for the six confirmed galleries.
- Add a minimal shared layout and global CSS foundation without pre-empting the final art direction.
- Configure production-root and `/staging` build modes.
- Add local development, type-checking, build and preview commands.
- Preserve the existing production holding page outside the Astro build until launch is approved.

Verification:

- Dependency installation completes with a committed lockfile.
- Astro content and TypeScript checks pass.
- Production and staging builds complete locally.
- The staging build uses `/staging` for internal asset and page paths.
- No deployment occurs.

## Milestone 2: Image-Pipeline Proof

Status: Complete

Completed on 18 August 2026.

Completion record:

- Generated 96 proof derivatives from six representative sources.
- Produced 32 files in each of AVIF, WebP and JPEG for the proof comparison.
- Confirmed the 970-pixel Families source was not enlarged and that intrinsic widths were retained as final candidates.
- Confirmed derivatives preserve aspect ratio, carry a standard sRGB output profile and contain no EXIF, XMP or IPTC payload.
- Flagged the three proof sources without embedded profiles for explicit colour review and documented the wider set of 30 untagged sources.
- Created an ignored local comparison page at `C:\GitHub\ingaforde.co.uk\.image-proof\comparison.html`.
- Lucas approved the proof comparison, encoder settings and sRGB working assumption for the current untagged sources.
- Generated 1,866 public derivatives from all 102 source photographs: 622 AVIF, 622 WebP and 622 JPEG files, totalling 436.8 MB.
- Reconciled all six gallery counts and confirmed the manifest matches every generated path and byte size with no missing, extra or duplicate files.
- Confirmed no derivative exceeds its source dimensions, the largest public file is 2.87 MB and no private source path is present in the manifest or build output.

Deliverables:

- Implement a local Sharp/libvips preparation script.
- Read the private source directory through documented local configuration.
- Generate proof derivatives from a representative set covering documentary, landscape, macro, portraiture, low-resolution and untagged sources.
- Produce AVIF, WebP and JPEG candidates without enlargement.
- Add intrinsic source width as the final candidate where it falls between configured widths.
- Convert tagged sources to sRGB, flag untagged sources for visual approval and strip private metadata from public output.
- Generate a machine-readable manifest containing source classification, dimensions and derivative paths.

Verification:

- Compared proof images at intended display size and 100% inspection.
- Confirmed natural aspect ratios and expected dimensions across the complete generated collection.
- Confirmed low-resolution sources are not enlarged.
- Confirmed generated files contain no EXIF, GPS, XMP or IPTC data and include the standard sRGB output profile.
- Recorded the approved Sharp/libvips, resize and encoder settings in the brief and repository runbook.
- Passed Astro content and TypeScript checks plus production-root and `/staging` static builds using the completed public collection.

Approval gate:

- Satisfied on 18 August 2026: Lucas approved the working colour assumption for the current untagged images and the final JPEG, WebP and AVIF settings before completion of full derivative generation.

## Milestone 3: Site Structure

Status: Complete

Completed on 18 August 2026.

Completion record:

- Added the shared site header, primary navigation, current-section treatment, skip link, breadcrumb navigation and footer.
- Added base-path-aware route and image helpers used by both production-root and `/staging` builds.
- Implemented Home, Photography, Documentary, Portraiture, Biography and Contact pages.
- Implemented all six gallery routes from the typed gallery collection and generated image manifest rather than duplicating gallery page code.
- Added responsive AVIF, WebP and JPEG picture markup with accurate intrinsic dimensions and `sizes` values.
- Kept the numbered manifest order as the documented provisional image order; content entries can override order and add alt text, captions, dates, locations and credits later.
- Marked homepage and cover-image choices plus unfinished biography copy clearly as provisional in source.
- Kept the enlarged viewer and its interaction decisions out of this milestone for implementation in Milestone 4.

Deliverables:

- Build the shared header, navigation, layouts and current-page states.
- Implement Home, Photography, Documentary, Portraiture, Biography and Contact routes.
- Implement the six galleries: Kalk Bay, Beauty Queen of Leenane, Landscape, Macro, Families and Women.
- Generate gallery pages from structured content rather than duplicating page code.
- Use temporary copy only where the final content has not yet been supplied, and label it clearly in source.

Verification:

- Astro content and TypeScript checks pass with zero errors, warnings or hints across 21 source files.
- Production-root and staging-base builds each generate the same 12-page route structure.
- An automated rendered-output audit resolved 2,224 internal links, assets and responsive-image candidates in each build with no failures.
- Every page contains one main landmark, one primary heading, primary navigation and a keyboard-accessible skip link.
- Breadcrumbs and current-section navigation make the site hierarchy explicit.
- Gallery output counts reconcile to all 102 prepared photographs: 7 Beauty Queen of Leenane, 18 Kalk Bay, 14 Landscape, 45 Macro, 7 Families and 11 Women.
- Every staging URL and image candidate is prefixed with `/staging/`; all staging pages have the matching canonical URL and `noindex, nofollow` metadata.
- No deployment occurred.

## Milestone 4: Gallery Viewer

Status: Complete

Completed on 18 August 2026.

Completion record:

- Added PhotoSwipe 5.4.4 as the approved progressively enhanced gallery viewer.
- Converted all 102 gallery photographs into accessible direct links with intrinsic viewer dimensions and responsive JPEG candidates.
- Added large, labelled previous and next controls with directional pointer-following treatment and generous touch-width side regions.
- Added a restrained horizontal transition for button and arrow-key navigation while keeping opening, closing and zoom animations disabled.
- Preserved PhotoSwipe swipe navigation and limited preloading to adjacent photographs.
- Added an unobtrusive position indicator, close control and conditional caption area.
- Kept each photograph's natural aspect ratio and fitted it within the available viewport.
- Moved focus into the modal viewer and explicitly restored it to the originating gallery link without changing scroll position.
- Kept direct image links as a non-JavaScript fallback.

Deliverables:

- Integrate and customise PhotoSwipe 5.
- Add large, labelled previous and next interaction regions with directional pointer treatment.
- Support swipe, generous touch targets, arrow keys, Escape, focus trapping and focus restoration.
- Restore the originating gallery position where practical.
- Load the selected image promptly and preload no more than useful adjacent images.
- Disable unnecessary opening, closing, zoom and drag animations.
- Respect `prefers-reduced-motion`.

Implemented defaults:

- Enlarged photographs do not modify the URL or browser history.
- Galleries do not loop.
- Captions and supplied date, location or credit information appear only when present in gallery content.

Verification:

- Tested opening and closing the viewer in the Codex in-app browser with no current console errors.
- Tested the large next control, keyboard right-arrow navigation and Escape-to-close behaviour.
- Confirmed the first and final photographs expose only the available navigation direction.
- Confirmed focus moves inside the dialog, remains trapped there and returns to the originating photograph on close.
- Confirmed the URL and gallery scroll position remain unchanged after viewer navigation and close.
- Checked a 390 × 844 viewport: the image fits within the dialog and the active side tap region is 70 pixels wide by 728 pixels high.
- Confirmed production-root and staging-base builds pass with zero Astro diagnostics and generate all 12 routes.
- Confirmed all 102 viewer links and responsive viewer source sets are present.
- Resolved 2,960 internal route, asset, thumbnail and viewer-image candidates in the staging build with no failures.
- Confirmed the two deferred viewer JavaScript chunks total 75.3 KB before transfer compression.
- No deployment occurred.

## Milestone 5: Visual Design and Content

Status: In progress

Deliverables:

- Establish the approved typography, white background, text colour and spacing scale.
- Select landing-page and gallery covers; the homepage will remain image-free unless a later approved direction changes that decision.
- Complete Home, Biography and Contact content.
- Add approved project copy, captions, credits and alternative text.
- Apply the final responsive gallery-overview composition using small, uncropped thumbnails centred within consistent grid cells.

Progress recorded on 18 August 2026:

- Replaced the warm scaffold styling with a pure-white, sans-serif and more restrained visual system after reviewing the approved Nadav Kander reference.
- Removed the provisional large homepage image and constrained every other non-viewer photograph to a small thumbnail treatment.
- Added deterministic collection and gallery grids with consistent column counts per breakpoint and centred, aspect-ratio-preserving thumbnails.
- Extended the desktop previous/next viewer controls across the full left and right halves of the viewport and replaced the former circular pointer follower with locally defined directional cursor artwork.
- Kept touch controls narrower so PhotoSwipe's central swipe surface remains available.
- Confirmed the revised Astro source passes type and content checks and builds successfully; final content, typography decisions and the Milestone 5 approval gate remain open.

Approval gate:

- Lucas approves the principal desktop and mobile visual direction before final polish is applied across every page.

## Milestone 6: Quality and Staging

Status: Pending

Deliverables:

- Complete responsive, keyboard, touch, accessibility and reduced-motion checks.
- Verify image loading, layout stability, public metadata and output size.
- Add page titles, descriptions, canonical URLs, social metadata, sitemap, robots rules and a custom 404 page.
- Audit the finished artefact for private originals, unexpected large files and unwanted metadata.
- Prepare the GitHub Actions deployment workflow.

Approval gate:

- Deploy to `https://ingaforde.co.uk/staging/` only after Lucas explicitly approves the deployment.

## Milestone 7: Review and Launch

Status: Pending

Deliverables:

- Address approved staging feedback.
- Complete a final content, accessibility, image-quality and link check.
- Record any accepted limitations or deferred work.
- Prepare the root production artefact and rollback notes.

Approval gate:

- Replace the production holding page only after Lucas explicitly approves launch.

## Outstanding Inputs

These do not block Milestones 1 and 2:

- Preferred public name or wordmark.
- Homepage and cover-image selections.
- Final project, biography and introductory copy.
- Image titles, captions, dates, locations, credits and alternative text.
- Typography and exact colour choices.
- Viewer URL, looping and caption decisions.
- Copyright, privacy, analytics and browser-support decisions.
