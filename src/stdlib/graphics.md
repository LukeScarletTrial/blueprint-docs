# 2D Graphics & Windowing Engine

Blueprint provides zero-dependency, hardware-accelerated 2D windowing and double-buffered rendering directly in the standard library.

## Window Lifecycle

### `window_open(title: string, width: int, height: int): bool`
Creates a window with the given title and dimensions. Returns `true` if successful.

### `window_close()`
Destroys the active window and frees all graphics buffers.

### `window_should_close(): bool`
Returns `true` if the user clicked the close button or pressed Alt+F4.

### `window_poll()`
Dispatches operating system events (mouse, keyboard, window moves).

### `window_present()`
Flips the off-screen double buffer to the screen and syncs frame timing.

## Drawing Primitives

### `draw_clear(r: int, g: int, b: int)`
Fills the canvas with the specified RGB color (`0` to `255`).

### `draw_rect(x: int, y: int, w: int, h: int, r: int, g: int, b: int)`
Draws a filled solid rectangle.

### `draw_circle(cx: int, cy: int, radius: int, r: int, g: int, b: int)`
Draws a filled circle.

### `draw_line(x1: int, y1: int, x2: int, y2: int, r: int, g: int, b: int)`
Draws a line segment between `(x1, y1)` and `(x2, y2)`.

### `draw_text(text: string, x: int, y: int, size: int, r: int, g: int, b: int)`
Renders text onto the canvas with the specified font size and RGB color.

## Input Handling

### `is_key_down(key_code: int): bool`
Queries whether a specific key is pressed down.

## Complete Game Loop Example

```blueprint
@blueprint import Blueprint
Blueprint.Setup("2D Game Demo", true)

func Main(): [
    def opened = window_open("Blueprint 2D Canvas", 800, 600)
    if opened [
        // Clear background
        draw_clear(20, 24, 40)

        // Draw player rectangle
        draw_rect(100, 100, 50, 50, 230, 80, 60)

        // Draw collectible circle
        draw_circle(400, 300, 25, 240, 200, 50)

        // Draw UI text
        draw_text("Score: 100", 20, 20, 20, 255, 255, 255)

        // Present to screen
        window_present()
        window_close()
    ]
]
```
