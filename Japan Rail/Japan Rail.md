# JR - Japan Rail
**DEV URL** - [http://yonefujapan.xsrv.jp/php7/JapanRailTimes/web/]
| Username | Password |
| ----- | ----- |
| JRTAdmin | 123edcxzaqws |
 ## Folder Strucutre
> **folder structure** : web/themes/cmsApp/assets
  - **lib *(includes source files)***
    - **js**
        *use custom.js for writing custom javascript codes*
        - jQuery JavaScript Library v3.4.1 [jQuery](https://jquery.com/)
        - Bootstrap v4.0.0 [Bootstrap](https://getbootstrap.com)
        - FancyBox v3.3.5 [Fancy box](http://fancyapps.com/fancybox/)
 
    - **scss**
        - **theme**
            *includes all custom css files broken down into partials files which are compiled by importing in **theme.scss** file*
            *Bootstrap default styles have been overwritten. the file is in **theme/_variables.scss**, use this file to overwrite default styles or add new variables*
        - **thirdparty**
            *includes css libraries such as bootstrap, carousel, fancybox, fontawesome*
            - Bootstrap v4.0.0 [Bootstrap](https://getbootstrap.com)
            - Owl Carousel v2.1.1 [Owl Carousel](http://owlcarousel2.github.io/OwlCarousel2/)
            - FancyBox v3.3.5 [Fancy box](http://fancyapps.com/fancybox/)
            - Font Awesome 4.7.0 [FontAwesome](https://fontawesome.com/)

- **dist *(includes complied files)***
    - css *(compiled and minified css files)*
    - fonts
        *custom fonts - includes font icons and font family*
        *fonticons are included in fonts folder and css file for it is **fontastic.css***
        login to : [http://app.fontastic.me/] 
        **Font Name** - jr-rail

        | Username | Password |
        | ----- | ----- |
        | prajwol_mi@yonefu.info | miracle123 |
    - img
    - js *(compiled and minified js)*
## Overwriting Bootstrap variables
Make sure to import the **_variables.scss** file before importing the **bootstrap files**
## Color Theme
For color theme, the default bootstrap variables have been overwritten
If you need to change the colors you can change it in **_variables.scss** file.

Change the following variables, or add new according to the requirements.
```
  $theme-colors: map-merge((
    "primary":    $primary,     
    "secondary":  $secondary,   
    "success":    $success,
    "info":       $info,
    "warning":    $warning,
    "purple":    $purple,
    "magenta":    $magenta,
    "danger":     $danger,
    "light":      $light,
    "dark":       $dark,
    "black":       $black
  ), $theme-colors);
```  
  
## Grid and container width
The default bootstrap variables are overwritten to manage the grid and container widths to match design

Change the following variables, or add new according to the requirements.
```
  $grid-breakpoints: (
  xs: 0,
  sm: 576px,
  md: 768px,
  lg: 992px,
  xl: 1400px,
  xxl: 1700px
);

  $container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 940px,
  xl: 1200px,
  xxl: 1400px
);
```

## Sticky Header
> find this code in lib/js/custom.js

The sticky header is done through jQuery in two steps
1. In the first step, a class **"ready"** is added to the header nav, which adds a fixed position to header and other necessary styles. The class is added when the header scrolls 100px up from the top of the window
2. The second step adds a class **"fixed"** to the header nav, which slides down the navigation and sticks to the top. The class is added when the header scrolls 300px up from the top.

## SVG mapping - Japan map
In the artcle list page, when searching via prefecture map, a modal containing the prefecture list and japan map is included.
When a prefecture is selected, a class **selected** is added to the prefecture in the map. 
The class is styled with fill color for svg map, which shows a highlight for the selected prefecture.
