---
title: "Python debugging"
date: "2023-02-07"
---

From Andrej Karpathy:
> debugging in Python:
> - `print()`s alone: too simple
> - `import pdb; pdb.set_trace()`: too complex
> - `import code; code.interact(local=locals())`: just right simply drops you into interpreter, perfect for 95% of debugging

Tutorial: [How To Debug Python with an Interactive Console](https://www.digitalocean.com/community/tutorials/how-to-debug-python-with-an-interactive-console).

There's also `breakpoint()`: [Python breakpoint()](https://www.digitalocean.com/community/tutorials/python-breakpoint).