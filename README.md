### Use SASS
1. Go [SASS](https://sass-lang.com/install) use command line 
2. Download [Github dart-sass](https://github.com/sass/dart-sass/releases/tag/1.32.7)
3. Create new projet in Visual code
4. Create folder sass
5. Create file `style.scss` in sass folder
6. Execute in terminal  `.\dart-sass\sass sass/style.scss` for generate final css (`style.css`)
7. Execute `.\dart-sass\sass sass/style.scss style.css.map` for match

**Détails**
- style.css (CSS final)
- style.css.map (Allows browser mapping between CSS and SCSS)

**Usage options**
`.\dart-sass\sass --help` : Orders lists
`.\dart-sass\sass sass/style.scss style.css --watch` : Regenerates the style.css file on each modification

**Lib for reset css**
https://jgthms.com/minireset.css/

1. Create folder lib in folder sass
2. Create file `reset.scss`
3. Paste the [minreset.css](https://raw.githubusercontent.com/jgthms/minireset.css/master/minireset.min.css) code
4. Import the file in `style.scss`: `@import "libs/reset.scss";`

**Documentation**
https://sass-lang.com/guide

**Advantages**
- Nesting: `.btn{ … &hover {…}  }`
- Legacy: `%btn {…}` : `@extend %btn` ou  `.btn {@extend .btn}`
- Variables: 
    * 	`$secondary: rgb(105, 143, 214)`, usage: `.btn { color : $secondary }`
    * 	`$padding: 20px;`, usage: `.btn { padding : $pading + 10px }`
    * 	Can be import: `@import "responsive/style.scss";`
    * 	`$medium-size : 768px ;` 
    * 	`$medium : "only screen and (min-width :#{$medium-size})"`
    * 	`@media #{$medium}{...} `
- Fonctions: `color: darken(red, 10);` ou `ligten($blue, 20);` ou `rgba($blue, 0.5);`
- Mixins : allow you to create a block of properties that can be reused in several places
    * 	`@mixin rotate($rotation: 10deg) { transform: rotate($rotation) }`
    * 	`.btn { @include rotate(60deg);`  
    * conditions: `.btn { @if (lightness($primary) > 50%) { color: #000; } @else { color: #FFF; } }`
- Loop = https://grafikart.fr/tutoriels/sass-boucles-1107#autoplay

**Invite de commande**
    * Compress css: `.\dart-sass\sass sass/style.scss style.css –style=compressed`
    * Compress css no source: `.\dart-sass\sass sass/style.scss style.css –style=compressed –no-source-map`
    * Use watch.bat --> `.\dart-sass\sass sass/style.scss style.css --watch`

**Utilisez Boostrap**
- [Download Boostrap file source](https://getbootstrap.com/docs/5.0/getting-started/download/#source-files)
- Import the boostrap scss sources into a sass / boostrap folder
- Create file `style.scss` in folder sass
- Utiliser le fichier `style.css` dans votre `index.html`: `<link href="style.css" rel="stylesheet" crossorigin="anonymous">`
- We can 
    * import full boostrap (`@import "./boostrap/bootstrap.scss";`) en modfiant les valeurs des variables ex:`$primary: red;`
    * import composents part  boostrap minimum confguration /functions, /variables, /mixins, /utilities, /root, /reboot
