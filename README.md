# My Portfolio

> A static personal portfolio built with HTML, CSS, JavaScript and Bootstrap — originally created as a simple college portfolio and later rebuilt into a more complete snapshot of the things I build, the technologies I work with, and the things I enjoy outside code.

**Live site:** [yuti2908.github.io/My-Portfolio](https://yuti2908.github.io/My-Portfolio/)

---

## What is this repo?

This repository contains the source for my personal portfolio website.

Rather than making the site a direct copy of my resume, the portfolio is meant to give a little more context around me: selected projects, technologies I work with, achievements, things I've experimented with, and a few completely non-technical interests.

The current site is intentionally still a **static frontend** — there is no backend, database, or application server required.

---

## Tech Stack

| Area | Technologies |
|---|---|
| Structure | HTML5 |
| Styling | CSS3, Bootstrap |
| Interaction | JavaScript, jQuery |
| UI / Animation | Typed-style custom hero animation, Owl Carousel, Lightbox |
| Icons | Ionicons, Font Awesome |
| Deployment | GitHub Pages |
| CI/CD | GitHub Actions |
| Assets | Local images, SVG project visuals and certificates |

The project also keeps its frontend libraries under `lib/`, so the site can be run without a frontend build system such as npm/Webpack.

---

## Site Structure

| Section | Purpose |
|---|---|
| **Home** | Short introduction with rotating one-liners |
| **About** | Current role, education, technical areas and a more personal introduction |
| **Skills** | Grouped technical skills with additional project-specific details revealed on hover |
| **Experience** | Professional engineering experience |
| **Projects** | Selected projects with visuals, descriptions and technology tags |
| **Achievements** | Certifications, awards, programs and hackathon-related milestones |
| **Beyond the Code** | Interests that have nothing to do with pretending everything is a side project |
| **Contact** | Contact form / footer information |

---

## Running Locally

Because this is a static site, there is no dependency installation or build step.

### Option 1 — Open directly

Clone the repository and open `index.html` in a browser.

```bash
git clone https://github.com/Yuti2908/My-Portfolio.git
cd My-Portfolio
```

### Option 2 — Use a local server

A local server is preferable because it behaves more like the deployed site.

For example, with Python:

```bash
python -m http.server 8000
```

Then open:

```
http://localhost:8000
```

---

## Deploying with GitHub Pages

The site can be hosted directly from this repository.

### One-time GitHub setup

1. Open **Settings → Pages** in the repository.
2. Under **Build and deployment**, select **GitHub Actions** as the source.
3. Keep the repository's default branch as `main`.

The repository includes a workflow at:

```
.github/workflows/deploy.yml
```

After that, every push to `main` triggers a deployment.

### Deployment flow

```text
git push
   │
   ▼
GitHub Actions
   │
   ├── Checkout repository
   ├── Configure GitHub Pages
   ├── Package the static files
   └── Deploy Pages artifact
   │
   ▼
GitHub Pages
   │
   ▼
Live portfolio
```

There is deliberately no build command here. The repository already contains the HTML, CSS, JavaScript, libraries and assets required by the browser, so GitHub Actions only needs to package and publish them.

### Manual deployment alternative

If you don't want Actions, GitHub Pages can also serve the repository directly from a configured branch. The Actions workflow is useful because the deployment becomes automatic: **push → deploy**.

---

## How This Version Was Built

This portfolio started as a conventional static HTML/CSS/Bootstrap project. The recent refresh was done differently: the repository itself became the working environment.

### GitHub + ChatGPT workflow

I connected the GitHub repository to ChatGPT and used the GitHub connector to work directly against the repository.

The workflow was roughly:

```text
GitHub repository
      │
      ▼
GitHub connector
      │
      ▼
ChatGPT reads source files
      │
      ├── HTML structure
      ├── CSS/layout
      ├── JavaScript behavior
      ├── project repositories
      └── existing assets
      │
      ▼
ChatGPT proposes / implements changes
      │
      ▼
GitHub connector writes files + commits
      │
      ▼
GitHub Pages
```

### What is the GitHub connector?

The GitHub connector lets ChatGPT interact with repositories that you've authorized it to access.

For this project, that meant it could:

- read files such as `index.html`, CSS and JavaScript
- inspect repository/project information
- inspect other repositories for project context
- create new text/SVG assets
- update existing files
- commit changes directly to the repository

That made the process much closer to pair-programming on the actual project than copying snippets into a chat and manually pasting everything back.

### Why use it for a portfolio?

A portfolio has a lot of small pieces that need to stay consistent:

- project names ↔ descriptions ↔ tech stacks
- skill icons ↔ actual technologies
- image paths ↔ project cards
- responsive CSS ↔ desktop/mobile layouts
- JavaScript ↔ the HTML it controls
- README ↔ what the repository actually contains

Working against the repository meant changes could be made with the surrounding code in context rather than treating each snippet independently.

---

## Updating the Portfolio

Most content changes can be made directly in `index.html`.

Common locations:

```text
index.html
├── Hero
├── About
├── Skills
├── Experience
├── Stats
├── Projects
├── Achievements
└── Beyond the Code

css/
└── style.css        → layout, responsiveness and visual styling

js/
└── main.js          → interactions and hero text rotation

img/
└── ...              → portfolio images, certificates and project visuals

.github/
└── workflows/
    └── deploy.yml   → GitHub Pages deployment
```

For a new project card, update the project section and add the required visual under `img/`. Keep the technology tags concise enough that the card remains balanced across desktop and mobile layouts.

---

## Design Notes

A few choices in the current version are intentional:

- **The portfolio is not a resume clone.** Work experience is represented, but the site also has room for projects and personality.
- **Project cards use technology tags** so the stack can be scanned without turning every description into a paragraph of keywords.
- **Skill cards use hover details** for frameworks/libraries that don't deserve an entire standalone skill tile.
- **Project visuals are flexible.** Some are screenshots; architectural or system-oriented projects can use diagrams instead.
- **Responsive grids** keep the cards aligned rather than relying on manually sized images.

---

## Credits

The original portfolio was built using the [DevFolio](https://bootstrapmade.com/devfolio-bootstrap-portfolio-html-template/) Bootstrap template and has since been substantially modified.

The current version is maintained as a personal project and deployed through GitHub Pages.
