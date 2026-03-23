# Letterpress Digest: A Podcast About Letterpress Printing

This repository self-hosts an archived podcast (no longer producing new episodes) while maintaining the content for future listeners. Audio MP3s are hosted in an AWS S3 bucket, the RSS feed XML is maintained in this repository, and a static website is served via GitHub Pages.

## Website

**https://letterpressdigest.com** — A single-page static site with inline audio players for all 14 episodes, served via GitHub Pages from the `docs/` directory.

## Description

In the “Letterpress Digest” podcast, novice printer Jordan Berry talks about all things letterpress with some of the most influential and experienced artists, designers, and printers who are using letterpress printing today. You’ll hear guests talk about the resurgence of letterpress and their first printing press as well as numerous helpful and practical tips like how people launched their letterpress business, what type of ink they use, how they found their printing press, how to design for letterpress, and many more. There will also be some fun and entertaining stories along the way, all centered around letterpress.

## Architecture

- **`docs/index.html`** — Static website served by GitHub Pages at letterpressdigest.com
- **`docs/feed.xml`** — RSS 2.0 podcast feed with iTunes namespace extensions
- **`docs/CNAME`** — Custom domain configuration for GitHub Pages
- **`.github/workflows/uploadtoS3.yml`** — GitHub Actions workflow that syncs `docs/` to S3 on push to `main`
- **AWS S3** — Hosts the MP3 audio files, artwork image, and a copy of the feed (versioning enabled)

## Deployment

Pushing to `main` triggers two deployments automatically:
1. **GitHub Pages** serves the website from `docs/`
2. **GitHub Actions** syncs `docs/` to the S3 bucket (excluding the CNAME file)

## Podcast Reference Links

- **Website:** https://letterpressdigest.com
- **Apple Podcasts:** https://podcasts.apple.com/us/podcast/letterpress-digest-a-podcast-about-letterpress-printing/id1274859013
- **Spotify:** https://open.spotify.com/show/4wgI0vQuk3Q45lYl2Oy11J
- **iHeartRadio:** https://iheart.com/podcast/92237374/
- **RSS Feed:** https://letterpressdigest.s3.us-east-2.amazonaws.com/feed.xml
