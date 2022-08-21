---
title: "Intellij"
date: "2022-08-17"
lastmod: "2022-08-17"
---
Super-intelligent and super-bloated IDE. Or a family of IDEs.

### Importing projects
Is pain! See [this](https://intellij-support.jetbrains.com/hc/en-us/community/posts/115000097290-How-to-setup-Django-for-an-existing-project)! Like... WTF?!

Here's how to "import" a [[Django]] project:
```
A coworker of mine, had a different way of getting IntelliJ to recognize Django and thus far, it's been working for me so thought I'd share. 

Assuming you have an existing Django project from git (or wherever).

Now, in IntelliJ, use the File > New > Project... Yes, new project. Not new from sources, just new.

In the dialog that opens, select Python on the left and you should see Django as an option. Select that, give it the name of the directory (usually from git clone) in the `Application Name` field and click next.

Skip the "create from template" screen, next

In the next screen, in the "project Name" enter the name of the project (again, this should match the directory of your code), click next

It will tell you that the directory is not empty and ask if you want to override it, click yes (don't worry, it's not going to override any of your files).

That's it! You have a django project in the most unintuitive way possible, but slightly better than editing a file I guess.

Good luck
```
