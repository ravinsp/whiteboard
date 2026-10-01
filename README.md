# Whiteboard

**This is an AI-generated project**

Live page: https://ravinsp.github.io/whiteboard/

A simple whiteboard that runs in the browser, with almost no UI and fast keyboard shortcuts. The whole app is one file, `index.html`, with no dependencies and no build step.

## Running it

Open `index.html` directly in a browser, or serve the folder locally:

```sh
python -m http.server 8000
```

Then go to <http://localhost:8000>.

## Features

- **Pen** in 4 colors: black, red, blue, green.
- **Smart eraser**: click a line or text to delete the whole thing, or drag across several.
  - Whatever is under the eraser fades slightly so you can see what will be deleted.
  - Holding the right mouse button, or using a stylus's eraser end, erases while any tool is selected.
- **Text**: large text in the current pen color.
  - Press `T` and start typing at the mouse position.
  - In text mode, click existing text to edit it.
- **Rectangle tool**: drag from corner to corner. Hold `Shift` for a square.
- **Box auto-correct**: a box drawn with the pen snaps into a clean rectangle, even if it's rough or not quite closed.
  - Undo once to get your hand-drawn line back.
- **Arrow heads**: press `A` to add an arrow head to the end of the line you just drew with the pen.
  - If that line had snapped into a box, it goes back to your drawn line first.
- **Zoom and pan**: `Ctrl` + mouse wheel zooms around the cursor (a trackpad pinch works too); hold `Space` and drag to move around the board.
- **Undo / redo**, **PNG export**, and **auto-save**: the drawing and the current view are kept in the browser's local storage and survive a refresh.
  - PNG export saves what is currently on screen.

## Keyboard shortcuts

| Key | Action |
|---|---|
| `1`–`4` | Pick a color |
| `P` / `B` | Pen |
| `R` | Rectangle tool (press again to go back to the pen) |
| `E` | Eraser (press again to go back to the pen) |
| `T` / `Enter` | Text at the mouse position |
| `Esc` | Finish text and go back to the pen (`Ctrl+Enter` also finishes text) |
| `A` | Add or remove an arrow head on the last pen line (does nothing if the last tool used was the eraser, rectangle or text) |
| `Ctrl+Z` | Undo |
| `Ctrl+Y` / `Ctrl+Shift+Z` | Redo |
| `Ctrl+S` | Save the board as a PNG |
| `Del` | Clear the board (can be undone) |
| `?` | Show or hide the shortcut hint |

| Mouse / pen | Action |
|---|---|
| Left-drag | Use the current tool |
| Right-drag | Erase, with any tool selected |
| `Shift` + drag (rectangle tool) | Draw a square |
| `Ctrl` + wheel | Zoom in / out around the cursor |
| `Space` + drag | Pan around the board |

## Notes

- Saved drawings are kept in each browser separately. Clearing site data, or using a private window, starts with an empty board.
- When you open `index.html` directly from disk, some browsers keep that saved drawing apart from the one at `localhost:8000`, so the two can show different boards.
