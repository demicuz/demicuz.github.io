---
title: "Django Rest Framework"
date: "2022-12-10"
---

When deserializing data, you always need to call `is_valid()` before attempting to access the validated data, or save an object instance. If any validation errors occur, the `.errors` property will contain a dictionary representing the resulting error messages.

### Links
- [Django REST Framework Oversimplified - YouTube](https://www.youtube.com/watch?v=cJveiktaOSQ)
- [Field validation in serializers](https://www.django-rest-framework.org/api-guide/serializers/#validation)