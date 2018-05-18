# angularjs-sass-pack

This package is for quickly setting up sass workflow and has absolutely no jquery (we'll be using angular-bootstrap for meeting jquery dependencies via ui-bootstrap)

corrected bower.json file of important libraries so it plays well with wiredep and functions as intended!
*   font-awesome@5,
*   bootstrap-sass^3.2.0,
*   angular-bootstrap
*   angular-bootstrap-material
*   bootstrap-material-design@0.5.10, and much more




If the repo is working as intended then wiredep should pick up the dependencies without any fight :D

## Install:
`bower install angularjs-sass-pack --save`


> after much thought we have decided to just use `dist` files of the libraries in bower distribution to keep the size low (as the libraries have gone through the developement stage and are already super robust: feature complete as the angular-ui team puts it). Albeit, we do have all the files and modifications here on our github repo.


Libraries included with proper bower.json and dependencies:

*   bootstrap-sass
    *   removed jquery dependency

*   angular-bootstrap-material
    *   depencencies: bmd@0.5.10, ui-bootstrap([angular-bootstrap]())
*   bootstrap-material-design
    *   fixed version number for abm and removed jquery and js dependencies which are resolved by abm(with help of angular-bootstrap).

*   font-awesome-5
    *   added bower.json and using web-fonts-with-css



#### Recommended sass directory structure:

```bash
./sass/main.scss
./sass/components/  (for partials like buttons, carousel, cover, effects, animations, etc)
./sass/helpers/   (for partials like fonts, functions, mixins, variables(custom bootstrap variables), etc)
./sass/layout/    (for partials like base, footer, grid, header, etc)
./sass/pages/   (for partials like blog, contact, about, home, etc)
```



##### including fonts in main.scss

```scss
//include custom variable first
@import "./helpers/variables";

$icon-font-path: "../bower_components/angularjs-sass-pack/bootstrap-sass/assets/fonts/bootstrap/";
$fa-font-path: "../bower_components/angularjs-sass-pack/font-awesome/web-fonts-with-css/webfonts/";




```


##### grunt config for copying fonts to dist
consider using [our yeoman generator](https://google.com). This problem is already solved there.

```JS
// Copies remaining files to places other tasks can use
  copy: {
    dist: {
      files: [{
        expand: true,
        cwd: '.',
        src: 'bower_components/angularjs-sass-pack/font-awesome/web-fonts-with-css/webfonts/*',
        dest: 'path/to/dist'
      }, {
        expand: true,
        cwd: '.',
        src: 'bower_components/angularjs-sass-pack/bootstrap-sass/assets/fonts/bootstrap/*',
        dest: 'path/to/dist'
      }]
    }
  },
```



### Contribute
*   clone the repo
*   update packages
*   fix bower.json of all the packages and their depencencies
*   make a [pull request](https://help.github.com/articles/about-pull-requests/)
