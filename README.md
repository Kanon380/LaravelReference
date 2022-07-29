# Laravel_vite_to_webpack

## Run if vite doesn't work

### webpack mix official migration guide
https://github.com/laravel/vite-plugin/blob/main/UPGRADE.md#migrating-from-vite-to-laravel-mix

### webpack.mix.js
```js
const mix = require('laravel-mix');
const path = require('path');

/*
 |--------------------------------------------------------------------------
 | Mix Asset Management
 |--------------------------------------------------------------------------
 |
 | Mix provides a clean, fluent API for defining some Webpack build steps
 | for your Laravel applications. By default, we are compiling the CSS
 | file for the application as well as bundling up all the JS files.
 |
 */

mix.webpackConfig({
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "resources/js")
    }
  }
});

mix.js('resources/js/app.jsx', 'public/js')
  .react()
  .postCss('resources/css/app.css', 'public/css', [
    //
  ]);
```
