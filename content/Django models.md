---
title: "Django models"
date: "2022-12-13"
---

ManyToMany is a cool feature!

Use `through=` to explicitly define the intermediate table:
```python
from django.db import models
 
class Course(models.Model):
    name    = models.CharField(max_length=30)
 
class Student(models.Model):
    name    = models.CharField(max_length=30)
    courses = models.ManyToManyField(Course, through="Enrollment")
 
class Enrollment(models.Model):
    student = models.ForeignKey(Student, on_delete=models.CASCADE)
    course  = models.ForeignKey(Course, on_delete=models.CASCADE)
    date    = models.DateField()
    mark    = models.IntegerField(max_value=5)
```

### Links
- [Django | Отношение многие ко многим (Many to Many)](https://metanit.com/python/django/5.7.php)