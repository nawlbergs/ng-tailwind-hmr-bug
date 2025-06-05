### angular hmr + tailwind + scss + @import = no hmr
if using tailwind: `@use "tailwindcss";`
it seems that HMR does not work for any styles thar are @imported.

 - `$ npm install`
 - `$ npm run start`

inside the `myapp/styles.scss` file:

```scss
// COMMENTING THIS OUT MAKES HMR WORK AGAIN FOR @use "./other-styles.scss";
@use "tailwindcss";

@use "./other-styles.scss";
```

I also tried the older:
```scss
@import "tailwindcss";

@import "./other-styles.scss";
```
