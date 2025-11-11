# Immanuel Satya - Academic Blog

A professional academic blog built with Jekyll and the Minima theme, featuring research updates, publications, and insights on spatial methods and regional economics.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [How to Operate the Website](#how-to-operate-the-website)
  - [Adding a New Blog Post](#adding-a-new-blog-post)
  - [Editing Existing Posts](#editing-existing-posts)
  - [Updating Site Configuration](#updating-site-configuration)
  - [Modifying Pages](#modifying-pages)
  - [Customizing Styles](#customizing-styles)
- [Building and Deploying](#building-and-deploying)
- [Project Structure](#project-structure)
- [Troubleshooting](#troubleshooting)

## Overview

This blog serves as a platform to share academic activities, research publications, personal reflections, and academic-related content. It's built on Jekyll, a static site generator that transforms Markdown content into a beautiful, fast website.

## Features

- **Clean Academic Design**: Professional, minimalist theme optimized for readability
- **Responsive Layout**: Mobile-friendly design that works on all devices
- **SEO Optimized**: Built-in SEO tags and metadata for better search visibility
- **RSS Feed**: Automatic RSS feed generation for subscribers
- **Social Media Integration**: Links to Twitter, GitHub, and LinkedIn
- **Easy Content Management**: Write posts in Markdown
- **Custom Styling**: Enhanced typography and visual improvements

## Prerequisites

Before you begin, ensure you have the following installed:

- **Ruby** (version 2.7 or higher)
- **RubyGems** (comes with Ruby)
- **Bundler** gem: Install with `gem install bundler`
- **Jekyll** (will be installed via Bundler)

## Installation

1. **Clone the repository** (if not already done):
   ```bash
   git clone <your-repo-url>
   cd academicblog
   ```

2. **Install dependencies**:
   ```bash
   bundle install
   ```
   Or use the bootstrap script:
   ```bash
   script/bootstrap
   ```

3. **Run the local development server**:
   ```bash
   bundle exec jekyll serve
   ```
   Or use the server script:
   ```bash
   script/server
   ```

4. **View your site**: Open your browser and navigate to `http://localhost:4000`

## How to Operate the Website

### Adding a New Blog Post

Blog posts are stored in the `_posts/` directory and written in Markdown format.

1. **Create a new file** in the `_posts/` directory with the naming convention:
   ```
   YYYY-MM-DD-title-of-post.md
   ```
   Example: `2024-12-15-my-new-research.md`

2. **Add front matter** at the top of the file:
   ```yaml
   ---
   layout: post
   title: "Your Post Title Here"
   categories: general
   author: Immanuel Satya Pekerti
   ---
   ```

3. **Write your content** in Markdown below the front matter:
   ```markdown
   ## Introduction

   Your post content goes here. You can use **bold**, *italic*, and all standard Markdown formatting.

   ### Subheading

   More content with [links](https://example.com), lists, and code blocks:

   ```python
   def hello_world():
       print("Hello, World!")
   ```
   ```

4. **Save the file** and Jekyll will automatically regenerate the site (if the server is running)

5. **Preview your post** at `http://localhost:4000`

#### Blog Post Front Matter Options

```yaml
---
layout: post                           # Always use 'post' for blog posts
title: "Your Awesome Post Title"       # Required: Post title
categories: general                     # Optional: Categories (space-separated)
author: Immanuel Satya Pekerti         # Optional: Author name
date: 2024-12-15 14:30:00 +0000       # Optional: Override date/time
---
```

### Editing Existing Posts

1. Navigate to the `_posts/` directory
2. Open the post file you want to edit (e.g., `2024-08-10-idbt.md`)
3. Make your changes
4. Save the file
5. The site will automatically rebuild (if the dev server is running)

### Updating Site Configuration

The main configuration file is `_config.yml` at the root of the project.

**Common settings you might want to change:**

```yaml
title: Immanuel Satya - Academic Blog        # Site title
description: >                                 # Site description
  Your site description here

author:
  name: Your Name                              # Your name
  email: your.email@example.com               # Your email

# Social media links
minima:
  social_links:
    twitter: your_twitter_handle
    github: your_github_username
    linkedin: your_linkedin_username

# Navigation menu
header_pages:
  - about.md
  - cv.md
  - research.md
  - projects.md
```

**Important**: After editing `_config.yml`, you must **restart the Jekyll server** for changes to take effect:
```bash
# Stop the server (Ctrl+C) and restart:
bundle exec jekyll serve
```

### Modifying Pages

Static pages (About, CV, Research, Projects) are Markdown files in the root directory.

**To edit a page:**

1. Open the desired page file:
   - `about.md` - About page
   - `cv.md` - Curriculum Vitae
   - `research.md` - Research & Publications
   - `projects.md` - Projects page
   - `index.md` - Homepage content

2. Edit the content in Markdown format

3. Save the file

**Page structure:**
```yaml
---
layout: page                # Use 'page' layout for static pages
title: About                # Page title
permalink: /about/          # URL path
---

Your page content in Markdown goes here.
```

### Customizing Styles

The site uses SCSS for styling. Custom styles can be added to:

**`_sass/minima/custom-styles.scss`** - For CSS overrides and additions

Example of adding custom styles:
```scss
// Add your custom styles here
.my-custom-class {
  color: #2c5282;
  font-weight: bold;
}

// Override existing styles
.post-title {
  color: #1a365d;
}
```

**`_sass/minima/custom-variables.scss`** - For variable overrides

Example of changing variables:
```scss
// Override theme variables
$base-font-size: 18px !default;
$content-width: 900px !default;
```

**Color scheme**: Change the theme skin in `assets/css/style.scss`:
```scss
---
---

@import "minima/skins/classic";  // Options: classic, dark, solarized, solarized-dark
@import "minima/initialize";
```

## Building and Deploying

### Local Development

```bash
# Start development server with auto-rebuild
bundle exec jekyll serve

# Or use the script
script/server

# Build without serving
bundle exec jekyll build
```

### Production Build

```bash
# Build the site for production
bundle exec jekyll build

# Or use the build script
script/build

# The static site will be generated in the _site/ directory
```

### Deployment Options

1. **GitHub Pages**:
   - Push your code to a GitHub repository
   - Enable GitHub Pages in repository settings
   - Select the branch to deploy (usually `main`)

2. **Netlify/Vercel**:
   - Connect your repository
   - Build command: `jekyll build`
   - Publish directory: `_site`

3. **Manual Deployment**:
   - Build the site locally: `jekyll build`
   - Upload the contents of `_site/` to your web server

## Project Structure

```
academicblog/
├── _config.yml              # Site configuration
├── _includes/               # Reusable template components
│   ├── head.html
│   ├── header.html
│   ├── footer.html
│   └── ...
├── _layouts/                # Page templates
│   ├── default.html         # Base layout
│   ├── home.html           # Homepage layout
│   ├── post.html           # Blog post layout
│   └── page.html           # Static page layout
├── _posts/                  # Blog posts (Markdown files)
│   ├── 2024-08-10-idbt.md
│   └── ...
├── _sass/                   # Stylesheets (SCSS)
│   └── minima/
│       ├── custom-styles.scss    # Your custom CSS
│       └── custom-variables.scss # Variable overrides
├── assets/                  # Static assets
│   └── css/
│       └── style.scss      # Main stylesheet
├── script/                  # Utility scripts
│   ├── bootstrap           # Install dependencies
│   ├── build              # Build the site
│   └── server             # Run dev server
├── about.md                # About page
├── cv.md                   # CV page
├── research.md             # Research page
├── projects.md             # Projects page
├── index.md                # Homepage content
└── README.md               # This file
```

## Troubleshooting

### Jekyll Server Won't Start

**Problem**: Error when running `jekyll serve`

**Solution**:
```bash
# Reinstall dependencies
bundle install

# If that doesn't work, update bundler
gem install bundler
bundle update
```

### Changes Not Appearing

**Problem**: Made changes but they don't show up on the site

**Solutions**:
1. If you edited `_config.yml`, restart the server (Ctrl+C, then `jekyll serve` again)
2. Hard refresh your browser (Ctrl+Shift+R or Cmd+Shift+R)
3. Clear Jekyll cache: `bundle exec jekyll clean` then rebuild

### Posts Not Showing Up

**Problem**: Created a new post but it doesn't appear

**Checklist**:
1. File is in `_posts/` directory
2. Filename follows format: `YYYY-MM-DD-title.md`
3. Front matter is properly formatted (check for YAML errors)
4. Date is not in the future (Jekyll won't show future-dated posts by default)

### Ruby Version Issues

**Problem**: Jekyll requires a different Ruby version

**Solution**:
```bash
# Install rbenv or rvm to manage Ruby versions
# Example with rbenv:
rbenv install 3.1.0
rbenv local 3.1.0
bundle install
```

### Permission Errors

**Problem**: Permission denied when installing gems

**Solution**:
```bash
# Don't use sudo with gem/bundle
# Instead, configure gem installation path:
bundle install --path vendor/bundle
```

## Additional Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Minima Theme Documentation](https://github.com/jekyll/minima)
- [Markdown Guide](https://www.markdownguide.org/)
- [Liquid Template Language](https://shopify.github.io/liquid/)
- [Jekyll Cheat Sheet](https://devhints.io/jekyll)

## Support

For questions or issues, contact:
- **Email**: satya.immanuel@gmail.com
- **GitHub**: [@soegampars](https://github.com/soegampars)

---

**Last Updated**: November 2025
