## 1.1.0

- Signing in with GitHub is goblog's job now. The button is a plain link to `/login/github`; the theme no longer assembles the authorize URL in an inline script, where `window.location` went into `redirect_uri` unescaped, nor handles the `?code=` that came back. goblog completes the exchange server-side against a `state` it minted, so a code obtained for one account can no longer be replayed into another visitor's browser (goblog #631, #637).
- The button's own URL comes from the server too, as `.github_login_url`, instead of being built with a template conditional in every theme (goblog #639).
- The email login posts to `/api/login/email` directly rather than rebuilding the site's origin first.
- **Requires goblog 0.12.0**, and the manifest now says so, so the installer refuses the combination rather than installing a theme whose sign-in button has no URL to point at. Upgrade goblog first. An older version of this theme still signs in on 0.12.0 — goblog restarts the flow when a callback arrives with no state (goblog #640) — but it gets there via a second round trip to GitHub, so update the theme rather than relying on that.

Note that this theme still renders markdown in the browser; goblog 0.10.0 moved that to the server for the other themes but it has not been ported here (#2).

## 1.0.1

- Inline scripts that call jQuery and highlight.js wait for `DOMContentLoaded`, so the theme keeps working when goblog defers its CDN scripts (goblog 0.11.0, goblogplatform/goblog#624). Without this, posts lose syntax highlighting, the GitHub login button does nothing and the post body is never inserted.
- The GitHub login button's `href` is set during parse with `document.getElementById(...).href` instead of jQuery, so the link is never briefly inert.
- Backward compatible: still works on older goblog.

## 1.0.0

- First release as a directory theme: the public templates and CSS of the `minimal` theme that was compiled into goblog up to 0.6.x, layered on goblog's default theme.
