# AI for Everyone — TinkerHub_Marala

## Project overview



`AI for Everyone` is a single-page static web experience built as a statewide initiative prototype for AI literacy (an initiative enabled by **TinkerHub**). The site is an interactive, educational landing page that mixes content, visuals and mini-games (AI Arcade) to introduce AI concepts to learners across ages and backgrounds.

This README contains everything you need to add to the repository `README.md` on GitHub: description, features, tech stack, file structure, how to run / deploy, customization notes, contribution guidelines, license and next steps.

---

## Live demo

A demo link is embedded in the app UI: `https://godsonmd.github.io/ai4everyone/` (also exposed in the page links). You can open `index.html` locally for a full experience.

---

## Key features

* **Hero + content sections**: Mission, approach, target groups, partners and CTAs.
* **Interactive visual background**: Performance-tuned `neural-canvas` particle system with spatial-gridding for efficient particle connections and mouse interaction (trail + connection glow).
* **AI Arcade**: Multiple interactive mini-games to teach AI ideas through play:

  * **Neural Dash** — collect good data, avoid hallucinations; integrates with the canvas rendering.
  * **Alpha Scramble** — word-scramble educational game.
  * **Logic Grid (Tic-Tac-Toe)** — simple user vs AI logic game.
  * **Ethical Dilemma (Story)** — branching short scenarios for discussion.
  * **Cyber Cube** — interactive 3D cube with words on faces (touch/drag rotation supported).
* **AI graph UI**: `AIGraphSystem` — a dynamic node graph for categories (Text, Image, Code, Video, Audio, etc.) which opens a radial menu of AI tools (links to external tools are included).
* **Polished UI and microinteractions**: Tailwind-based design (via CDN), gradient typography, glass cards, animated buttons, cursor effects and click ripples.
* **Accessibility & mobile**: Cursor hidden on mobile; touch-drag input for games; some responsive adjustments included.

---

## Tech stack

* **Markup / UI**: Single `index.html` file; Tailwind CSS (CDN) for styling.
* **Fonts & icons**: Google Fonts (Space Grotesk, Inter) and Font Awesome.
* **Vanilla JavaScript**: self-contained scripts in `index.html` (no build step required).

---

## File structure (project root)

```
godsonmd-ai4everyone/
├── index.html       # Full single-file web app (UI, CSS, JS, games)
└── LICENSE          # Apache 2.0
```

> Note: The repository currently contains a single-page distribution-ready artifact. Consider splitting styles/scripts into separate files for maintainability.

---

## Getting started — run locally

**Requirements:** any modern web browser.

1. Clone the repo:

```bash
git clone https://github.com/godsonmd/ai4everyone.git
cd ai4everyone
```

2. Open `index.html` in your browser (double-click or `open index.html`).

Optional: run a static server for better local testing (hot reload support):

```bash
# Python (quick static server)
python3 -m http.server 8000
# then open http://localhost:8000

# or use VS Code Live Server extension
```

---

## Configuration & customization notes

Most UI and behavior is configured in `index.html` in clearly marked sections:

* **Tailwind config**: top of `<head>` sets custom colors, font families and animations.
* **Particle system tuning** (neural canvas): `PARTICLE_COUNT`, `CONNECTION_DISTANCE`, `MOUSE_DISTANCE`, `TRAIL_LENGTH`, `CELL_SIZE`. These values are responsive-aware (mobile vs desktop) and can be tuned for performance.
* **Game word pools & data**: arrays for `ScrambleGame.data`, `CubeGame.pool`, and `StoryGame.nodes` are defined in the script — edit them to add terms, scenarios or localized content.
* **Links & external resources**: tools in `AIGraphSystem.data` include `url` fields; update these to point to your preferred resources.
* **Highscore persistence**: `NeuralDash` stores `nd_highscore` in `localStorage`.

**Recommended changes for production**

* Split JS and CSS into separate files and add minification.
* Add a small build pipeline (Vite/webpack) if you plan to expand.
* Externalize strings for i18n (Malayalam translations for Kerala audience).
* Add accessibility improvements (keyboard navigation for games, ARIA attributes, focus outlines).

---

## Known issues & notes

* The custom cursor is hidden on mobile (`cursorParticle.style.display = 'none'`) — expected by design. If you want a small visible pointer for accessibility, toggle that behavior.
* `index.html` is currently a single file — moving to a modular structure will make maintenance easier.
* Performance is tuned, but very old devices may still have heavy CPU use due to canvas and particle rendering. Consider reducing `PARTICLE_COUNT` for low-end devices.

---

## How to contribute

Contributions are welcome. Suggested ways to help:

* Open issues for bugs or feature requests (UI polish, game rules, localization).
* Submit PRs that:

  * Split code into `/css/`, `/js/` directories and add a build step.
  * Add localization (e.g., Malayalam) for all public-facing text.
  * Improve accessibility (ARIA labels, keyboard controls, contrast adjustments).
  * Add automated tests for any extracted logic modules.

When opening a PR, please include:

* Short description of change
* Screenshots (if UI changes)
* Steps to test

---

## Development roadmap / TODOs

* Modularize JS into `src/` and create a simple build (ES modules).
* Add continuous deployment (GitHub Pages / Vercel) config.
* Add language selector and translated copy for Malayalam.
* Add progressive enhancement for non-JS fallback.
* Add analytics (opt-in) to measure learning engagement.

---

## Security & privacy

* The site runs fully client-side; no server-side data collection is included in the current code.
* High score and small preferences are stored locally via `localStorage`.
* If you add analytics or any networked features, disclose them in a privacy policy and follow applicable laws.

---

## Attribution & credits

* Built by **Godson M D** (GitHub: `@Godsonmd`) — see footer links in the page.
* Enabled by **TinkerHub** — initiative partner mentioned in the UI.
* Icons: Font Awesome.
* Fonts: Google Fonts (Space Grotesk, Inter).

---

## Contact

If you want help improving this repo or to collaborate on localisation / deployment, open an issue or contact the maintainer via the GitHub profile linked in the footer.

---

*Prepared automatically from repository contents — modify as needed before publishing on GitHub.*
