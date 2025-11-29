# How to Switch Themes

## Current Theme: Cayman
The blog currently uses `jekyll-theme-cayman` which is clean and modern.

## Quick Theme Changes (No extra setup needed)

Edit `_config.yml` and change the `theme:` line:

### Option 1: Hacker Theme (Dark, perfect for security)
```yaml
theme: jekyll-theme-hacker
```
Also update `Gemfile`: `gem "jekyll-theme-hacker"`

### Option 2: Slate Theme (Dark with gradient)
```yaml
theme: jekyll-theme-slate
```
Also update `Gemfile`: `gem "jekyll-theme-slate"`

### Option 3: Architect Theme (Professional)
```yaml
theme: jekyll-theme-architect
```
Also update `Gemfile`: `gem "jekyll-theme-architect"`

## Advanced Theme: Chirpy (Most Professional)

For the best-looking blog with features like:
- 🌓 Dark mode toggle
- 🔍 Built-in search
- 📱 Fully responsive
- 📊 Categories & tags
- 📦 Archive view
- ⚡ Fast and modern

### Setup Chirpy:

1. **Replace _config.yml** with _config.chirpy.yml:
   ```bash
   mv _config.yml _config.backup.yml
   mv _config.chirpy.yml _config.yml
   ```

2. **Update Gemfile**:
   ```ruby
   source "https://rubygems.org"
   
   gem "jekyll", "~> 4.3"
   gem "jekyll-theme-chirpy", "~> 7.0"
   
   group :jekyll_plugins do
     gem "jekyll-feed"
     gem "jekyll-seo-tag"
     gem "jekyll-sitemap"
     gem "jekyll-paginate"
     gem "jekyll-archives"
   end
   ```

3. **Adjust post front matter** in `_posts/` files:
   ```yaml
   ---
   title: "Your Title"
   date: 2025-01-30
   categories: [AI, Security]
   tags: [boxpwnr, llm, ctf]
   ---
   ```

4. **Push and wait** - GitHub Pages will rebuild with the new theme!

## Testing Locally

After changing theme:
```bash
bundle install
bundle exec jekyll serve
```

Visit http://localhost:4000 to see the changes.

## My Recommendation

- **For quick improvement**: Stick with `jekyll-theme-cayman` or try `jekyll-theme-hacker`
- **For best appearance**: Use Chirpy (requires more setup but worth it!)
- **For security vibe**: Use `jekyll-theme-hacker` (dark theme)

