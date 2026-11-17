# Image Check

Clickable prototypes for a UX research and product design challenge: **Real, AI-enhanced or AI-generated?**

Image Check helps people decide whether to trust an image. Take a screenshot (or share/drag the original file) and tap **Check for AI**. The result shows one of four states, the evidence behind it, and how sure the check is:

| Result | Meaning |
|---|---|
| **Real** | Captured, not changed |
| **AI-enhanced** | A real photo, partly changed with AI |
| **AI-generated** | Fully made by AI |
| **Can't verify** | Not enough evidence either way |

> **Detection is simulated.** The prototypes show how results, evidence and uncertainty are explained, not a working detector.

## Try it

Open `index.html` in a browser, then pick a prototype:

- **iPhone** (`phone.html`): press the side button to take a screenshot, tap the thumbnail, then **Check for AI**. Or tap the share icon next to an image and choose **Image Check** to check the original file.
- **Laptop** (`laptop.html`): click **Take screenshot** and drag a box over an image, then **Check for AI**. Or drag an image onto the **Drop to check** pop-up in the corner. Best on a laptop or desktop screen.

No build step and no dependencies: plain HTML, CSS and JavaScript.

## Two ways in

| | Screenshot | Original file |
|---|---|---|
| Phone | Side button, then the thumbnail | Share, then Image Check |
| Laptop | Take screenshot, then drag a box | Drag onto the corner pop-up |
| Checks | 3 of 4 (edit history is lost) | 4 of 4 (includes edit history) |

## Project structure

```
index.html          Landing page
phone.html          iPhone prototype
laptop.html         Laptop prototype
assets/             Test images, previews and wallpaper
slides/research/    Research deck (LaTeX Beamer source)
slides/design/      Design deck (LaTeX Beamer source)
vercel.json         Vercel settings (static site)
```

## Publish

- **GitHub Pages:** Settings → Pages → Deploy from branch → `main`, folder `/ (root)`.
- **Vercel:** run `npx vercel --prod` in this folder.

## Build the slides

The decks use Helvetica Neue and Times New Roman, so they need **XeLaTeX** (each folder has a `.latexmkrc` that selects it):

```bash
cd slides/research && latexmk presentation.tex
cd slides/design && latexmk presentation.tex
```

## Research behind it

A survey of 16 people (ages 18–35) judged five image pairs. Key findings that shaped the design:

- 58% of answers were right overall (guessing is 50%).
- Only 44% spotted the AI edit on a real photo, the hardest case.
- 1 in 4 wrong answers was rated "very sure", so feeling sure is a weak guide.
- People rely on vague cues ("light", "sharpness", "instinct") rather than evidence.

## Credits

Research, test images and design decisions by Bulluraj Mutum (M.Des UX).
AI use: Claude helped write the prototype code and the LaTeX slides.
