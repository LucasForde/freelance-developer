# Inga Forde Photography Website

## Project Summary

Create a modern, image-led photography portfolio website for Inga Forde. The site should feel calm, warm, spacious and gallery-like, allowing the photographs to dominate without decorative complexity.

The website does not require a CMS. Content and gallery changes can be maintained in the project source.

## Status

- Initial structure and visual direction confirmed.
- Reference-site preferences and gallery interaction requirements recorded.
- Content, photography selections, brand assets, technical stack, hosting and delivery arrangements are not yet confirmed.
- No price, timeline, deployment or ongoing-support commitment is recorded here.

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

`Photography` should be a usable landing page as well as the parent navigation item for the portfolio. `Documentary` and `Portraiture` are also landing pages rather than image galleries in their own right:

- Documentary leads to Kalk Bay and Beauty Queen of Leenane.
- Portraiture leads to Families and Women.
- Landscape and Macro remain direct galleries.

This produces six image galleries: Kalk Bay, Beauty Queen of Leenane, Landscape, Macro, Families and Women.

## Confirmed Visual Direction

- Warm white background rather than soft grey.
- Restrained, image-first presentation.
- Generous whitespace.
- Minimal interface that does not compete with the photographs.
- Preserve the natural aspect ratios of photographs rather than forcing uniform crops in enlarged views.
- Avoid a long, scrolling project-index experience like Pieter Hugo's website.
- Do not use the visual or structural direction of Rhiannon Adam's or Daniel Meadows' websites.
- Do not use decorative animation, parallax, scroll reveals, autoplay carousels or other unnecessary movement.
- The only desired animation is the horizontal transition from one enlarged photograph to the previous or next photograph.

The exact typefaces, text colour, spacing scale and any accent colour remain to be selected after reviewing Inga's photographs and any existing identity material.

## Reference Sites

### Nadav Kander

Reference: [nadavkander.com](https://www.nadavkander.com/)

Use as the primary interaction reference for enlarged photographs:

- The pointer indicates the available previous or next action with a directional arrow.
- The user can click a large left or right navigation region instead of locating a small button.
- The enlarged photograph remains the focus of the screen.

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

- The main Photography page should provide a clean overview of Documentary, Landscape, Macro and Portraiture.
- The Documentary landing page should introduce and link to Kalk Bay and Beauty Queen of Leenane using a selected cover image for each project.
- The Portraiture landing page should introduce and link to Families and Women using a selected cover image for each gallery.
- Each of the six image galleries should have a clean overview of its photographs.
- The overview should make it easy to scan the collection without becoming visually busy.
- Selecting a photograph should open a spacious, near-full-screen enlargement experience.
- Thumbnail treatment, column count and spacing should respond to the supplied image orientations and the eventual art direction.
- An enlarged photograph should return the visitor to the same gallery and, where practical, the same scroll position when closed.

## Source Image Inventory

The private high-resolution source images are held outside this development project at `C:\GitHub\freelance-assistant\clients\inga-forde\images\hi-res`. That directory is ignored by Git in the `freelance-assistant` repository.

The 102 JPEGs have been flattened into one directory and renamed according to the six confirmed image galleries:

- Beauty Queen of Leenane: `documentary-beauty-queen-of-leenane-01.jpg` to `documentary-beauty-queen-of-leenane-07.jpg` (7 images)
- Kalk Bay: `documentary-kalk-bay-01.jpg` to `documentary-kalk-bay-18.jpg` (18 images)
- Landscape: `landscape-01.jpg` to `landscape-14.jpg` (14 images)
- Macro: `macro-01.jpg` to `macro-45.jpg` (45 images)
- Families: `portraiture-families-01.jpg` to `portraiture-families-07.jpg` (7 images)
- Women: `portraiture-women-01.jpg` to `portraiture-women-11.jpg` (11 images)

The `documentary-` and `portraiture-` prefixes express the site hierarchy; they do not identify separate general image groups. Do not create standalone parent-page image groups unless new assets are supplied specifically for them. Documentary and Portraiture cards and hero areas should use explicitly selected images from the relevant child galleries without duplicating the source files.

## Enlarged Photograph Viewer

### Desktop and Pointer Devices

- Divide the main viewer interaction area into large previous and next regions.
- Show an appropriate left- or right-pointing cursor according to the available action.
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
- Make the Photography landing page directly accessible; do not make it available only through a hover-dependent dropdown.
- Ensure all navigation works with keyboard and touch input.
- Provide a clear current-page state.
- Keep gallery navigation separate from the site's primary navigation.

## Content Management

- No CMS is required.
- Prefer a simple, documented source structure for gallery metadata and image ordering.
- Keep adding, removing, reordering and captioning photographs straightforward for a developer.
- Do not add CMS dependencies, accounts, editor interfaces or third-party content services without a later confirmed requirement.

## Accessibility and Usability

- Use semantic navigation, links and buttons.
- Provide visible keyboard focus states.
- Give viewer controls meaningful accessible names.
- Trap and restore focus appropriately if the enlargement is implemented as a modal dialog.
- Support keyboard, pointer and touch navigation.
- Provide useful alternative text for meaningful photographs, with the wording agreed as part of content preparation.
- Maintain sufficient text and focus-indicator contrast against the warm white background.
- Do not disable browser zoom.

## Image Performance

- Generate appropriately sized responsive image variants.
- Use modern image formats where they preserve the intended photographic quality.
- Avoid downloading full-resolution gallery images before they are needed.
- Preload only the most important opening image and, where useful, the adjacent viewer images.
- Prevent layout movement by reserving each image's dimensions or aspect ratio.
- Retain suitable source files outside the public build if public originals would be unnecessarily large or expose unwanted metadata.

Exact image-processing and colour-management requirements must be confirmed using the supplied master files.

## Search and Sharing Basics

- Give each main page and photography section a descriptive URL, page title and meta description.
- Provide suitable social-sharing metadata and a selected preview image.
- Use a logical heading structure.
- Include an XML sitemap and appropriate robots configuration when the production URL is known.
- Do not promise search rankings.

## Content and Assets Required

- Inga's preferred public name or wordmark.
- Opening/homepage photograph.
- Cover images for Photography, Documentary and Portraiture, plus the six image galleries.
- Final photograph selection for each of the six image galleries.
- Required gallery order and image order.
- Image titles, captions, dates, locations and credits where applicable.
- Introductory text for the Documentary and Portraiture landing pages.
- Project text for Kalk Bay and Beauty Queen of Leenane.
- Biography copy and portrait, if one is to be shown.
- Contact details and preferred enquiry route.
- Social profile links, if required.
- Copyright wording and the desired policy on image downloads.
- Favicon and social-sharing image.
- Domain and hosting details.

## Decisions Still Required

- Technical stack and hosting target.
- Exact typography and warm-white colour value.
- Whether any galleries loop from the final image back to the first.
- Whether enlargement views need unique URLs that can be bookmarked or shared.
- Whether captions are always visible, optionally revealed or used only where supplied.
- Whether the Contact page uses a form, an email link or both.
- Whether image protection measures such as disabled context menus or watermarks are wanted; these have usability costs and cannot prevent determined copying.
- Analytics and cookie requirements.
- Privacy, copyright and any other required policy content.
- Browser and device support expectations.

## Preliminary Acceptance Criteria

- All confirmed pages and photography sections are present and reachable.
- Photography is both a landing page and a navigable parent section.
- Documentary is a landing page that leads to Kalk Bay and Beauty Queen of Leenane.
- Portraiture is a landing page that leads to Families and Women.
- Landscape and Macro are available as direct galleries.
- The interface uses a warm white background and restrained visual styling.
- Gallery overview pages remain clear across mobile and desktop layouts.
- Selecting a photograph opens an uncluttered enlarged view.
- Pointer users can navigate using large cursor-arrow regions without finding small previous or next buttons.
- Keyboard users can navigate and close the viewer.
- Touch users can swipe or use large tap regions.
- No thumbnail carousel appears below enlarged photographs.
- No animation is used apart from the restrained previous/next slide transition.
- The site does not depend on a CMS.
- Responsive images and gallery loading avoid unnecessarily downloading all full-size assets at once.

These criteria are provisional until the content, stack and final visual design have been approved.
