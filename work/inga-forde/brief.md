# Inga Forde Photography Website

## Project Summary

Create a modern, image-led photography portfolio website for Inga Forde. The site should feel calm, warm, spacious and gallery-like, allowing the photographs to dominate without decorative complexity.

The website does not require a CMS. Content and gallery changes can be maintained in the project source.

## Status

- Initial structure and visual direction confirmed.
- Reference-site preferences and gallery interaction requirements recorded.
- Technical stack, hosting target, development URL, contact method and image-handling direction confirmed.
- Final content, photography selections, brand assets, detailed visual design and launch arrangements are not yet confirmed.
- No price, timeline, deployment or ongoing-support commitment is recorded here.

## Confirmed Technical Direction

- Use Astro to generate a fully static website.
- Use TypeScript for content schemas, image metadata and interactive behaviour.
- Use plain CSS with custom properties; do not add a utility CSS framework without a later demonstrated need.
- Use typed, source-managed content rather than a CMS, database or server-side application.
- Use PhotoSwipe 5 as the starting point for the enlarged photograph viewer, customised to meet the interaction, accessibility and motion requirements in this brief.
- Host the finished static site on GitHub Pages at `https://ingaforde.co.uk/`.
- Publish the development review build at `https://ingaforde.co.uk/staging/` while retaining the production holding page until launch is approved.
- Use a direct email link to `ingamareeforde@gmail.com`; do not add a contact form or form-processing service.

## Site Structure

- Home
- Photography
  - Documentary
    - Kalk Bay
    - Beauty Queen of Leenane
  - Landscape
  - Macro
  - Portraiture
    - Families
    - Women
- Biography
- Contact

`Photography` should be an accessible submenu control in the primary navigation rather than a visual landing page. The submenu links directly to all six galleries. `Documentary` and `Portraiture` are submenu group labels rather than image galleries or card-based landing pages:

- Documentary leads to Kalk Bay and Beauty Queen of Leenane.
- Portraiture leads to Families and Women.
- Landscape and Macro remain direct galleries.

This produces six image galleries: Kalk Bay, Beauty Queen of Leenane, Landscape, Macro, Families and Women.

## Confirmed Visual Direction

- White background, or an imperceptibly off-white value if later visual testing requires it.
- Restrained, image-first presentation.
- Generous whitespace.
- Minimal interface that does not compete with the photographs.
- Present gallery-overview photographs as consistent square crops in a close, orderly grid with enough whitespace to keep the page calm.
- Keep landing-page cover photographs restrained and aligned with the other covers in their row.
- Do not use large page imagery outside the enlarged photograph viewer.
- Preserve the natural aspect ratios of photographs rather than forcing uniform crops in enlarged views.
- Avoid a long, scrolling project-index experience like Pieter Hugo's website.
- Do not use the visual or structural direction of Rhiannon Adam's or Daniel Meadows' websites.
- Do not use decorative animation, parallax, scroll reveals, autoplay carousels or other unnecessary movement.
- The only desired animation is the horizontal transition from one enlarged photograph to the previous or next photograph.

The exact typefaces, text colour, spacing scale and any accent colour remain to be selected after reviewing Inga's photographs and any existing identity material. The background direction is settled as white or visually indistinguishable from white.

## Reference Sites

### Nadav Kander

Reference: [nadavkander.com](https://www.nadavkander.com/)

Use as the primary interaction reference for enlarged photographs:

- The pointer indicates the available previous or next action with a directional arrow.
- The user can click a large left or right navigation region instead of locating a small button; each region should continue across its half of the viewer, from the photograph to the edge of the viewport.
- The enlarged photograph remains the focus of the screen.
- Use the site's restrained white canvas, small utility typography and generous whitespace as broad tonal references.

Do not copy the site's branding, assets or distinctive composition. Recreate only the underlying interaction principle in an original design appropriate to Inga.

### Laura Pannack

Reference: [laurapannack.com](https://laurapannack.com/)

- Do not use the homepage as a design reference.
- Use the gallery overview and individual enlargement experience as useful references for clarity, spacing and image presentation.

### Ryan Prince

Reference: [ryan-prince.com](https://www.ryan-prince.com/)

- Do not use a thumbnail carousel beneath enlarged photographs.
- Avoid a busy or layered enlargement interface.

## Gallery Overview Requirements

- Do not use image-card indexes for Photography, Documentary or Portraiture; navigation to the six galleries belongs in the Photography submenu.
- Each of the six image galleries should have a clean overview of its photographs.
- Begin each gallery page directly with its thumbnail grid beneath the primary navigation. Do not show breadcrumbs, a category eyebrow, a visible gallery title or a photograph count above the grid.
- Retain the gallery name in the document title and a visually hidden page heading so removing the visible header does not remove the page's accessible identity.
- The overview should make it easy to scan the collection without becoming visually busy.
- Use a deterministic CSS grid rather than masonry or independently sized rows.
- Show five equal square thumbnails per row on desktop. Reduce to three and then two columns where the viewport cannot support five usable targets.
- Use the same restrained gap between rows and columns: close enough to read as a coherent photographic set, with enough breathing room to keep the page calm.
- Generate a centred square crop for each overview thumbnail. The crop applies only to the overview; the enlarged photograph must retain its complete natural aspect ratio.
- Selecting a photograph should open a spacious, near-full-screen enlargement experience.
- Column count and spacing should respond to viewport size while staying consistent within each row.
- An enlarged photograph should return the visitor to the same gallery and, where practical, the same scroll position when closed.

## Source Image Inventory

The private high-resolution source images are held inside this development project at `work/inga-forde/hi-res-images/`. The directory contains local source material, is ignored by Git and must not be included in a public deployment.

The 102 JPEGs have been flattened into one directory and renamed according to the six confirmed image galleries:

- Beauty Queen of Leenane: `documentary-beauty-queen-of-leenane-01.jpg` to `documentary-beauty-queen-of-leenane-07.jpg` (7 images)
- Kalk Bay: `documentary-kalk-bay-01.jpg` to `documentary-kalk-bay-18.jpg` (18 images)
- Landscape: `landscape-01.jpg` to `landscape-14.jpg` (14 images)
- Macro: `macro-01.jpg` to `macro-45.jpg` (45 images)
- Families: `portraiture-families-01.jpg` to `portraiture-families-07.jpg` (7 images)
- Women: `portraiture-women-01.jpg` to `portraiture-women-11.jpg` (11 images)

The `documentary-` and `portraiture-` prefixes express the site hierarchy; they do not identify separate general image groups. Do not create standalone parent-page image groups unless new assets are supplied specifically for them. Documentary and Portraiture cards and hero areas should use explicitly selected images from the relevant child galleries without duplicating the source files.

`documentary-kalk-bay-18.jpg` was the exceptional 23,400 × 15,600 source image. Lucas resized the local copy to 5616 × 3744 for consistency with the other Kalk Bay photographs; the original is backed up elsewhere. The remaining source images do not require manual resizing solely for website use.

## Image Preparation and Delivery

### Private Sources

- Treat `hi-res-images/` as private build input, not public website content.
- Do not copy the directory into `public/`, the production document root or the deployed build.
- Do not commit these source files to Git.
- Source JPEG byte size does not affect visitor performance when the originals are never served. It may affect only local storage, image-processing time and build memory.
- Do not recompress source JPEGs merely to reduce their local byte size; avoid an unnecessary lossy generation before producing the final web derivatives.
- Keep the current filenames and aspect ratios unless Lucas explicitly approves another content change.

### Photoshop

- Use Photoshop only when a photograph needs a creative decision such as retouching, colour correction, an intentional crop or image-specific sharpening.
- Do not manually create every responsive size or thumbnail in Photoshop.
- If a source must be manually reduced, preserve its aspect ratio, convert it to sRGB, keep resampling enabled and use Photoshop's `Automatic` reduction method. `Bicubic Sharper (reduction)` is an acceptable alternative when visual inspection shows that it produces the better result.
- Do not use `Preserve Details 2.0` for reduction; it is intended primarily for enlargement.
- Pixels-per-inch metadata does not affect website display. Pixel dimensions are the relevant measurement.
- Inspect any manually resized photograph at 100% before accepting it.

### Automatic Derivatives

Use a build-time image processor capable of high-quality downsampling, controlled output quality and AVIF, WebP and JPEG output. Configure it to preserve aspect ratios and prevent enlargement.

The confirmed implementation direction is a local Sharp/libvips preparation script maintained with the website project. Configure Lanczos 3 reduction and explicitly enable `withoutEnlargement`; do not rely on defaults for the enlargement safeguard. The script should read the private source directory from documented local configuration rather than embedding a machine-specific absolute path in application code.

Generate only candidates used by the implemented layouts, omitting any candidate larger than its source:

- Gallery overview thumbnails: centred square crops at 320, 640 and 960 pixels in AVIF, WebP and JPEG.
- Landing-page and project covers: use the natural-aspect JPEG candidates shared with the viewer and let `sizes` select the appropriate file.
- Enlarged viewer images: natural-aspect JPEG candidates at 768, 1280, 1920, 2560 and 3200 pixels wide.
- Social-sharing images: a separately approved 1200 × 630 crop where required.

These widths are an initial implementation specification and may be refined after the final layouts are measured. Do not generate files simply because a nominal width exists; generate only candidates used by the implemented `srcset` and `sizes` rules.

When a source width falls between configured candidates, include its intrinsic width as the final candidate, up to the maximum required width. This avoids discarding usable source resolution merely because the next standard candidate would exceed the source. Never upscale an image to create that candidate.

- Generate overview thumbnails automatically from the same approved source image; do not maintain a separate manual thumbnail collection.
- Use the approved centred square crop for gallery-overview thumbnails. If an individual photograph later needs a different focal position, record that as an explicit image-specific crop decision rather than altering the source.
- Preserve each photograph's natural aspect ratio in landing-page covers and enlarged views.
- Create a dedicated art-directed cover crop only when the design genuinely requires one and Lucas has approved the crop.
- Convert sources with a reliable embedded colour profile to sRGB for public output.
- A metadata scan indicates that 30 current sources have neither an embedded ICC profile nor an EXIF sRGB declaration: all seven Beauty Queen of Leenane images, thirteen Macro images and ten Women images. Representative files from the affected groups were visually compared and Lucas approved treating the current untagged sources as sRGB for this build on 18 August 2026. This remains a documented working-profile assumption rather than evidence about the sources' original colour space.
- A standard sRGB output profile may be embedded where it improves reliable browser colour reproduction; it is useful colour information rather than private metadata.
- Remove GPS data and unnecessary EXIF or other private metadata from public derivatives.
- Use visual quality settings suitable for a photography portfolio rather than choosing compression solely for the smallest possible file.
- Visually compare representative portraits, macro photographs, landscapes, monochrome work and detailed documentary photographs before applying final encoder settings to the complete collection.

Lucas approved the representative proof comparison on 18 August 2026. The approved derivative settings are Sharp 0.35.3 with libvips 8.18.3, Lanczos 3 reduction, `withoutEnlargement: true` and `fastShrinkOnLoad: false`; JPEG quality 90 with mozjpeg and 4:4:4 chroma subsampling; WebP quality 86 with effort 5 and smart subsampling; and AVIF quality 65 with effort 5 and 4:4:4 chroma subsampling. Public derivatives are written with an sRGB ICC profile and without source EXIF, XMP or IPTC metadata. Revisit these values only through another representative visual comparison rather than changing them implicitly.

### Loading and Layout

- Use `srcset` and accurate `sizes` values so the browser selects an appropriate derivative for the rendered image slot and device pixel density.
- Include intrinsic width and height information so the browser can reserve the correct aspect ratio and avoid layout movement.
- Load the initial homepage or page-defining image eagerly when it is the page's primary visual.
- Lazy-load non-critical gallery images below the initial viewport.
- In the enlarged viewer, load the selected image promptly and preload at most the immediately adjacent images where testing shows a useful benefit.
- Never load all full-size viewer images when a gallery first opens.

### Build and Deployment Boundary

The required flow is:

```text
Private hi-res source
→ local or framework image processor
→ responsive AVIF/WebP/JPEG derivatives
→ finished website build
→ public host
```

- Deploy only the finished website and its generated derivatives.
- GitHub Actions cannot access the ignored private source directory. Generate the final responsive derivatives locally with the approved Sharp script, write a manifest containing their public paths and intrinsic dimensions, and commit only those public derivatives and the manifest to the website repository.
- Astro should consume the generated manifest to produce the required `<picture>`, `srcset`, `sizes`, width and height markup. The remote GitHub Actions build must not require the private source originals.
- Regenerate and visually review derivatives deliberately when photographs, widths, formats or encoder settings change; do not make every ordinary Astro build rewrite the complete derivative set.
- Before every production deployment, inspect the final build artefact and confirm that it contains no `hi-res-images/` directory, private source originals, unexpectedly large JPEGs or unwanted metadata.
- A generated derivative may retain a recognisable source-derived filename, but it should be emitted through the build pipeline rather than copied directly from the private source directory.

## Enlarged Photograph Viewer

### Desktop and Pointer Devices

- Divide the main viewer interaction area into large previous and next regions.
- Show an appropriate left- or right-pointing cursor according to the available action.
- Extend each pointer region across its full half of the viewer so the cursor and action remain available over the image and out to the viewport edge.
- Clicking the left region opens the previous photograph.
- Clicking the right region opens the next photograph.
- At the beginning or end of a gallery, do not display an action that is unavailable unless the gallery is deliberately configured to loop.
- Provide an unobtrusive close control.
- Support `Escape` to close and the left and right arrow keys to navigate.

The large click regions should be implemented as real, accessible controls with meaningful labels, even if their visible presentation is reduced to the cursor treatment.

### Touch Devices

- Support horizontal swipe navigation.
- Provide generous left and right tap regions as a fallback.
- Do not rely on hover or cursor behaviour.
- Avoid a persistent strip of thumbnails.

### Presentation

- Preserve each enlarged image's aspect ratio.
- Fit the photograph comfortably within the available viewport without obscuring important content.
- Keep captions and interface elements secondary to the photograph.
- A restrained position indicator such as `04 / 18` is acceptable.
- Use only a short horizontal slide when moving between photographs.
- Respect the user's reduced-motion preference; navigation must remain clear without animation.

## Homepage Direction

The homepage should be static, minimal and image-led. It should not use an autoplay carousel or the layout of Laura Pannack's homepage.

A likely direction is one carefully chosen opening photograph, Inga's name, a short description and clear routes into the Photography, Biography and Contact pages. The final composition and homepage photograph require approval after the assets have been reviewed.

## Navigation

- Keep the primary navigation simple and predictable.
- Use Photography as a submenu control rather than a link to a card-based portfolio index.
- Include direct submenu links to Kalk Bay, Beauty Queen of Leenane, Landscape, Macro, Families and Women; group the documentary and portraiture links under clear labels.
- The submenu must work by click, keyboard and touch and must not depend on hover. It should close with Escape and when focus or pointer interaction moves outside it.
- Ensure all navigation works with keyboard and touch input.
- Provide a clear current-page state.
- Keep gallery navigation separate from the site's primary navigation.

## Content Management

- No CMS is required.
- Prefer a simple, documented source structure for gallery metadata and image ordering.
- Keep adding, removing, reordering and captioning photographs straightforward for a developer.
- Do not add CMS dependencies, accounts, editor interfaces or third-party content services without a later confirmed requirement.

## Hosting and Deployment

- The canonical production URL is `https://ingaforde.co.uk/`.
- The development review URL is `https://ingaforde.co.uk/staging/`.
- Configure Astro's `site` value with the production origin.
- Use `/staging` as the staging base path and `/` as the production base path. Internal links and manually referenced public assets must remain base-path aware in both environments.
- Use a custom GitHub Actions workflow to assemble and deploy the GitHub Pages artefact. During development, it should contain the holding page at the root and the review build beneath `/staging/`.
- Apply `noindex, nofollow` metadata and a matching robots rule to the staging build. This discourages indexing but does not make staging private.
- Replace the holding page with the approved root build only when launch is explicitly approved.
- Configuring or running a deployment remains a separate approval step from local implementation and verification.

## Contact

- Provide a clear email link to `ingamareeforde@gmail.com` on the Contact page.
- A prefilled subject such as `Photography enquiry` is acceptable.
- Do not add a contact form, form provider, server function or personal-data submission workflow.

## Accessibility and Usability

- Use semantic navigation, links and buttons.
- Provide visible keyboard focus states.
- Give viewer controls meaningful accessible names.
- Trap and restore focus appropriately if the enlargement is implemented as a modal dialog.
- Support keyboard, pointer and touch navigation.
- Provide useful alternative text for meaningful photographs, with the wording agreed as part of content preparation.
- Maintain sufficient text and focus-indicator contrast against the white background.
- Do not disable browser zoom.

## Image Performance

- Follow the preparation, derivative, loading and deployment rules in `Image Preparation and Delivery`.
- Treat image quality and download size as jointly important: the photography must remain faithful while each visitor receives only the dimensions needed for their display context.
- Validate the chosen formats and quality settings visually and with a production build before treating the image pipeline as complete.

## Search and Sharing Basics

- Give each main page and photography section a descriptive URL, page title and meta description.
- Provide suitable social-sharing metadata and a selected preview image.
- Use a logical heading structure.
- Include an XML sitemap and appropriate robots configuration when the production URL is known.
- Do not promise search rankings.

## Content and Assets Required

- Inga's preferred public name or wordmark.
- Opening/homepage photograph.
- Final photograph selection for each of the six gallery overviews.
- Required gallery order and image order.
- Image titles, captions, dates, locations and credits where applicable.
- Project text for Kalk Bay and Beauty Queen of Leenane.
- Biography copy and portrait, if one is to be shown.
- Social profile links, if required.
- Copyright wording and the desired policy on image downloads.
- Favicon and social-sharing image.

## Decisions Still Required

- Exact typography, text colour and spacing scale.
- Whether the current non-looping gallery behaviour should be changed.
- Whether the current enlargement behaviour should be extended with unique bookmarkable or shareable URLs; it does not currently modify browser history.
- Whether the current caption policy should be changed; captions are currently shown only where content is supplied.
- Whether image protection measures such as disabled context menus or watermarks are wanted; these have usability costs and cannot prevent determined copying.
- Analytics and cookie requirements.
- Privacy, copyright and any other required policy content.
- Browser and device support expectations.

## Preliminary Acceptance Criteria

- All confirmed pages and photography sections are present and reachable.
- Photography is an accessible submenu control with direct links to all six galleries and no card-based index.
- Documentary groups Kalk Bay and Beauty Queen of Leenane within the submenu rather than using a separate image-card page.
- Portraiture groups Families and Women within the submenu rather than using a separate image-card page.
- Landscape and Macro are available as direct galleries.
- The interface uses a white or visually indistinguishable near-white background and restrained visual styling.
- Gallery pages use centred square thumbnail crops in a consistent five-column desktop grid.
- Gallery pages contain no visible breadcrumb trail, category label, gallery heading or photograph count above the grid.
- Gallery rows and columns use the same close, breathable gap; the grid reduces to three and then two columns on narrower screens.
- Thumbnail cropping does not affect the natural aspect ratio of enlarged photographs.
- Selecting a photograph opens an uncluttered enlarged view.
- Pointer users can navigate using half-viewport cursor-arrow regions that extend across the photograph to the viewport edge, without finding small previous or next buttons.
- Keyboard users can navigate and close the viewer.
- Touch users can swipe or use large tap regions.
- No thumbnail carousel appears below enlarged photographs.
- No animation is used apart from the restrained previous/next slide transition.
- The site does not depend on a CMS.
- Responsive images and gallery loading avoid unnecessarily downloading all full-size assets at once.

These criteria are provisional until the content and final visual design have been approved.
