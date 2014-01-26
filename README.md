## Hawkeye

Hawkeye is a library of highly specific user-agent CSS selectors. These are useful for targeting specific browser versions to work around edge case bugs and stuff.

**Inspiration for this repo comes from Rogie's [blog post](http://rog.ie/blog/html5-boilerplate-addon) about writing super specific user agent selectors in CSS.**

***

#### How it works

We've got this little snippet of JavaScript in the `<head>`:

```javascript
var b = document.documentElement;
b.setAttribute('data-useragent',  navigator.userAgent);
b.setAttribute('data-platform', navigator.platform );
b.className += ((!!('ontouchstart' in window) || !!('onmsgesturechange' in window))?' touch':'');
```

When loaded in a browser, the `data-useragent` attribute will return the user agent. Here's an example from Chrome 32:

```html
<html data-useragent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/32.0.1700.77 Safari/537.36">
```

We can use CSS to make a selector from a portion of this string:

```css
html[data-useragent*='Chrome/32.0'] { /* custom styles here */ }
```

***

Boom. Again, this is all based on Rogie's blog post, I just want to create a library of user agent selectors. If you have any ideas for improvements or anything, please open an issue/submit a PR! :)
