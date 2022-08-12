---
title: "Django"
---

A [[Python]] framework for creating websites and web apps.

### Notes
Use `timezone.now()` instead of `datetime` stuff.

To change your models, you have to `makemigrations`, than `migrate`.

`python manage.py shell` to open a shell and interact with Django API. Can write stuff to databases!
```Python
# Django provides a rich database lookup API that's entirely driven by
# keyword arguments.
>>> Question.objects.filter(id=1)
<QuerySet [<Question: What's up?>]>
>>> Question.objects.filter(question_text__startswith='What')
<QuerySet [<Question: What's up?>]>
```

When sending POST request, use `{% csrf_token %}`. Whatever that means.

`forloop.counter` indicates how many times the `for` tag has gone through its loop.

Should do `.save()` to commit changes to DB.

To create a custom `404` page, just add `404.html` to templates folder. Don't know why this works.

### Stuff to read later
- [Related objects reference](https://docs.djangoproject.com/en/4.0/ref/models/relations/)
- [Making queries](https://docs.djangoproject.com/en/4.0/topics/db/queries/#field-lookups-intro)
- [Passing variable from django template to view](https://stackoverflow.com/questions/29153593)
- [How to redirect to previous page in Django after POST request - Stack Overflow](https://stackoverflow.com/questions/35796195)

### Not that important, but interesting
- [Cross Site Request Forgery protection](https://docs.djangoproject.com/en/4.0/ref/csrf/)
- [Avoid race conditions using F()](https://docs.djangoproject.com/en/4.0/ref/models/expressions/#avoiding-race-conditions-using-f)

### Example projects
- [How To Build a Weather App in Django | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-build-a-weather-app-in-django)
