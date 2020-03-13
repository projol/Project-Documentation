# JR - Japan Rail
**DEV URL** - [http://yonefujapan.xsrv.jp/php7/JapanRailTimes/web/]
 ## Folder Strucutre
> **folder structure** : web/themes/cmsApp/assets
  - lib *(includes source files)*
    - **js**
        *use custom.js for writing custom javascript codes*
    - **scss**
        - **theme**
            *includes all custom css files broken down into partials files which are compiled by importing in **theme.scss** file*
            *Bootstrap default styles have been overwritten. the file is in **theme/_variables.scss**, use this file to overwrite default styles or add new variables*
        - **thirdparty**
            *includes css libraries such as bootstrap, carousel, fancybox, fontawesome*

- dist *(includes complied files)*
    - css
    - fonts
        *custom fonts - includes font icons and font family*
        *fonticons are included in fonts folder and css file for it is **fontastic.css***
        login to : [http://app.fontastic.me/] 
        **Font Name** - jr-rail
        username - prajwol_mi@yonefu.info
        password - miracle123
    - img
    - js
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
