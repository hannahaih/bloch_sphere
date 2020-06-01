# Qubit Bloch Sphere Visualization

A collection of visualization tools for the qubit Bloch sphere.
The Bloch sphere is a useful representation of the state of a single-qubit quantum computer.

![Example animated Bloch sphere](https://raw.githubusercontent.com/cduck/bloch_sphere/master/examples/example0.gif)

# Install

bloch\_sphere is available on PyPI:

```bash
python3 -m pip install bloch_sphere
```

## Prerequisites

Cairo needs to be installed separately to render videos.
See platform-specific [instructions for Linux, Windows, and macOS from Cairo](https://www.cairographics.org/download/).
Below are some examples for installing Cairo on Linux distributions and macOS.

**Ubuntu**

```bash
sudo apt-get install libcairo2
```

**macOS**

Using [homebrew](https://brew.sh/):

```bash
brew install cairo
```

# Usage

This package provides a command line tool to generate animations.
In your shell, run the following (run `animate_bloch -h` for help).
```bash
animate_block hadamard x y s s
```

# Code Examples

```python
from bloch_sphere.animate_bloch import do_or_save_animation, AnimState

@do_or_save_animation('my_animation', save=False, fps=20, preview=True)
# Or
#@do_or_save_animation('my_animation', save='gif', fps=20, preview=True)
#@do_or_save_animation('my_animation', save='mp4', fps=20, preview=False)
def animate(state: AnimState):
    state.x_gate()
    state.y_gate()
    state.s_gate()
    state.s_gate()
    ...
    state.wait()  # Pause at the end
```

![Example output animation](https://raw.githubusercontent.com/cduck/bloch_sphere/master/examples/example1.gif)

