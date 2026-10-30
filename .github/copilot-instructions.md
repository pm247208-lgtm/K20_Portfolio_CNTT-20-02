# Copilot Instructions

## Project
- This is a Vietnamese student portfolio built with static HTML and CSS. The main pages are `index.html` and `ket-qua.html`; shared styles are in `css/style.css`, and local images are in `assets/`.
- There is no package manager, framework, JavaScript application, or build/test pipeline. Keep changes in the existing HTML/CSS unless the task specifically calls for additional technology.
- The contact form is a browser-validation and GET-navigation exercise only. It does not send email or persist submissions; do not imply otherwise.

## Editing
- Preserve the existing semantic HTML, Vietnamese content, accessible labels and descriptions, and visual conventions unless the request calls for a redesign.
- Use relative, repository-local paths for stylesheets and assets so the pages work after checkout or deployment. Avoid machine-specific absolute paths.
- Keep shared presentation in `css/style.css`; retain responsive behavior at the existing mobile breakpoints and check that content remains usable at narrow widths.
- Do not invent personal details, repository URLs, deployment status, test results, or other evidence. `AI_log.md` is a student worksheet: only fill it from facts the user provides or verifiable project evidence, and leave unknowns explicitly unverified.

## Verification
- For HTML/CSS changes, inspect both pages in a browser at desktop and mobile widths when browser tooling is available. Check local asset and stylesheet loading, navigation/form behavior affected by the change, and the browser console.
- There are no automated project tests or build commands. Do not claim a build or test passed when it was not run; state any verification limitation clearly.
