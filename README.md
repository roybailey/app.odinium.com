# app.odinium.com
Wesite for app.odinium.com

See https://github.com/rafgraph/spa-github-pages/tree/gh-pages for how to get SPA working on GitHub pages.

1) Move the `404.html` file into the docs folder
2) Change the base name in ReactBrowser and number of path parameters to keep depending on whether you have custom domain or need the repository name in the path
3) Inject the redirect script from the index.html into the new bundle index.html, ensuring the redirect script comes before the bundle is loaded
 
