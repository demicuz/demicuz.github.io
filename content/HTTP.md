---
title: "HTTP"
---

### `GET` and `POST`
According to the HTTP specification, you should use the POST method when you're using the form to change the state of something on the server end. For example, if a page has a form to allow users to add their own comments, like this page here, the form should use POST. If you click "Reload" or "Refresh" on a page that you reached through a POST, it's almost always an error -- you shouldn't be posting the same comment twice -- which is why these pages aren't bookmarked or cached.

You should use the GET method when your form is, well, getting something off the server and not actually changing anything. For example, the form for a search engine should use GET, since searching a Web site should not be changing anything that the client might care about, and bookmarking or caching the results of a search-engine query is just as useful as bookmarking or caching a static HTML page.

==Don't use GET for storing/sending sensitive data!==

##### Links
- [http - What is the difference between POST and GET?](https://stackoverflow.com/questions/3477333)
- [Чем отличаются HTTP-методы GET и POST — Блог HTML Academy](https://htmlacademy.ru/blog/boost/frontend/get-vs-post)
