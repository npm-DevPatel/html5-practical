# HTML5 + CSS3 + Docker Practical

This project extends the previous HTML5 Practical by adding CSS3 styling and Docker containerization.  
The theme is inspired by **Oracle Red Bull Racing / Max Verstappen**.

---

## Pages

- **index.html** — Semantic structure, navigation, skip link, headings, blockquote, time, abbr, code/kbd/samp.  
- **about.html** — Sections with short history, unordered and ordered lists, definition list.  
- **media.html** — `<picture>` responsive image, audio element, and video with WebVTT captions.  
- **extras.html** — Tables (caption/thead/tbody/tfoot), `<details>`, `<dialog open>` for microcontent.  

---

## Design Decisions

### 🎨 Palette
Based on Red Bull Racing brand identity:
- `--bg`: dark navy (`#0a0f2c`)  
- `--fg`: white (`#ffffff`)  
- `--muted`: grey (`#888888`)  
- `--brand`: Red Bull red (`#e10600`)  
- `--brand-contrast`: light grey/white for legibility  

### 🔠 Typography
- Sans-serif system font stack (`Segoe UI`, `Roboto`, `Helvetica`, `Arial`, sans-serif).  
- Modular scale: `--h1: 2rem`, `--h2: 1.5rem`, `--body: 1rem`.  
- Line height `1.6` for readability.  

### 📏 Spacing
- `--space-1: 0.5rem` up to `--space-5: 3rem`.  
- Applied consistently for rhythm (padding/margin).  

### 🧩 Components
- **Cards**: padded, rounded, shadowed sections for grouping content.  
- **Tables**: striped rows, responsive overflow.  
- **Media**: responsive images & video with subtle captions.  

---

## Accessibility Notes

- **Skip to content** link styled to appear on focus.  
- High color contrast maintained (WCAG AA).  
- Focus states visible on links, buttons, and interactive elements.  
- Reduced motion respected:  
  ```css
  @media (prefers-reduced-motion: reduce) {



  Responsive Design

Mobile-first approach.

Breakpoints:

<480px → single column.

≥768px → content + sidebar.

≥1024px → multi-column grid.

Tested at narrow (375px) and wide (1280px+) widths.

Docker

This site can run locally inside a Docker container using nginx:alpine.

Dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
HEALTHCHECK --interval=30s --timeout=3s \
 CMD wget -qO- http://localhost:80/ >/dev/null || exit 1

Build & Run

From the project root:

# Build image
docker build -t npmdevpatel/html5-practical .

# Run container locally at http://localhost:8080
docker run --rm -p 8080:80 npmdevpatel/html5-practical

Publish to Docker Hub
docker tag npmdevpatel/html5-practical npmdevpatel/html5-practical:latest
docker push npmdevpatel/html5-practical:latest

Links

Live GitHub Pages site: https://npm-devpatel.github.io/html5-practical/

GitHub Repository: https://github.com/npm-devpatel/html5-practical

Docker Hub Image: https://hub.docker.com/r/npmdevpatel/html5-practical

Screenshots

(add screenshots here of mobile + desktop views, e.g. from browser + dev tools)

Lighthouse

Accessibility: ≥90

Performance: optimized (CSS under 50KB, responsive images respected).
    * { animation: none; transition: none; }
  }
