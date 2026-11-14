# Glass Sketchbook

A 3D sketchbook for planning furnace-blown glass. Shape a piece the way you would at the bench: draw one side of the bubble's silhouette and it spins into the full form, then paddle it flat, square it up, add bits (spikes, pulled horns, spouts), cut an opening (across the top, tilted, or as a hole in the side) with a fire-polished or ground-flat lip, add a jaw kickstand the piece leans on, and pick colors and wraps. When it's ready, save an orthographic drawing sheet (front, side and top at one true scale, shaded, outlined or both, with real dimensions) as a PNG. You can upload a photo of a pencil sketch to trace over.

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
- Openings clip the body mesh against a plane that can face any direction, splitting triangles at the plane so a hole can sit anywhere; the cut edges are chained into rim loops that get a lip (a round bead for fire-polished, a frosted flat band for ground)
- The jaw is a stubby swept bit angled toward the table, round or squared (a superellipse cross-section); the piece is then tipped (found by bisection) until the jaw and the body both touch the ground
- A hollow jaw keeps its flat end on the table and gets an oval opening with a lip midway along its upper face; the body is clipped a second time by the jaw's own footprint, so the opening leads down the jaw into the inside of the piece, like an abstract nasal cavity
- The donut body is a torus with a neck cylinder
- Bits are tapered tubes swept along a curve
- Drawings use orthographic cameras sharing one scale; the outline style renders part IDs and surface normals offscreen and inks wherever the part changes or the surface folds
- Undo and redo (Ctrl/Cmd+Z, Ctrl/Cmd+Shift+Z or Ctrl+Y, or the ↶ ↷ buttons) step through up to 100 snapshots of the design; a change is recorded once things settle for 0.4 s, so one drag is one step
- Your last design is saved in the browser's localStorage; sketch photos are not saved

## Ideas for later

- Type a description or upload a sketch and have the shape update from it
- Curled or bent bodies, and donuts with a gap
- Cane and murrini surface patterns
- Export to STL for 3D printing
