# Chris Kelly Portfolio (Codecademy Unit 2)

A one-page developer portfolio built for Unit 2 of the Codecademy Full-Stack Developer bootcamp. Plain HTML and CSS with a Flexbox layout, no JavaScript, no build step. This is the coursework version of my portfolio; the production one is at kellybuilt.dev.

Live: [https://ctk1215.github.io/codecademy-portfolio/](https://ctk1215.github.io/codecademy-portfolio/)

## What's on the page

Everything lives on one page, and the sticky nav links to each section by anchor.

| Section | Content |
|---|---|
| Hero | Name, typed-out tagline, short intro, "View My Work" button |
| About | Headshot and three paragraphs on how I got into software |
| Skills | Three cards: Frontend, Backend, Tools |
| Projects | Three cards styled as terminal windows (NurseTrack, Wendell Turner Real Estate, Unshackled Truth Media), each with a tech list, a GitHub button, and a live-site button |
| Contact | Email, LinkedIn, and GitHub as icon links |

## Stack

- HTML5 and CSS3. No frameworks, no preprocessors, no scripts.
- Flexbox for layout; one `@keyframes` animation for the tagline.
- Inline SVG icons.

## Project structure

```
index.html        the whole page
css/styles.css    theme variables, base styles, one block per section, media queries at the end
images/
  chris-headshot.jpg
  favicon.svg
```

## Running locally

Nothing to install. Clone the repo and open `index.html` in a browser, or serve the folder with any static server:

```
npx serve .
```

No environment variables.

## Deployment

GitHub Pages, from the `main` branch, root folder. Pushing to `main` publishes the site. There is no workflow file; this is the standard branch-based Pages build.

## Notes on the implementation

- **Responsive with Flexbox.** The skills and project grids are `display: flex` with `flex-wrap: wrap`, and the cards use `flex: 1 1 250px` and `flex: 1 1 300px`, so they reflow from one column to three without layout media queries. The two media queries that do exist widen the nav spacing at 768px and reformat the last skill card as an inline list between 579px and 852px.
- **Terminal theme in CSS.** The `$ whoami` prompt above the name and the `> ` before each heading are `::before` pseudo-elements. The project cards' window chrome (three dots and a path) is plain markup marked `aria-hidden`.
- **Reduced motion.** The typing animation on the tagline is disabled under `prefers-reduced-motion: reduce`.
- **Aligned card buttons.** The project links row uses `margin-top: auto` so the buttons sit at the bottom of every card regardless of description length.
