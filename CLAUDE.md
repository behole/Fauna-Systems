# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for Fauna Systems, exported from Webflow. It's an artistic/scientific presentation about biobot research and technology, featuring video backgrounds and interactive slider navigation.

## Project Structure

- `index.html` - Main website file with embedded HTML, CSS, and JavaScript
- `css/` - Stylesheets
  - `fauna-systems-v0-3.webflow.css` - Primary Webflow-generated styles
  - `webflow.css` - Webflow framework styles  
  - `normalize.css` - CSS reset/normalize
- `js/webflow.js` - Webflow framework JavaScript (large minified file)
- `images/` - Static images including favicon and logos
- `videos/` - Video assets in multiple formats (mp4, webm with poster frames)

## Architecture

This is a single-page application with:
- **Video slider**: Full-screen background videos that rotate
- **Custom cursor**: Interactive cursor that changes based on mouse position over slider
- **Anchor-based navigation**: Internal page sections (#001, #002, etc.) with smooth scrolling
- **Responsive design**: Mobile-first approach with breakpoints at 479px, 767px, 991px
- **Sticky navigation**: Top navigation that becomes visible on scroll

The main interaction is a custom slider system built on top of Webflow's slider component, with custom JavaScript for click-based navigation and cursor effects.

## Development Commands

Since this is a static Webflow export, there are no build tools or package managers. To work with this project:

- **Local development**: Use any static file server (e.g., `python -m http.server` or `live-server`)
- **Testing**: Open `index.html` directly in browser or serve via HTTP server
- **Deployment**: Upload all files to web server maintaining directory structure

## Key Implementation Details

- Videos are provided in multiple formats (mp4/webm) with poster images for performance
- Custom JavaScript handles slider navigation via click detection on left/right halves
- CSS custom properties and transforms used for animations
- Font loading via Adobe Typekit (ibm-plex-mono family)
- All content is embedded in single HTML file with inline styles and scripts

## Content Management

Video assets follow naming convention: `{name}-poster-00001.jpg` for thumbnails and `{name}-transcode.{ext}` for video files. When adding new videos, maintain this pattern and update both the slider markup and video element sources.