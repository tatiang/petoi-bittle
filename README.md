# Bittle Mission Control 🚀

A browser-based interface for programming the [Petoi Bittle](https://www.petoi.com/products/bittle) robot dog. Students use visual command blocks to build a mission sequence, then send it to the robot over Bluetooth — no app installation required.

**Live app:** [https://tatiang.github.io/petoi-bittle/mission-control.html](https://tatiang.github.io/petoi-bittle/mission-control.html)

**Repository:** [https://github.com/tatiang/petoi-bittle](https://github.com/tatiang/petoi-bittle)

---

## Table of Contents

- [For Students (2nd – 6th Grade)](#for-students-2nd--6th-grade)
- [For Teachers](#for-teachers)
- [For IT Staff](#for-it-staff)
- [For Developers](#for-developers)

---

## For Students (2nd – 6th Grade)

### What is this?

This is **Bittle Mission Control** — a website where you can program a robot dog named Bittle! You pick moves, put them in order, and hit **GO!** to watch Bittle carry out your mission.

### How to use it

1. **Turn Bittle on.** Flip the power switch on its back. Wait for it to stand up and beep.
2. **Open the website** in Chrome or Microsoft Edge.
3. **Click the green "Connect Robot" button.** A list will pop up — choose the one with Bittle's name in it.
4. **Click the colored blocks** on the left to add moves to your mission.

   | Block | What Bittle Does |
   |-------|-----------------|
   | 🚶 Walk | Walks forward |
   | 🪑 Sit | Sits down |
   | 👋 Wave | Waves one paw |
   | 🦒 Stretch | Does a big stretch |
   | 🤸 Flip | Does a backflip |
   | 💪 Pushup | Does push-ups |
   | 🔁 Repeat 2x | Copies your whole list and runs it twice |

5. **Press ▶ GO!** — the block that Bittle is doing right now will glow pink.
6. **Press ⏹ Stop** at any time to stop early.
7. **Click the ✕ on any block** to remove it from your mission.

### The Secret Move 🥷

Want to unlock a hidden **Ninja Roll** block? Here's your hint:

> Make Bittle **Wave**, then **Flip** — right in a row, anywhere in your mission.

A new block will appear if you do it!

### Saving and loading your mission

- **💾 Save Mission** — downloads your mission as a file so you can use it again later.
- **📂 Load Mission** — opens a mission file you saved before.

### Tips

- Bittle needs about **2.5 seconds** between each move — be patient, it's not broken!
- If Bittle isn't moving, ask your teacher to help reconnect it.
- The **🔊 Sound** button turns Bittle's beeping on or off.

---

## For Teachers

### Overview

Bittle Mission Control runs entirely in the browser — nothing to install. Students open the live link in Chrome or Edge, connect their Bittle over Bluetooth, and use colored blocks to build a sequential program. It is designed for grades 2–6 and intentionally mirrors the logic of block-based programming environments like Scratch.

**Live app:** [https://tatiang.github.io/petoi-bittle/mission-control.html](https://tatiang.github.io/petoi-bittle/mission-control.html)

### Before class — checklist

- [ ] Each Bittle robot is **charged** (USB-C port on its back; full charge ~1.5 hrs).
- [ ] Each Bittle has been **Bluetooth-paired** to its assigned computer once (see [IT Staff → Pairing](#bluetooth-pairing-one-time-per-computer)).
- [ ] Each student computer uses **Chrome or Microsoft Edge** (not Safari, not Firefox).
- [ ] **Mac users:** students know to select the `cu.` port — see the connection tip below.

### Connecting a robot

When a student clicks **Connect Robot**, a helper screen appears with instructions, then the OS port picker opens. Guide them:

- **On a Mac:** choose the port starting with **`cu.`** — for example, `cu.Bittle77_SSP`. Ports starting with `tty.` look the same but will not transmit data to Bittle.
- **On Windows:** choose the **`COM`** port — for example, `COM4`.

### Feature guide

| Feature | Notes for teachers |
|---------|-------------------|
| **Command blocks** | Click to add to the mission strip. Students can remove individual blocks with the ✕ button. Blocks are disabled while a mission is running. |
| **▶ GO!** | Sends the full sequence to Bittle. Each command waits 2.5 seconds before the next — this pacing is intentional and mirrors the robot needing time to complete each motion. |
| **⏹ Stop** | Appears during a running mission. Stops cleanly between commands (does not interrupt a motion mid-way). |
| **🔁 Repeat 2x** | Duplicates the entire current sequence. Good for introducing the concept of loops without any syntax. |
| **Challenge banner** | Shows the current secret unlock goal (Wave → Flip). Resets automatically if the sequence is broken. |
| **🥷 Ninja Roll** | Unlocked by meeting the challenge. Disappears again if students remove the Wave+Flip pair. |
| **🔊 Sound** | Mutes or unmutes all of Bittle's beeps, *including the startup melody*. This setting is **saved permanently on the robot** — once muted, Bittle stays quiet across power cycles until the button is pressed again. |
| **💾 Save / 📂 Load Mission** | Students can save their mission as a `.json` file and reload it next class. Works as a simple portfolio or homework artifact. |

### Classroom management tips

- **One robot per pair of students** works well — one student builds the mission, the other verifies the sequence before pressing GO.
- **The 2.5-second delay** between commands is a built-in thinking prompt: "What did Bittle just do? What's next?"
- **If a student closes the tab** while connected, the app automatically releases the Bluetooth port so the next student can connect without rebooting.
- **If "port already in use" appears**, close all browser tabs and reopen the page — another tab has the port locked.
- **Bittle's random idle behaviors** (spontaneous movements after a few minutes of inactivity) are disabled automatically every time the app connects. If they reappear, disconnect and reconnect.

### Troubleshooting

| Symptom | Likely cause | Fix |
|---------|-------------|-----|
| "Could not connect" | Bittle not paired, or turned off | Turn Bittle off and on; disconnect and reconnect Bluetooth in OS settings |
| Connected but Bittle doesn't move | Wrong port selected on Mac | Disconnect, reconnect, choose the `cu.` port |
| "Port already in use" | Another tab has the port | Close all other Bittle tabs; refresh the page |
| Bittle moves on its own | Firmware idle behavior | The app disables this on connect — disconnect and reconnect to re-suppress it |
| Sound button label seems wrong | Robot was muted/unmuted before connecting | Press the button once to resync the label |
| Mission stops partway through | Bluetooth range or low battery | Move computer closer to Bittle; check battery |

---

## For IT Staff

### System requirements

| Requirement | Details |
|-------------|---------|
| **Browser** | Google Chrome 89+ or Microsoft Edge 89+. Web Serial API is not available in Safari or Firefox. |
| **Operating system** | macOS 10.15 (Catalina) or newer; Windows 10 or newer. Linux is supported but untested in this classroom context. |
| **Network** | HTTPS access to `tatiang.github.io` to load the page (port 443). **No network traffic during robot operation** — all communication is local Bluetooth serial. |
| **Firewall / proxy** | No special rules needed. The app has no backend, no WebSocket, no telemetry. |
| **Software installation** | None. No drivers, extensions, or packages required. |

### Bluetooth pairing (one-time per computer)

Pairing must be done once per computer. The robot remembers paired devices.

#### Mac
1. Turn Bittle on and wait ~5 seconds for it to complete its startup routine.
2. Go to **System Settings → Bluetooth**.
3. Find `Bittle` (or `Bittle77`, etc.) in the "Nearby Devices" list and click **Connect**.
4. After pairing, two virtual ports appear in the browser picker: `cu.BittleXX_SSP` and `tty.BittleXX_SSP`. Students must always choose the **`cu.`** entry — the `tty.` port opens without error but does not transmit data.

#### Windows
1. Turn Bittle on.
2. Go to **Settings → Bluetooth & devices → Add device → Bluetooth**.
3. Select `Bittle` from the scan list. No PIN required.
4. After pairing, Bittle appears as a COM port in Device Manager (e.g. `COM4`). That same label appears in the browser port picker.

### Web Serial — browser permission model

- The **first connection** requires a user gesture (clicking Connect Robot) and the student selecting a port from the OS picker. This is enforced by the browser and cannot be scripted around.
- The browser **remembers the granted port** for `tatiang.github.io`. On future visits the picker appears again (required by the spec) but the previously granted port is pre-listed.
- If a student's Chrome profile is wiped, they simply re-grant access on the next visit.
- No data is sent to any server. The app has no login, no cookies beyond the browser's own site-permission record, and no analytics.

### Known platform-specific issues

| Issue | Platform | Explanation & fix |
|-------|----------|-------------------|
| `tty.` port silently fails | macOS | macOS creates two virtual serial devices for every Bluetooth SPP pairing. Only `cu.` (call-up) transmits; `tty.` (teletype) blocks waiting for a carrier signal that never arrives. The app shows a pre-picker modal and a post-connect warning banner if it detects a slow pipe. |
| Zombie port lock | macOS / Windows | If Chrome is force-quit while a port is open, the OS may hold the port lock until the browser fully exits. Fix: close all Chrome windows and relaunch, or power-cycle Bittle. The app registers `beforeunload` and `pagehide` event handlers to release the port on normal tab close or navigation. |
| Phantom "connected" state | macOS | The browser can report a successful connection while the Bluetooth data pipe is clogged (e.g., robot turned off after pairing but before connecting). The app detects this with a 1.5-second write timeout and shows a warning. |

### Self-hosting / private deployment

The app is a single self-contained HTML file with no external dependencies.

1. Copy `mission-control.html` to any web server.
2. The page **must be served over HTTPS** (or `localhost`) — the Web Serial API is disabled on plain HTTP by the browser's secure-context requirement.
3. No build step, no Node.js, no database.

If you need to update the live URL referenced in the app itself, search for `tatiang.github.io` in `mission-control.html` (it only appears in comments).

---

## For Developers

### Tech stack

| Layer | Choice | Reason |
|-------|--------|--------|
| Language | Vanilla HTML / CSS / JS | No build step; single file; editable in any text editor; deployable by drag-and-drop |
| Serial API | [Web Serial API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Serial_API) | Native browser API; no driver or Electron required |
| Hosting | GitHub Pages | Free, HTTPS by default, deploys on every push to `main` |
| Styling | CSS custom properties | No framework dependency; easily themeable |

### File structure

```
mission-control.html
├── <style>       CSS (custom properties, no external frameworks)
├── <body>        HTML (modal, header, toolbox panel, mission panel)
└── <script>      JavaScript
    ├── Constants             (BAUD_RATE, timeouts, delays)
    ├── State variables       (connState, port, writer, mission, …)
    ├── Connection management (connectSerial, disconnectSerial, forceCleanup)
    ├── Startup configuration (applyStartupSettings — sends 'z' on connect)
    ├── Connection UI         (setConnState, updateConnectionUI)
    ├── sendCommand()
    ├── Mission execution     (runMission, stopMission)
    ├── toggleMute()
    ├── Mission builder       (addToMission, removeFromMission, duplicateSequence, renderMission)
    ├── Challenge evaluator   (evaluateChallenge)
    └── Export / Import       (saveMission, loadMission)
```

### Connection state machine

A 4-state string replaces a boolean to prevent partial-state bugs and debounce rapid clicks during transitions:

```
'disconnected' ──► 'connecting' ──► 'connected' ──► 'disconnecting' ──► 'disconnected'
```

All UI changes are driven by a single `setConnState(state)` call. The Connect/Disconnect button is disabled during `'connecting'` and `'disconnecting'` states.

### Teardown sequence

Each step races against `CLOSE_TIMEOUT_MS` (2500 ms) to prevent indefinite hangs caused by a clogged Bluetooth write buffer — a common failure mode on macOS + Bluetooth Classic:

```javascript
await Promise.race([writer.close(), sleep(CLOSE_TIMEOUT_MS)]);  // 1. end stream
await Promise.race([outputDone,     sleep(CLOSE_TIMEOUT_MS)]);  // 2. drain pipe
await Promise.race([port.close(),   sleep(CLOSE_TIMEOUT_MS)]);  // 3. release OS lock
```

`outputDone` (the `pipeTo()` promise) is silenced with `.catch(() => {})` at creation time so a race timeout never surfaces as an unhandled promise rejection.

### Key serial commands

| Command | Persists? | Notes |
|---------|-----------|-------|
| `kwkF\n` | No | Walk forward |
| `ksit\n` | No | Sit |
| `khi\n`  | No | Wave |
| `kstr\n` | No | Stretch |
| `kbk\n`  | No | Backflip |
| `kpu\n`  | No | Push-ups |
| `krl\n`  | No | Ninja Roll |
| `b\n`    | **Yes — EEPROM** | Toggle all sounds + startup melody. NyBoard: EEPROM addr 282. BiBoard: addr 81 + NVS key `bootSndState`. |
| `z\n`    | **No — RAM only** | Toggle `RANDOM_MIND` idle behaviors. Resets on every power cycle; the app re-sends it automatically 800 ms after every successful connection. Silently ignored if firmware was not compiled with `#define RANDOM_MIND`. |
| `\n`     | No | No-op; sent immediately after connect as a health check to verify the write pipe isn't clogged. |

### Adding new command blocks

Add a `.block` `<div>` to the toolbox grid in the HTML:

```html
<div class="block" onclick="addToMission('Spin', 'kvt', '🌀')">
    <span>🌀</span>Spin
</div>
```

Arguments: `(displayName, serialCode, emoji)`. The serial code is sent verbatim with `\n` appended. No other changes are required — `renderMission()`, `runMission()`, save/load, and `evaluateChallenge()` all operate on the generic `{ name, code, emoji }` object shape.

### Mission file format (v1)

```jsonc
{
  "version": 1,
  "savedAt": "2026-03-30",
  "commands": [
    { "name": "Walk", "code": "kwkF", "emoji": "🚶" },
    { "name": "Wave", "code": "khi",  "emoji": "👋" }
  ]
}
```

`loadMission()` validates that `commands` is a non-empty array of objects with `name`, `code`, and `emoji` string fields before replacing state, so a corrupt or wrong file can never silently wipe a student's work. The `version` field enables forward-compatible migrations if the schema changes.

To add a cloud-save or share-link feature, `POST` this object to an API endpoint — no other changes are needed.

### Adding new challenges

`evaluateChallenge()` scans `mission` for a specific adjacent pair of `code` values. To add a second challenge:

```javascript
// New challenge: Walk immediately followed by Pushup → unlocks "Parade March"
const marchUnlocked = mission.some((item, i) =>
    item.code === 'kwkF' && mission[i + 1]?.code === 'kpu'
);
```

Then show/hide the corresponding secret block and update the banner text.

### Known issues / future work

- **Write-only serial:** The app sends commands but never reads responses. Reading Bittle's serial output would enable acknowledgement-based sequencing (send the next command only after the robot confirms the previous motion is complete) and surface battery level or error codes.
- **Sound button state desync:** `isMuted` resets to `false` on every page load. The app cannot read the robot's EEPROM state, so if Bittle was already muted before connecting, the button label is out of sync until pressed once. A read-back of EEPROM address 282 on connect would solve this.
- **Flat inter-command delay:** All commands wait `CMD_DELAY_MS` (2500 ms). Some motions (backflip, push-up sequence) take longer. A `delayMs` field on the block definition would allow per-command timing.
- **No drag-to-reorder:** Mission blocks can be added and individually removed but not reordered. [SortableJS](https://sortablejs.github.io/Sortable/) (one `<script>` tag) would add drag-and-drop reordering with minimal integration.
- **Single active challenge:** The challenge system supports one unlock at a time. `evaluateChallenge()` is easy to extend for multiple simultaneous challenges — see above.
