# minimal-website-template

Minimal but powerful website template.

## Features

- JS reactivity by [Alpine.js](https://alpinejs.dev/)
- CSS preprocessor by [Less.js](https://lesscss.org/)
- UI components by [Semantic UI](https://semantic-ui.com/)
  - bundled with FontAwesome v5
  - depended on [jQuery](https://jquery.com/)
- Animation by [Animate.css](https://animate.style/)
- Icons by [FontAwesome Free](https://fontawesome.com/)

## Remarks

### General

All resources are referenced from CDNs and use the non-minimized version with the major version number as the dependency.
For production, please check for the minimized version and hardcode version number for stability.

### Semantic UI

`semantic.js` is optional, some components in Semantic UI require JavaScript.
The `semantic.js` is dependent on `jQuery`.
You can remove both if you don't need those components.

### Alpine.js

Alpine.js is referenced as CommonJS. It will initialize itself once the script is evaluated.
If you need to call Alpine.js' global API before `Alpine` is initialized, like `Alpine.data`, you need to call them in the `alpine:init` DOM event.
See the [documentation on the lifecycle](https://alpinejs.dev/essentials/lifecycle#alpine-initialization)

Alpine.js can also be referenced as an ESM module.
But Alpine is not exported to the `window` object and will not be initialized by itself.
You can import Alpine via your module. See the [documentation on installation](https://alpinejs.dev/essentials/installation#as-a-module)

```js
import Alpine from "https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/module.esm.js";

// Optional, this will expose alpine to the window object.
window.Alpine = Alpine;

Alpine.start();
```
