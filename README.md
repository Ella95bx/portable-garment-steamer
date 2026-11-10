# Portable Garment Steamer Simulator

## Purpose

This small browser project demonstrates variables, state, conditional logic, timers, and user events. It simulates a portable garment steamer with four states: `Off`, `Heating`, `Ready`, and `Steaming`.

The project is self-contained. Its HTML, CSS, and JavaScript are all in `index.html`, and it does not use external libraries or APIs.

## How to open it

1. Open the `portable-garment-steamer` folder.
2. Double-click `index.html`, or drag it into a web browser.
3. No installation or internet connection is required.

## Simulation rules

- The water level starts at 50 and stays between 0 and 100.
- Pressing **Power** while the steamer is `Off` starts a 5-second preheat if water is available.
- When preheating finishes, the state changes from `Heating` to `Ready`.
- Pressing **Power** in any running state immediately changes the state to `Off`. Any heating or steaming timer is stopped.
- Starting again always begins a new 5-second preheat.
- Steam starts only when **Hold to steam** is newly pressed while the state is `Ready`.
- Holding the steam button during preheating does not automatically start steam later.
- While steaming, 10 simulated water units are used every second.
- Releasing or cancelling the steam press changes `Steaming` back to `Ready` only if the steamer is still running and has water.
- When the water reaches 0, steaming stops and the state changes to `Off`.
- **Refill water** works only in `Off`. It fills the tank to 100 but does not switch the steamer on.
- Water units and the 5-second preheat are demonstration parameters.
- `Off` means the simulation has stopped. It does not mean that a real appliance has cooled down.

## Steam button input

The steam button supports a mouse, touch input, and the keyboard (`Space` or `Enter`). Steam ends when the input is released or cancelled, when the button loses focus, or when the browser tab/window loses focus.
