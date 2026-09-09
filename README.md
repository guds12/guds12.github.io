# Srikanth's portfolio

This repository contains Srikanth's personal portfolio website. It introduces his software-engineering background, presents his experience and technical skills, lists certifications and education, provides direct contact links, and offers a downloadable PDF resume.

Live website: [srikanthguduri.blog](https://srikanthguduri.blog)

## Pages

- `/` - interactive homepage, profile photography, specialties, About section, and recruiter contact actions
- `/portfolio/` - experience, skills, certifications, education, and resume download
- `/credits/` - image sources, authors, licenses, and modifications
- `/studio/` - browser-based editor for maintaining portfolio content

## Technology and tools

- [React 19](https://react.dev/) for components and client-side interactions
- [TypeScript](https://www.typescriptlang.org/) for typed application code
- [Vinext](https://github.com/cloudflare/vinext) and [Vite](https://vite.dev/) for the application and static production build
- [Base UI](https://base-ui.com/) and local UI components for accessible tabs, accordions, and buttons
- [Lucide](https://lucide.dev/) for interface icons
- CSS media queries, responsive grids, flexible navigation, and touch-friendly controls for desktop, tablet, and mobile layouts
- Locally hosted [Manrope](https://github.com/sharanda/manrope) fonts under the SIL Open Font License
- [GitHub Pages](https://docs.github.com/pages) for static hosting
- [Porkbun](https://porkbun.com/) for the `srikanthguduri.blog` domain and DNS management

The production site is fully static. It does not use a database, analytics service, server-side contact form, or visitor-facing authentication.

## Content updates

The portfolio content is stored in `public/content.json`. Edit this file to update the profile, experience, skills, education, certifications, contact details, or resume path. The `/studio/` page can also create and export an updated `content.json` file.

Store personal photos in `public/images/`. Store the current resume in `public/` and update the `resume` value in `public/content.json`. The current downloadable file is `public/Srikanth_Resume.pdf`.

Certification buttons appear only when an HTTPS credential URL is supplied. Empty URLs do not display placeholder or pending-link text.

## Local development

Requirements: Node.js 22.13 or newer and npm.

```bash
npm ci
npm run dev
```

The development server prints the local preview address. The site supports both light and dark themes and remembers the visitor's selection on the current device.

## Build and GitHub Pages publication

Create and verify the production build:

```bash
npm run build
python3 scripts/export-pages.py
```

The exporter creates `../publish-v2`, including the static routes, JavaScript, CSS, fonts, images, resume, `CNAME`, and `.nojekyll`. The prepared release is copied into `../github-release` and published to the `main` branch of `guds12/guds12.github.io` with:

```bash
python3 "../publish-github.py"
```

The publishing script requests a fine-grained GitHub token at runtime. Restrict the token to `guds12/guds12.github.io` and grant only **Contents: Read and write**. The token is hidden while entered and is not saved.

## Responsive and accessibility behavior

The layout adapts at desktop, tablet, and phone widths. Mobile navigation uses touch-sized links, content grids collapse to one column, long experience text wraps cleanly, skill tabs scroll horizontally, and calls to action fill the available width where appropriate. Text remains readable without horizontal page scrolling.

The site includes semantic headings, alternative text, visible keyboard focus, a skip link, reduced-motion support, and keyboard-accessible interactive controls.

## Design and content references

The visual direction draws inspiration from [Sinan Tokmak's portfolio](https://sinantokmak.framer.website/) and [Bohdan Blunar's portfolio](https://www.blunar.cz/), while using original structure, content, typography, and implementation for Srikanth's site.

Professional information is based on Srikanth's supplied resume. Personal photographs were supplied by Srikanth. Openly licensed technology and software-development photographs come from Wikimedia Commons. Complete author, source, license, and modification records are maintained in `public/image-credits.json` and displayed on the website's [Image credits](https://srikanthguduri.blog/credits/) page.

## Repository structure

```text
app/                  Pages, shared site components, and styles
components/ui/        Reusable interface controls
lib/                  Content validation and shared helpers
public/content.json   Editable portfolio content
public/images/        Personal and licensed images
public/fonts/         Locally hosted Manrope font files and license
scripts/              GitHub Pages export utility
```

## License and reuse

The third-party images and font remain subject to their respective licenses. See `public/image-credits.json`, `/credits/`, and `public/fonts/OFL.txt`. Srikanth's personal photographs and resume are included for this portfolio and should not be reused without his permission.
