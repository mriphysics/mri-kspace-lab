# MRI K-space Lab

A dependency-free static teaching app derived from `MRI_kspace_encoding.mlx`.

The app now generates a rotated modified Shepp–Logan phantom on a 512 × 512 grid spanning 400 mm. It includes 2, 3, 4, 6 and 8 mm disc targets, continuous 50–400 mm FOV controls, 0.8–8 mm image-resolution prescriptions and a fixed-TR scan-time estimate. Full extent in k-space mode corresponds to 1 mm resolution. Resolution is controlled by k-space extent; FOV is controlled independently by Δk, so enlarging phase FOV increases the number of phase lines without implying better resolution.

The interface supports two linked workflows:

- **K-space driven:** change sampling extent, line spacing and asymmetry, then observe the image-domain result.
- **Image prescribed:** choose readout/phase FOV and resolution, then inspect the required Cartesian matrix, Δk, kmax and a scan-time estimate.

The sequence-time estimate assumes 2D Cartesian imaging, one phase-encoding line per TR, NEX = 1 and a fixed TR of 10 ms.

## Run locally

Serve the `dist` folder with any static web server, for example:

```bash
python3 -m http.server 8000 --directory dist
```

Then open `http://localhost:8000`.

## Test

```bash
npm test
```

## Host elsewhere

Upload the contents of `dist/` to GitHub Pages, Netlify, Cloudflare Pages, or any static web host. No server, MATLAB runtime, account, or build step is required.

All phantom generation, FFT and reconstruction run locally in the browser. The `dist/` folder is the complete deployable site.
