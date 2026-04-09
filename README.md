# ryanjussel.com

Personal vanity site and CV for Ryan Jussel — built with [Astro](https://astro.build) and Tailwind CSS. Deployed on Netlify.

## Stack

- **Framework**: Astro (static output)
- **Styling**: Tailwind CSS v4
- **Hosting**: Netlify
- **Fonts**: Inter (Google Fonts)

## Project Structure

```
src/
├── components/
│   ├── Hero.astro          # Name, bio, CTA
│   ├── WorkHistory.astro   # Career timeline
│   ├── Skills.astro        # Core + technical skills
│   ├── Hobbies.astro       # Outside of work
│   └── Nav.astro           # Fixed top nav
├── layouts/
│   └── Layout.astro        # HTML shell, meta tags
├── pages/
│   ├── index.astro         # Main single-page site
│   └── cv.astro            # Print-friendly CV (/cv)
└── styles/
    └── global.css          # Tailwind import + theme
cv.md                       # Source of truth for CV content
netlify.toml                # Build + deploy config
```

## Pages

| Route | Description |
|-------|-------------|
| `/` | Main site — hero, work history, skills, hobbies |
| `/cv` | Print-friendly CV with "Save as PDF" button |
| `/resume` | Redirects to `/cv` |

## Local Development

```sh
npm install
npm run dev        # http://localhost:4321
```

## Build & Deploy

```sh
npm run build      # Outputs to ./dist
npm run preview    # Preview production build locally
```

Netlify deploys automatically on push to `main`. Build settings are defined in `netlify.toml`.

## Updating Content

All CV content originates from `cv.md`. Component files pull content directly — update the data arrays in each component to reflect changes:

- **Bio / headline** → `src/components/Hero.astro`
- **Work history** → `src/components/WorkHistory.astro`
- **Skills** → `src/components/Skills.astro`
- **Hobbies** → `src/components/Hobbies.astro`
- **CV print page** → `src/pages/cv.astro`

## Adding a Headshot

A placeholder circle is in `Hero.astro` (line 9). Replace the `<div>` with an `<img>` tag:

```astro
<img
  src="/headshot.jpg"
  alt="Ryan Jussel"
  class="flex-shrink-0 w-20 h-20 rounded-full object-cover border border-[#333]"
/>
```

Drop the image file in `public/headshot.jpg`.
