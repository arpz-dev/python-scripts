# 💐 ASCII Flower Bouquet

A spinning 3D flower bouquet that runs right in your terminal. Daisies, tulips, a paper wrap with a ribbon, baby's breath, sparkles and floating hearts, all drawn with text characters.

## ▶️ Run it

You only need Python 3.7+. No packages to install.

```bash
python3 ascii-flower-bouquet.py
```

Press `Ctrl + C` to stop it.

> [!TIP]
> On Windows, use `python ascii-flower-bouquet.py` instead.

## 💡 Tips

- Make your terminal window big, or zoom out a bit (`Cmd -` on macOS, `Ctrl -` on Windows/Linux). More space means a smoother-looking bouquet.
- Use a terminal with 256-color support. Most have it: macOS Terminal, iTerm2, Windows Terminal, VS Code and pretty much anything on Linux.
- If the hearts show up as boxes, switch your terminal font to one with good Unicode support (for example Menlo or SF Mono on macOS).

## 🎨 Make it yours

Open `ascii-flower-bouquet.py` and change the values at the top of the file:

| Setting      | What it does                                   |
| ------------ | ---------------------------------------------- |
| `MESSAGE`    | The text shown under the bouquet               |
| `SPIN_SPEED` | How fast the bouquet spins                     |
| `TILT`       | How much you look down at it                   |
| `CAM_DIST`   | Lower number = more dramatic perspective       |
| `NUM_HEARTS` | How many hearts float in the background        |
| `FPS`        | Frame rate                                     |

You can also swap the color lists (`PINK`, `RED`, `PURPLE`, etc.) to change the flowers. They use 256-color terminal codes.

## ⚙️ How it works

Every part of the bouquet is a set of 3D points. On each frame the points are rotated, projected onto the screen with perspective, and shaded according to a light direction. A depth buffer makes sure the closest point wins each character cell. The flower heads are drawn as flat shapes that always face the camera, so the petals stay readable while the bouquet spins.
