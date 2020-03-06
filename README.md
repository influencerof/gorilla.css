# Gorilla.css [![GitHub release](https://img.shields.io/github/release/influencerof/Gorilla.css.svg)](https://github.com/influencerof/Gorilla.css/releases) [![CDNJS](https://img.shields.io/cdnjs/v/Gorilla.css.svg)](https://cdnjs.com/libraries/Gorilla.css) [![Build Status](https://travis-ci.com/influencerof/Gorilla.css.svg?branch=master)](https://travis-ci.com/influencerof/Gorilla.css) [![devDependencies Status](https://david-dm.org/influencerof/Gorilla.css/dev-status.svg)](https://david-dm.org/influencerof/Gorilla.css?type=dev) [![chat](https://img.shields.io/badge/chat-gitter-green.svg)](https://gitter.im/Gorilla-css/Lobby) [![npm version](https://badge.fury.io/js/Gorilla.css.svg)](https://www.npmjs.com/package/Gorilla.css)

> **We need your help!** Gorilla.css v2 is almost ready with lots of changes and updates. We want **your feedback**! You can follow the development on the [`dev`](https://github.com/influencerof/Gorilla.css/tree/dev) branch and give your feedback on the [issue tracker](https://github.com/influencerof/Gorilla.css/issues).
**Give Me Your Feedback!**

_Dope CSS Animations_

`Gorilla.css` is a bunch of amazing, frosty, chilling animations for you to use in your life. Great for the most dope people on the web.



### Animations

To Gorilla an element, add the class `Gorillad` to an element. You can include the class `infinite` for an infinite loop. Finally you need to add one of the following classes to the element:

| Class Name        |                    |                     |                      |
| ----------------- | ------------------ | ------------------- | -------------------- |
| `bounce`          | `flash`            | `pulse`             | `rubberBand`         |
| `shake`           | `headShake`        | `swing`             | `tada`               |
| `wobble`          | `jello`            | `bounceIn`          | `bounceInDown`       |
| `bounceInLeft`    | `bounceInRight`    | `bounceInUp`        | `bounceOut`          |
| `bounceOutDown`   | `bounceOutLeft`    | `bounceOutRight`    | `bounceOutUp`        |
| `fadeIn`          | `fadeInDown`       | `fadeInDownBig`     | `fadeInLeft`         |
| `fadeInLeftBig`   | `fadeInRight`      | `fadeInRightBig`    | `fadeInUp`           |
| `fadeInUpBig`     | `fadeOut`          | `fadeOutDown`       | `fadeOutDownBig`     |
| `fadeOutLeft`     | `fadeOutLeftBig`   | `fadeOutRight`      | `fadeOutRightBig`    |
| `fadeOutUp`       | `fadeOutUpBig`     | `flipInX`           | `flipInY`            |
| `flipOutX`        | `flipOutY`         | `lightSpeedIn`      | `lightSpeedOut`      |
| `rotateIn`        | `rotateInDownLeft` | `rotateInDownRight` | `rotateInUpLeft`     |
| `rotateInUpRight` | `rotateOut`        | `rotateOutDownLeft` | `rotateOutDownRight` |
| `rotateOutUpLeft` | `rotateOutUpRight` | `hinge`             | `jackInTheBox`       |
| `rollIn`          | `rollOut`          | `zoomIn`            | `zoomInDown`         |
| `zoomInLeft`      | `zoomInRight`      | `zoomInUp`          | `zoomOut`            |
| `zoomOutDown`     | `zoomOutLeft`      | `zoomOutRight`      | `zoomOutUp`          |
| `slideInDown`     | `slideInLeft`      | `slideInRight`      | `slideInUp`          |
| `slideOutDown`    | `slideOutLeft`     | `slideOutRight`     | `slideOutUp`         |
| `heartBeat`       |

Full example:

```html
<h1 class="Gorillad infinite bounce delay-2s">Example</h1>
```

[Check out all the animations here!](https://influencerof.github.io/Gorilla.css/)

It's possible to change the duration of your animations, add a delay or change the number of times that it plays:

```css
.yourElement {
  animation-duration: 3s;
  animation-delay: 2s;
  animation-iteration-count: infinite;
}
```

## Usage with Javascript

You can do a whole bunch of other stuff with Gorilla.css when you combine it with Javascript. A simple example:

```javascript
const element =  document.querySelector('.my-element')
element.classList.add('Gorillad', 'bounceOutLeft')
```

You can also detect when an animation ends:

```javascript
const element =  document.querySelector('.my-element')
element.classList.add('Gorillad', 'bounceOutLeft')

element.addEventListener('animationend', function() { doSomething() })
```

You can use this simple function to add and remove the animations:

```javascript
function GorillaCSS(element, animationName, callback) {
    const node = document.querySelector(element)
    node.classList.add('Gorillad', animationName)

    function handleAnimationEnd() {
        node.classList.remove('Gorillad', animationName)
        node.removeEventListener('animationend', handleAnimationEnd)

        if (typeof callback === 'function') callback()
    }

    node.addEventListener('animationend', handleAnimationEnd)
}
```

And use it like this:

```javascript
GorillaCSS('.my-element', 'bounce')

// or
GorillaCSS('.my-element', 'bounce', function() {
  // Do something after animation
})
```

Notice that the examples are using ES6's `const` declaration, dropping support for IE10 and some aging browsers. If you prefer, switch the `const` to `var` declarations and IE10 and some old browsers will get support (they still have to provide [classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) support, so do your [research](https://caniuse.com/#feat=classlist)).

## Setting _Delay_ and _Speed_

### Delay Class

It's possible to add delays directly on the element's class attribute, just like this:

```html
<div class="Gorillad bounce delay-2s">Example</div>
```

| Class Name | Delay Time |
| ---------- | ---------- |
| `delay-1s` | `1s`       |
| `delay-2s` | `2s`       |
| `delay-3s` | `3s`       |
| `delay-4s` | `4s`       |
| `delay-5s` | `5s`       |

> _**Note**: The default delays are from 1 second to 5 seconds only. If you need custom delays, add it directly to your own CSS code._

### Slow, Slower, Fast, and Faster Class

It's possible to control the speed of the animation by adding these classes, as a sample below:

```html
<div class="Gorillad bounce faster">Example</div>
```

| Class Name | Speed Time |
| ---------- | ---------- |
| `slow`     | `2s`       |
| `slower`   | `3s`       |
| `fast`     | `800ms`    |
| `faster`   | `500ms`    |

> _**Note**: The `Gorillad` class has a default speed of `1s`. If you need custom duration, add it directly to your own CSS code._

## Custom Builds

Gorilla.css is powered by [gulp.js](https://gulpjs.com/), which means you can create custom builds pretty easily. First of all, you’ll need Gulp and all other dependencies:

```sh
$ cd path/to/Gorilla.css/
$ npm install
```

Next, run `npx gulp` to compile your custom builds. For example, if you want only some of the “attention seekers”, simply edit the `Gorilla-config.json` file to select only the animations you want to use.

```javascript
"attention_seekers": {
  "bounce": true,
  "flash": false,
  "pulse": false,
  "shake": true,
  "headShake": true,
  "swing": true,
  "tada": true,
  "wobble": true,
  "jello":true
}
```

## Accessibility

Gorilla.css supports the [`prefers-reduced-motion` media query](https://webkit.org/blog/7551/responsive-design-for-motion/) so that users with motion sensitivity can opt out of animations. On supported platforms (currently all the majors browsers and OS), users can select "reduce motion" on their operating system preferences and it will turn off CSS transitions for them without any further work required.

## License

Gorilla.css is licensed under the MIT license. (https://opensource.org/licenses/MIT)

## Code of Conduct

This project and everyone participating in it is governed by the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to [callmeelton@gmail.com](mailto:callmeelton@gmail.com).

## Contributing

Pull requests are the way to go here. We only have two rules for submitting a pull request: match the naming convention (camelCase, categorised [fades, bounces, etc]) and let us see a demo of submitted animations in a [pen](https://codepen.io). That **last one is important**.
