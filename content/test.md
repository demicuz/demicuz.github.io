---
date: "2023-01-28"
lastmod: "2023-01-28"
---
# Instructions

### Building and testing

__Requirements__
- OpenGL 3.3+
- GCC (haven't tested with Clang, but should be fine too)
- [GLFW](https://www.glfw.org/)
- [libcheck](https://github.com/libcheck/check) *(optional, for testing only)*
- [lcov](https://github.com/linux-test-project/lcov/) *(optional, for creating a test coverage report)*
- [Doxygen](https://www.doxygen.nl/) *(optional, for generating this documentation)*

**Commands**
- `make` to create a `3DViewer` executable
- `make tests` to run tests
- `make gcov_report` to create and open a test coverage report
- `make html` to generate this documentation and save it in `docs/html`
- `make insall DESTDIR=~` to install the executable in `~/.local/bin`

### Usage

Press `Load .obj file` button and choose an `.obj` file you want to view. Use the sliders to control the object's position, scale and rotation. If you want to set an exact value, `Ctrl + click` on a slider and enter it.