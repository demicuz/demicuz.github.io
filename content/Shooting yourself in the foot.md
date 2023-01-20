---
title: "Shooting yourself in the foot"
date: "2022-09-06"
lastmod: "2022-09-06"
---

[A timeless classic](https://www-users.cs.york.ac.uk/susan/joke/foot.htm).

In [[C (language)|C]] it's extremely easy :)

[[C pitfalls]]

 Also, `mv` and `rm` commands. I once had a bunch of pngs named `1.png`, `2.png`, etc. But the numbering was in the wrong order, so I wrote a script to fix that:
```shell
mv 1.png 30.png
mv 2.png 12.png
# ...
mv 30.png 5.png
# ...
```

You can easily spot where it shot me in the foot. More than a half of the pngs were gone 🙂👍. Should've used a separate folder, renaming in-place is dangerous.