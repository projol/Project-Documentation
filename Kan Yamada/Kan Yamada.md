# Kan Yamada
**DEV URL** - [http://cms.yigserver.com/kan-yamada/v0.1/] un/pw - yig/yig

 ## Folder Strucutre
> **folder structure** : protected/modules/cms/themes/v3
  - **lib *(includes source files)***
    - **js**
        *use custom.js for writing custom javascript codes*
        - jQuery JavaScript Library v3.4.1 [jQuery](https://jquery.com/)
        - Bootstrap v4.0.0 [Bootstrap](https://getbootstrap.com)
        - Slick slider v1.8.0 [Slick Slider](http://kenwheeler.github.io)
        - Swup js v2 [Swup js Documentation](https://swup.js.org/) *(for changing the page content without reloading the page)*
 
    - **scss**
        - **theme**
            *includes all custom css files broken down into partials files which are compiled by importing in **theme.scss** file*
        - **thirdparty**
            *includes css libraries such as bootstrap, carousel, fancybox, fontawesome*
            - Bootstrap v4.0.0 [Bootstrap](https://getbootstrap.com)
            - Slick slider v1.8.0 [Slick Slider](http://kenwheeler.github.io)
            - Font Awesome 4.7.0 [FontAwesome](https://fontawesome.com/)

- **dist *(includes complied files)***
    - css *(compiled and minified css files)*
    - fonts
        *custom fonts - includes font icons and font family*
    - img
    - js *(compiled and minified js)*

## How to use Swup js

First thing we need to do is prepare our HTML content. Define the elements that are being animated and elements (containers) that need to be replaced. Let’s assume we want to fade in/out the content of main element and replace it’s contents.

Add swup id to tell swup to replace the content of that element and your animation class to tell swup to wait for that element to animate. Both are adjustable in options and are not related to each other (you can animate completely different elements than the containers).
### 1. HTML structure
```
<html>
  <head>
    <title>Homepage</title>
  </head>
  <body>
    <main id="swup" class="transition-fade">
      <h1>This is homepage</h1>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
        labore et dolore magna aliqua.
      </p>
      <a href="/someOtherPage">Go to other page</a>
    </main>
  </body>
</html>
```
### 2. Enable Swup
```
const swup = new Swup(); // only this line when included with script tag
```

### 3. Swup CSS
At this point your page is already enhanced as swup will stop page from reloading a replace the content. This is especially good with a preload plugin which can make your page blazing fast.

…but let’s continue. Add CSS for the element animation.

```
.transition-fade {
  transition: 0.4s;
  opacity: 1;
}

html.is-animating .transition-fade {
  opacity: 0;
}
```
And believe it or not, that’s it! We’re all set, or at least for our simple fade in/fade out example…
Swup loads the page, handles classes for the css animation, waits for the animation to finish/page to load, replaces content and fades your content back. Swup also changes the title of your page to the loaded one

> **NOTE:** Some plugins are required to be reinitiated after page load, or else the plugins won't work. for this we use swup:contentReplaced event
```
    document.addEventListener('swup:contentReplaced', function () {
        // do something when content is replaced
        $(document).scrollTop(0); // scrolls to top of the page
        smoothScroll(); // smooth scroll on page when clicked on link referencing to element on the same page
        headerSlider(); // to enable slick slider after page load
    });
    ```