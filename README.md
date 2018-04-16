# Upgrade Browser

This repository contains a simple `upgrade-browser.html` you can show to your visitors if their browser is not supported. The buttons and download links for the following browsers will be shown: `"chrome", "edge", "firefox", "opera", "safari"`.

## 👍 How to use

I recommend that you do some feature checking before showing the page. Here's an example of what you could do if you only wanted to supported browsers with support for `CSS grids` and `custom elements`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Upgrade Browser (demo)</title>
</head>
<body>

<p>Only show this if CSS grids and custom elements are supported.</p>

<script type="text/javascript">
  (function () {
    var supportsGrid = ("grid-column" in document.documentElement.style || "msGridColumn" in document.documentElement.style);
    var supportsCustomElements = ("customElements" in window);
    var supported = supportsCustomElements && supportsGrid;

    // Show the upgrade-browser dialog if the browser is not supported
    if (!supported) {
      window.location = "upgrade-browser.html?nofirefox&noopera";
    }
  })();
</script>
</body>
</html>
```

As seen in the above code at `window.location = "upgrade-browser.html?nofirefox&noopera";`, the URL of the `upgrade-browser.html` file may contain a query that specifies which browsers that should not be recommended to the users. You are able to specify the following fragments in the query.

- "nochrome"
- "noedge"
- "nofirefox"
- "noopera"
- "nosafari"

You are also able to specify a `title`, a `subtitle` and a `backgroundColor` as a hex without the `#`.

## 🎉 License

MIT license