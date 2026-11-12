# Glass Sketchbook

A 3D sketchbook for planning furnace-blown glass. Shape a piece the way you would at the bench: draw one side of the bubble's silhouette and it spins into the full form, then paddle it flat, square it up, add bits (spikes, pulled horns, spouts), cut an opening (straight or tilted) with a fire-polished or ground-flat lip, and pick colors and wraps. You can upload a photo of a pencil sketch to trace over.

## Run it

It's a single file with no build step. Open `index.html` in a browser.

## Put it online with GitHub Pages

1. Push this folder to a GitHub repo.
2. In the repo, go to Settings, then Pages.
3. Under "Build and deployment", choose "Deploy from a branch", pick `main` and `/ (root)`, and save.
4. The site appears at `https://<your-username>.github.io/<repo-name>/` after a minute or two.

## How it's built

- Plain HTML, CSS and JavaScript in `index.html`
- [three.js r128](https://threejs.org/) loaded from cdnjs for the 3D view
- Bubble forms are a lathe (spun profile); "square up" uses a superellipse, "paddle flat" scales depth
- The lathe is built one meridian at a time so each can end exactly on the cut plane; any fully open mouth gets a lip (a round bead for fire-polished, a frosted flat band for ground)
- The donut body is a torus with a neck cylinder
- Bits are tapered tubes swept along a curve
- Your last design is saved in the browser's localStorage; sketch photos are not saved

## Ideas for later

- Type a description or upload a sketch and have the shape update from it
- Jaw or foot kickstand
- Cane and murrini surface patterns
- Export to STL for 3D printing
