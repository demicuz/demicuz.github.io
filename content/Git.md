---
title: "Git"
date: "2022-08-28"
lastmod: "2022-08-28"
---

A version control system. Maybe not the best in all aspects, but the most popular. Sane people use git clients like [[Sublime Merge]] or Magit.

**Basic commands**
- [[git merge]]
- [[git stash]]

**Other stuff**
- [[Git recipes and how-to's]]
- [[Git tips]]
- [[Git resources]]
- [[Git tags]]
- [[Git repo cleaning]]

### Git config
To view config: `git config --list`
Don't forget to set a local timezone: `git config --global log.date local` UPD: not sure if it works! And not sure if it's even needed.

### `.gitignore`
If you commit some file and then decide to not track it and add it to `.gitignore`, it still *will* be tracked. Tracked files are never ignored, see [git - File is not ignored despite adding it to .gitignore](https://stackoverflow.com/questions/66716064).

As for a separate `.gitignore` for each branch, It's kinda complicated. See [this gist](https://gist.github.com/wizioo/c89847c7894ede628071) and this [SO question](https://stackoverflow.com/questions/58332148/).

- [`.gitignore` ignore everything except a few files](https://stackoverflow.com/questions/987142/)
- [Whitelisting and subdirectories in Git](https://stackoverflow.com/questions/9162919/)

### Patches
I still don't quite understand how they work. They contain commit hashes, so they should only be applicable on the same repo, but I was somehow able to apply it to a repo with wiped out commit history.

**Tip**: to generate a patch from a commit on github, just add `.patch` to the commit URL.


### Commit info structure
Example:
```
tree 1334e254df78294aee11e6c914483bd7837c6930
parent 56ad2cf5d956fbc3860fbdc1c15a0073cae21223
author demicuz <pure.demicube@gmail.com> 1654647098 +0300
committer demicuz <pure.demicube@gmail.com> 1654647663 +0300

initial commit
```

Use `git cat-file commit <some-commit>` to view it. Yes, there is an **author**, and a **committer**. See more [here](https://ivan.bessarabov.com/blog/git-author-committer). And [here](https://stackoverflow.com/questions/750172)'s how to change committer and author.

### Submodules
```bash
git submodule add git@github.com:johndoe/leftpad # add a submodule
git submodule update --remote --merge # to update submodules
```

### Links
- [Reinventing Git interface](https://tonsky.me/blog/reinventing-git-interface/) by [[Nikita Prokopov]]