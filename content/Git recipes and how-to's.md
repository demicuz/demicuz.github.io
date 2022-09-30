---
title: "Git recipes and how-to's"
date: "2022-09-19"
---

### Squash two last commits
```shell
git rebase --interactive HEAD~2
```

And then instead of `pick` do either `fixup` or `squash`.

### Other links
- [6 типичных ошибок Git и как их исправить / Хабр](https://habr.com/ru/company/flant/blog/419733/)
- [oh shit! I want to split my commit into 2 commits!](https://wizardzines.com/comics/oh-shit-split-commit/)
- [Five Useful Git Tips - adit.io](https://adit.io/posts/2013-08-16-five-useful-git-tips.html)
- [How to create development branch from master on GitHub](https://stackoverflow.com/questions/39478482)
- [How do I squash two non-consecutive commits?](https://stackoverflow.com/questions/3921708)
- [How can one change the timestamp of an old commit in Git?](https://stackoverflow.com/questions/454734)

**To look into later**
- [Merge Branches but Keep Commit History](https://stackoverflow.com/questions/28550602)

See also [[Git resources]].