# AoE2 Auto-Spectator

Autonomous camera control for Age of Empires II spectating. Point it at a CaptureAge replay and it drives the camera for you — tracking battles, base raids, expansions, and map control using computer vision.

Built for shoutcasters who want to step away from the wheel, or just want a smarter default camera while they focus on commentary.

## Download

Grab the latest `.exe` from [Releases](https://github.com/Alamander8/aoe2-auto-spectator/releases). No installation needed — just run it.

> **Pre-1.0 Notice**: This is an active development build. It works, but expect rough edges. Bug reports are very welcome.

## Requirements

- **Windows 10/11**
- **CaptureAge** (the spectator overlay for AoE2:DE)
- A 1920x1080 or 2560x1440 monitor (other 16:9 resolutions may work but are untested)

## How to Use

1. Download and run `AoE2AutoSpectator-vX.Y.Z.exe`
2. An outpost icon appears in your system tray, and a small overlay bar appears in the top-right corner
3. Open a replay in CaptureAge — the auto-spectator detects it and starts driving the camera
4. **Move your mouse** to instantly pause automation and take manual control
5. Stop moving and it resumes after a configurable delay (default: 5 seconds)

### Overlay Controls

| Button | What it does |
|--------|-------------|
| `||` / `>` | Pause / resume the auto-spectator |
| Reset arrow | Restart the spectator (new game) |
| Gear icon | Open settings |

The overlay bar is draggable — put it wherever you want.

### Settings

Click the gear icon on the overlay or right-click the tray icon:

- **Mouse detection**: Toggle whether mouse movement pauses the camera
- **Pause duration**: How long to wait after mouse stops before resuming (1-15 seconds)
- **Resolution**: Match to your monitor (hit the reset button after changing)
- **Stat cycling**: Automatically presses ALT+C to cycle the CaptureAge stats bar

## How It Works

The spectator analyzes the CaptureAge minimap in real-time using OpenCV:
- Detects player activity (unit movement, building placement, combat)
- Prioritizes action — fights over farming, raids over idle TCs
- Clicks the minimap to move the camera to points of interest
- Switches perspective between players based on who's doing what

## Reporting Bugs

Found something weird? [Open an issue](https://github.com/Alamander8/aoe2-auto-spectator/issues/new) and include:
- What happened vs. what you expected
- Your screen resolution
- The log file (found at `%APPDATA%\AoE2AutoSpectator\spectator.log`)

## License

MIT License — see [LICENSE](LICENSE) for details.
