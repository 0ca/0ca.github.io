# 0ca's Blog

A GitHub Pages blog powered by Jekyll, focusing on AI, Security, and CTF Challenges.

## Setup Instructions

### 1. Create the GitHub Repository

1. Go to [GitHub](https://github.com/new)
2. Create a new repository named `0ca.github.io`
3. Make sure it's public
4. Initialize with a README (optional)

### 2. Push This Code to GitHub

```bash
cd 0ca.github.io
git init
git add .
git commit -m "Initial blog setup"
git branch -M main
git remote add origin git@github.com:0ca/0ca.github.io.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on "Settings"
3. Scroll down to "Pages" section
4. Under "Source", select "Deploy from a branch"
5. Choose "main" branch and "/ (root)" folder
6. Click "Save"

Your blog will be live at `https://0ca.github.io` in a few minutes!

## Local Development

### Prerequisites

- Ruby (2.5 or higher)
- Bundler gem

### Setup

```bash
# Install dependencies
bundle install

# Serve locally
bundle exec jekyll serve

# Visit http://localhost:4000
```

## Creating Blog Posts

Create new posts in the `_posts` directory with the naming format:
```
YYYY-MM-DD-title.md
```

Example: `2025-01-30-introducing-boxpwnr.md`

Each post should start with front matter:
```yaml
---
layout: post
title: "Your Post Title"
date: 2025-01-30
categories: [ai, security, ctf]
tags: [boxpwnr, llm, hackthebox]
---
```

## Theme Options

The blog currently uses `jekyll-theme-minimal`. You can change this in `_config.yml`:

### Built-in GitHub Pages Themes
- `jekyll-theme-minimal`
- `jekyll-theme-cayman`
- `jekyll-theme-hacker`
- `jekyll-theme-merlot`
- `jekyll-theme-midnight`
- `jekyll-theme-minima`
- `jekyll-theme-modernist`
- `jekyll-theme-primer`
- `jekyll-theme-slate`
- `jekyll-theme-tactile`
- `jekyll-theme-time-machine`

### Advanced Themes (using remote_theme)

Popular options:
- `mmistakes/minimal-mistakes` - Feature-rich, highly customizable
- `cotes2020/jekyll-theme-chirpy` - Modern, clean, with dark mode
- `jekyller/jekyller.github.io` - Professional and minimal

To use a remote theme, replace `theme:` with `remote_theme:` in `_config.yml`:
```yaml
remote_theme: mmistakes/minimal-mistakes
```

## Customization

- Edit `_config.yml` for site-wide settings
- Modify `index.md` for homepage content
- Update `about.md` for the about page
- Add custom CSS in `assets/css/` (if using a theme that supports it)

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/pages)
- [Jekyll Themes](https://jekyllthemes.io/)

