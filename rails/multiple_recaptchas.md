# Multiple Recaptchas

If you end up having multiple forms, each with their own recaptch widget, using
the default `reset()` method won't always work. 

With multiple recaptchas, you need to specify the widget id of the widget you
want to reset. It's not easy to look these up; however, they're just a counter
that starts at 0. So widgetId = 0 is the widget for the first form registered, 1
the second, and so on.

An easy and brute force way to handle this is to just reset them all whenever
you need to reset one. A little overkill, but ensures the job is done:

```js
$(".g-recaptcha").each(function (index) { grecaptcha.reset(index);})
```
