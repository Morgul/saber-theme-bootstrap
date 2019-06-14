# Saber Theme Bootstrap

> A Saber theme using BootstrapVue with Bootswatch support.

## Features

* [BootstrapVue][bootstrap-vue] included, all components allowed.
* [Bootswatch][bootswatch] theme support
* Bootstrap `variables.scss` and `overrides.scss` style override support
* Custom style support
* Flexible layouts, with options
* Sweet, sugary goodness
* Not known to cause cancer _(except in the state of California)_
* Plus Ultra!

## Install

**NPM**
```bash
$ npm install saber-theme-bootstrap
```

**Yarn**
```bash
$ yarn add saber-theme-bootstrap
```

## Layouts

Below is the list of included layouts. All layouts support the `bootswatch` property in their front-matter. This allows the bootswatch theme to be overridden on a per-page basis.

If a layout has a `layout-options` section, these are additional properties that can be set in the page's front-matter, under the key `layout-options`.

* `default` - Contains the header and footer, wrapping content in a bootstrap `container`.
  * `layout-options`:
    * `fluid` - If `true`, wraps the content in a `container-fluid` instead.

## Site Config

This theme supports all the normal properties of a Saber site (i.e. `title`), but adds `favicon` and `logo`:

```yml
siteConfig:
  title: My Site
  favicon: assets/images.favicon.png
  logo: assets/images/logo.png
```

These paths are relative to the project's root directory, and will be required through webpack.

## Theme Config

Part of the point of Bootstrap (and hence this theme) is to allow people to get up and going very quickly, while still having the ability to customize the look and feel of their site as they grow. To me, this means that this theme needs to make it easy to pick a theme other than the default Bootstrap theme, and even be able to easily customize the theme to be something entirely unique. That is why the theme's main configuration is centered around the ability to modify the bootstrap theme.

### Bootswatch Support

For most people, it's easiest to simply pick one of the excellent [Bootswatch][bootswatch] themes. Simply specify the one you want with the `bootswatch` key:
```yml
themeConfig:
  bootswatch: 'cyborg'
```

[bootswatch]: https://bootswatch.com/

### Bootstrap Variables & Overrides

If, however, you want to override some (or all) of the bootstrap variables, you cant specify a `variables.scss` file. You can also specify a `overrides.scss` file, if you want to override some portion of bootstrap after the variables and mixins have been imported. Simply specify the paths to the files. _(All paths are assumed relative to the project root.)_

```yml
themeConfig:
  variables: 'style/variables.scss'
  overrides: 'style/overrides.scss'
```

### Additional Styles

Sometimes, however, you want to go crazy and do your own thing. That's totally fine; you can specify your own styles, and as long as you have the appropriate loader installed, they'll be included _after_ the bootstrap styles.


```yml
themeConfig:
  styles:
    - 'style/custom-theme.scss'
    - 'style/other-styles.scss'
    - 'style/other-other-style.css'
```
