# app.odinium.com
Wesite for app.odinium.com

See https://github.com/rafgraph/spa-github-pages/tree/gh-pages for how to get SPA working on GitHub pages.

1) Move the `404.html` file into the docs folder
2) Change the base name in ReactBrowser and number of path parameters to keep depending on whether you have custom domain or need the repository name in the path
3) Inject the redirect script from the index.html into the new bundle index.html, ensuring the redirect script comes before the bundle is loaded
 
## Deploying updates from SPA

* copy all distribution files into `/docs` folder
* check `/docs/404.html` is the same as the `/404.html` template (it should be as it's generic)
* copy the code block from `/index.html` into `/docs/index.html` to handle the SPA location, see below

```html

    <!-- Start Single Page Apps for GitHub Pages -->
    <script type="text/javascript">
      // Single Page Apps for GitHub Pages
      // MIT License
      // https://github.com/rafgraph/spa-github-pages
      // This script checks to see if a redirect is present in the query string,
      // converts it back into the correct url and adds it to the
      // browser's history using window.history.replaceState(...),
      // which won't cause the browser to attempt to load the new url.
      // When the single page app is loaded further down in this file,
      // the correct url will be waiting in the browser's history for
      // the single page app to route accordingly.
      (function(l) {
        if (l.search[1] === '/' ) {
          var decoded = l.search.slice(1).split('&').map(function(s) { 
            return s.replace(/~and~/g, '&')
          }).join('?');
          window.history.replaceState(null, null,
              l.pathname.slice(0, -1) + decoded + l.hash
          );
        }
      }(window.location))
    </script>
    <!-- End Single Page Apps for GitHub Pages -->

```