bootstrap-custom-build
# bootstrap-custom-build

> build bootstrap css for custom appply

## Build Setup

``` bash
# install dependencies
npm install

# build custom css
npm run css-c

# build all css(include bootstrap)
npm run css-m
```

## Scripts

```json
  "scripts": {
    "css-c": "npm-run-all --parallel css-lint css-compile-c --sequential css-prefix-c css-minify-c",
    "css-compile-c": "node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 scss/bootsrap/4.1.3/bootstrap-custom.scss stylesheets/bootsrap/4.1.3/bootstrap-custom.css",
    "css-prefix-c": "postcss --config build/postcss.config.js --replace \"stylesheets/bootsrap/4.1.3/bootstrap-custom.css\" \"!stylesheets/bootsrap/4.1.3/bootstrap-custom.min.css\"",
    "css-minify-c": "cleancss --level 1 --source-map --source-map-inline-sources --output stylesheets/bootsrap/4.1.3/bootstrap-custom.min.css stylesheets/bootsrap/4.1.3/bootstrap-custom.css",
       
    "css-m": "npm-run-all --parallel css-lint css-compile --sequential css-prefix css-minify",
    "css-lint": "stylelint --syntax scss \"scss/bootsrap/4.1.3/**/*.scss\"",
    "css-compile": "node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 scss/bootsrap/4.1.3/bootstrap.scss stylesheets/bootsrap/4.1.3/bootstrap.css && node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 scss/bootsrap/4.1.3/bootstrap-grid.scss stylesheets/bootsrap/4.1.3/bootstrap-grid.css && node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 scss/bootsrap/4.1.3/bootstrap-reboot.scss stylesheets/bootsrap/4.1.3/bootstrap-reboot.css && node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 scss/bootsrap/4.1.3/bootstrap-custom.scss stylesheets/bootsrap/4.1.3/bootstrap-custom.css",
    "css-prefix": "postcss --config build/postcss.config.js --replace \"stylesheets/bootsrap/4.1.3/*.css\" \"!stylesheets/bootsrap/4.1.3/*.min.css\"",
    "css-minify": "cleancss --level 1 --source-map --source-map-inline-sources --output stylesheets/bootsrap/4.1.3/bootstrap.min.css stylesheets/bootsrap/4.1.3/bootstrap.css && cleancss --level 1 --source-map --source-map-inline-sources --output stylesheets/bootsrap/4.1.3/bootstrap-grid.min.css stylesheets/bootsrap/4.1.3/bootstrap-grid.css && cleancss --level 1 --source-map --source-map-inline-sources --output stylesheets/bootsrap/4.1.3/bootstrap-reboot.min.css stylesheets/bootsrap/4.1.3/bootstrap-reboot.css && cleancss --level 1 --source-map --source-map-inline-sources --output stylesheets/bootsrap/4.1.3/bootstrap-custom.min.css stylesheets/bootsrap/4.1.3/bootstrap-custom.css"
  }
```

## Package

```
  "devDependencies": {
    "npm-run-all": "^4.1.3",
    "node-sass": "^4.9.1",
    "postcss-cli": "^5.0.1",
    "clean-css-cli": "^4.1.11",
    "stylelint": "^9.3.0",
    "stylelint-config-recommended-scss": "^3.2.0",
    "stylelint-config-standard": "^18.2.0",
    "stylelint-order": "^0.8.1",
    "stylelint-scss": "^3.1.3"
  },
```

