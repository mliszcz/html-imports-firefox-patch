# html-imports-firefox-patch

HTML Imports implementation seems to be broken in Firefox.
Enabling `dom.webcomponents.enabled` adds `import` attribute
to the `HTMLLinkElement`. This forces HTML Imports polyfill to
fall-back to native implementation.

This patch intercepts `document.createElement()` call from
the polyfill, thus needs to be loaded before HTMLImports.

For more details regarding the issue see:  
https://github.com/webcomponents/webcomponentsjs/issues/289
