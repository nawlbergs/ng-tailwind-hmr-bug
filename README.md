## angular hmr + tailwind + scss + @import = no hmr
if using tailwind: `@use "tailwindcss";`
it seems that HMR does not work for any `scss` styles that are @imported

## To replicate

 - `$ npm install`
 - `$ npm run start`
 - modify styles inside `./other-styles.scss`   HMR does not update browser.
 - Comment out `@use "tailwind"`... now changing `./other-styles.scss` works.

Note: Importing .css files seems to work as expected.


```scss
// COMMENTING THIS OUT MAKES HMR WORK AGAIN FOR @use "./other-styles.scss";
@use "tailwindcss";

// CHANGING STYLES IN AN @IMPORTED/@USE SCSS FILE.. does not trigger HMR:
@use "./other-styles.scss";
```

I also tried the older @import methods:
```scss
@import "tailwindcss";

@import "./other-styles.scss";
```

There is a branch `css-only` that does not use scss.
The HMR seems to work fine in with just css.
