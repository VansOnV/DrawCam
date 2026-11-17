<div align="center">

# DrawCam

**Trace any image onto real paper using your phone's camera.**

Show a reference image on top of your live camera feed, line it up with your page, and draw while watching the screen.

[![Live demo](https://img.shields.io/badge/live%20demo-open%20DrawCam-ff7a45?style=for-the-badge)](https://vansonv.github.io/DrawCam/)

![HTML](https://img.shields.io/badge/HTML5-single%20file-e34f26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-f7df1e?logo=javascript&logoColor=black)
![Dependencies](https://img.shields.io/badge/dependencies-0-2ea44f)
![Privacy](https://img.shields.io/badge/uploads-none-2ea44f)
![PWA friendly](https://img.shields.io/badge/works%20on-iOS%20%7C%20Android%20%7C%20desktop-555)

**[Open the live site](https://vansonv.github.io/DrawCam/)** · [How to use](#how-to-use) · [Features](#features) · [Run it yourself](#run-it-yourself) · [Troubleshooting](#troubleshooting)

</div>

<!-- Add a screenshot or GIF here, for example: ![DrawCam in use](docs/demo.gif) -->

---

## What is DrawCam?

DrawCam turns your phone into a tracing aid. Point the camera at a sheet of paper, pick an image, and DrawCam floats that image over the live camera view. Match it up with your page, then draw the lines you can see. It is the same idea as a lightbox or a projector, without buying either.

Everything runs in your browser. There is nothing to install, no account, and your images never leave your device.

## Features

**Overlay**
- Drag to move, pinch to resize and rotate (mouse wheel and Shift + wheel on desktop)
- Flip horizontally or vertically, rotate in 90° steps, fit or fill the screen
- Opacity slider on the main bar so you can fade the image in and out while drawing
- **Lock** the image so it cannot shift while you draw

**Tracing helpers**
- **Outline only** mode turns any photo into clean line art, with adjustable detail and line colour
- Grayscale, invert, brightness and contrast
- Blend modes including **Multiply**, which looks like ink sitting on the paper
- Optional grid overlay for working out proportions

**Camera**
- Back or front camera, with one-tap switching
- Camera zoom (hardware zoom where the device supports it, digital zoom otherwise)
- Light toggle on devices that expose a torch
- Freeze the view to hold a frame
- Screen stays awake while the camera is running

**Quality of life**
- Drop, paste (Ctrl/Cmd + V) or choose an image
- Remembers your last image and settings on the device
- Hide all controls for a clean full-screen view
- Works offline once the page has loaded

## How to use

1. Open the [live site](https://vansonv.github.io/DrawCam/) and tap **Start camera**. Allow camera access when asked.
2. Tap the image button and choose the picture you want to trace.
3. Move and resize the image until it sits where you want it on the paper.
4. Tap the **lock** button so it stays put.
5. Draw on the paper, watching the screen to follow the lines.

**Tips for good results**
- Prop your phone above the paper (a stack of books and a phone stand both work). If the phone moves, the overlay will drift away from the page.
- Light the paper evenly and avoid casting a shadow over it.
- For photos, try **Outline only**, then raise or lower **Detail** until the lines look right.
- Use a red or blue line colour on white paper so the overlay stands out from your pencil.
- Lower the opacity once you are happy with the placement so you can see your own marks clearly.

## Controls

| Action | Touch | Desktop |
| --- | --- | --- |
| Move image | Drag | Drag |
| Resize | Pinch | Mouse wheel, or `+` / `-` |
| Rotate | Twist two fingers | Shift + wheel, or `[` / `]` |
| Nudge | n/a | Arrow keys (hold Shift for bigger steps) |
| Lock image | Lock button | `L` |
| Hide controls | Eye button | `H` |
| Freeze camera | Camera tab, Freeze view | `F` |

## Run it yourself

DrawCam is a single `index.html` file with no build step and no dependencies.

```bash
git clone https://github.com/VansOnV/DrawCam.git
cd DrawCam
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

### Host your own copy

Browsers only allow camera access on pages served over **HTTPS** (or from `localhost`), so a file opened straight from storage will not work on a phone. The easiest way to get HTTPS is GitHub Pages:

1. Go to **Settings → Pages** in your fork.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and the `/ (root)` folder, then save.
4. After a minute your site is live at `https://<your-username>.github.io/DrawCam/`.

Netlify Drop and Cloudflare Pages also work if you prefer them.

## Privacy

- Your camera feed is shown on your screen only. It is never recorded, saved or sent anywhere.
- Images you choose are processed locally. Nothing is uploaded.
- The last image and your settings are stored in your browser's own storage so they are there next time. Clear your site data to remove them.
- There are no analytics, trackers or third-party scripts.

## Browser support

| Browser | Support |
| --- | --- |
| Chrome / Edge (Android, desktop) | Full |
| Safari (iOS, macOS) | Full, except fullscreen on iPhone and camera light |
| Firefox | Works. Camera zoom and light are not available |

Camera zoom, the light toggle and fullscreen depend on what your device and browser expose. DrawCam hides any control that is not available.

## Troubleshooting

**The camera will not start.**
The page must be served over HTTPS. Use the live site, or host your own copy as described above. Then check that camera permission is allowed for the site in your browser settings and that no other app is using the camera.

**The image drifts or does not line up.**
The phone or paper moved. Keep both steady, and use the lock button once the image is placed.

**The outline looks too busy or too faint.**
Open the **Look** tab, choose **Outline only**, and adjust **Detail**. Turning on **Smooth out small details** helps with noisy photos.

**The image is mirrored.**
Use **Flip H** in the **Image** tab. The front camera is mirrored automatically, and you can change that under **View**.

## Built with

Plain HTML, CSS and JavaScript. The overlay is drawn on a `<canvas>`, the camera uses `getUserMedia`, and the line-art mode is a small Sobel edge detector written from scratch.

## Contributing

Ideas and bug reports are welcome. Open an [issue](https://github.com/VansOnV/DrawCam/issues) and include your device, browser and what you expected to happen.

## Credits

Made by **Vans**.
