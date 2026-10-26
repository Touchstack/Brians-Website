# Brian Adjei-Otchwemah — Portfolio

Personal site for Brian Adjei-Otchwemah: founder and CEO of [Touch Stack Technologies](https://www.touchstacktechnologies.com/) and founder of [MediaForUs](https://www.mediaforus.live/), based in Accra, Ghana.

The site is styled like a roll of film. 12,000 WebGL particles draw a portrait of Brian, then change shape as you scroll through the chapters: Build, Lead, Story, Work, About, Skills, Play and Contact.

**Live site:** https://touchstack.github.io/Brians-Website/

## Features

- **Film-leader intro.** A 3-2-1 countdown, then the page lists what the visitor's browser told it (browser, screen, local time). Nothing is sent anywhere. Click or press any key to skip.
- **Particle portrait.** The hero particles are sampled from `brian-2.jpg`. As you scroll they become a DNA helix, a globe, a film reel, a galaxy, a voxel cube and finally the word BRIAN. They move away from the mouse.
- **Work strip.** Project cards on a film strip that slides sideways as you scroll down. On phones you swipe it.
- **About and contact sheet.** A taped print, a list of awards, and 7 photos as a film contact sheet. Click a frame to open it full size; use the arrow keys to browse.
- **Skills physics box.** Skills you can grab, throw, shake or flip upside down (Matter.js).
- **Terminal.** Press `` ` `` to open it. Try `help`, `about`, `awards`, `links`, `whoami` and `sudo hire brian`.
- **Kente loom.** A generated kente cloth that weaves itself. Click to weave a new one.
- **Frame hunt.** 5 film frames are hidden around the page. Find all of them, or type `directors-cut` in the terminal, to unlock director's cut mode.
- **Sound.** Optional synth sounds, off by default.

## Files

```
index.html     the whole site: HTML, CSS and JavaScript in one file
brian-*.jpg    the photos, resized to 1100px for the web
README.md      this file
```

The page looks for each photo in a `photos/` folder first and then next to `index.html`, so either layout works.

There is no build step and nothing to install. Three.js and Matter.js load from the cdnjs CDN, and fonts load from Google Fonts.

## Run it locally

The particle portrait reads pixels from a photo. Browsers block that when you open the file directly from disk, so serve the folder instead:

```bash
python3 -m http.server 4173
```

Then open http://localhost:4173.

## Edit the content

Most of the content is in the `EDIT ME` block near the top of the `<script>` in `index.html`:

| Setting | What it controls |
| --- | --- |
| `EMAIL` | The address in the contact section and the terminal |
| `PORTRAIT` | The photo the hero particles draw |
| `PHOTOS` | The frames on the contact sheet |
| `SOCIALS` | Contact links (LinkedIn, Instagram, Touch Stack, MediaForUs) |
| `WORK` | Project cards on the film strip |
| `SKILL_GROUPS` | Skills and colours in the physics box |

Headlines, chapter text and awards are in the HTML sections lower in the file. Search for the section name, for example `id="build"` or `id="about"`.

To use a different photo in the hero, add it next to `index.html` and change `PORTRAIT`. Head-and-shoulders shots against a plain background work best.

## Deploy to GitHub Pages

1. Push this folder to a public repository, with `index.html` at the top level.
2. In the repository, go to **Settings → Pages**.
3. Under "Build and deployment", choose **Deploy from a branch**, then select `main` and `/ (root)`, and click **Save**.
4. After a minute or two the site is live at `https://<owner>.github.io/<repo-name>/`. This repo publishes to https://touchstack.github.io/Brians-Website/.

## Browser support

Works in current versions of Chrome, Edge, Firefox and Safari, on desktop and mobile. It needs WebGL for the particles; without it the rest of the page still works. If the visitor has turned on "reduce motion" in their system settings, the intro is skipped and the animation calms down.

## Credits

Built with [Three.js](https://threejs.org/) and [Matter.js](https://brm.io/matter-js/). Fonts: Bricolage Grotesque, Instrument Serif and JetBrains Mono. Kente-inspired palette.

© 2026 Brian Adjei-Otchwemah
