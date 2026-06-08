# Hoshizuna: Model Viewer for Dome

A lightweight, browser-based 3D model viewer designed for projecting 3D models in planetariums and dome theaters. It allows anyone to easily run 3D presentations directly in a web browser without complex configurations.

[Live Demo](https://tasukuyoshioka.github.io/hoshizuna/) | [Detailed Guide (Notion)](https://atlantic-net-15f.notion.site/How-to-Use-Hoshizuna-372ecdd4ea4c80ddb18df8ad78f62e18)

---

## Features

- **Format Support:** Load 3D models in STL, OBJ (with vertex colors), or SVG (limited support) formats directly from your local drive.
- **Dome View (Dome Master):** Opens a separate child window in dome master format. Displaying this window in full screen allows projection across the entire dome screen.
- **Control Modes:**
  - **Orbit Mode:** Rotate and pan the camera angle around the model using the mouse.
  - **Fly Mode:** Freely move through the 3D space using keyboard shortcuts (`W`, `A`, `S`, `D`, `Q`, `E`, `R`, `F`, and arrow keys).
- **Environment Editing:** Customize background colors, equirectangular background images, ambient/directional/hemisphere lights, and output resolution.
- **Terminal:** Automated animation playback based on sequential or parallel command queues (camera coordinates, rotation, easing, pause, and object transformations).
- **Video Recording:** Record and export your automated command sequences as `.webm` videos directly from the browser.

## How to Use

1. **Open the App:** Access the live link in a WebGL-compatible browser (Hardware/GPU acceleration is highly recommended).
2. **Add a Model:** Click the **"Add Model"**  button and select your 3D file.
3. **Adjust Environment:** Click **"Env Edit"** to set up background stars (equirectangular images) or lighting conditions.
4. **Open Dome View:** Click **"Dome View"** to open the dome master window. Move this window to your planetarium's external video input and make it full screen.
5. **Animate:** Open the **"Terminal"**, paste your script queues, and hit the play button to start the presentation.

## Command Scripting (Terminal)

The built-in Terminal interprets instructions line by line. Blank lines and lines starting with `//` or `#` are ignored.

### Example Script:
```
// Move camera and adjust tilt instantly
pos: 0.00, 0.00, 50.00; rot: 0.0, 0.0, 0.0; tilt: 0.0, 0.0;

// Smooth camera transition over 5 seconds with ease-in-out curve
pos: 10.00, 20.00, 30.00; rot: 15.0, 45.0, 0.0; dur: 5; ease-in-out;

// Pause execution for 2 seconds
pause: 2;

// Transform a specific loaded model smoothly
obj(MyFossilModel) {pos: 0.0, 10.0, 0.0; rot: 0, 90, 0; size: 2.0; dur: 3; ease-out;}
```

## Update History / Changelog

- **v1.69 (June 2026)**: Fixed control issues when multiple gamepads are connected.
- **v1.68 (June 2026)**: Added background animations, color and opacity settings in the terminal, and gamepad support.
- **v1.67 (June 2026)**: Added the ability to save and load command scripts (`.txt`) locally, and English language supported. Hosted on GitHub.
- **v1.00 (May 2025)**: Initial release (hosted on [tsm.toyama.toyama.jp](https://www.tsm.toyama.toyama.jp/_ex/curators/yoshioka/ModelViewer4Dome/))


## Related Presentations & Publications

- Yoshioka et al. (2025) *Proc. Symp. Soc. Sci. Form Jpn.*, 10(1).
- Yoshioka & Takahei (2025) *Annu. Conf. Soc. Jpn. Sci. Teach.*, (25).
- [Yoshioka (2026) *IPS 2026 Fukuoka*, PO2-10](https://pub.confit.atlas.jp/en/event/ips2026/presentation/PO2-10). [coming soon!!]
