## 1.0.1

- Inline scripts that call jQuery and highlight.js wait for `DOMContentLoaded`, so the theme keeps working when goblog defers its CDN scripts (goblog 0.11.0, goblogplatform/goblog#624). Without this, posts lose syntax highlighting, the GitHub login button does nothing and the post body is never inserted.
- The GitHub login button's `href` is set during parse with `document.getElementById(...).href` instead of jQuery, so the link is never briefly inert.
- Backward compatible: still works on older goblog.

## 1.0.0

- First release as a directory theme: the public templates and CSS of the `minimal` theme that was compiled into goblog up to 0.6.x, layered on goblog's default theme.
