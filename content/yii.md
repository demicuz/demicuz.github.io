---
title: "yii"
---

A [[PHP]] framework.

### Notes
Serve:
```bash
php yii serve [--port=8888]
```

Follows an MVC model.

`/config` - stores configs!
`/controller` - controllers
`/models` - models
`/views` - page templates (views)

More [here](https://www.yiiframework.com/doc/guide/2.0/en/start-workflow).

Has weird naming conventions that map to ID's. `actionSomeStuff` maps to action ID `some-stuff`. `SiteController` takes its views from `views/site`.
