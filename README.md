# Conway's Game Of Life implemented with the Dioxus framework
An implementation of [Conway's game of life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life) using the Dioxus framework,
ported from the [rust wasm tutorial](https://rustwasm.github.io/docs/book/game-of-life/introduction.html).

While the code from the original tutorial is about 50% rust, 50% JavaScript, with the Dioxus framework the code can be 100% Rust.

## Install and run
* Install cargo and rust
* Install the dioxus API: cargo dioxus install
* Run in debug mode with the dioxus cli: dx serve --platform=web
* Point your browser at: http://localhost:8080

## Methodology
Defines a GameOfLifeGrid component that renders the game of life (with several control buttons),
and a FramesPerSecond component which shows how many frames per seconds are being rendered (which
depends on the monitor frame rate).

This is stitched together using a use_animation_frame() hook returns a frame_id that can be used
to trigger use_effect calls to render each frame (for the grid, and frames per second).  Also returns
frames_running, which can be set false or true to stop or start the frames.