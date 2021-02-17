# GSTA - GSAP ScrollTrigger Animation
Launch gsap scrollTrigger plugin from your HTML DOM via data-attributes

## Requirements
In order to initialize this code you have to include several libraries in your project before start:

- jQuery

```
<!-- jQuery CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js" integrity="sha512-bLT0Qm9VnAYZDflyKcBaQ2gg0hSYNQrJ8RilYldYQ1FxQYoCLtUjuuRuZo+fjqhx/qtq/1itJ0C2ejDxltZVFg==" crossorigin="anonymous"></script>

<!-- jQuery NPM Install -->
npm i jquery
```

- gsap library, including scrollTrigger plugin
```

<!-- GSAP CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/gsap.min.js" integrity="sha512-1dalHDkG9EtcOmCnoCjiwQ/HEB5SDNqw8d4G2MKoNwjiwMNeBAkudsBCmSlMnXdsH8Bm0mOd3tl/6nL5y0bMaQ==" crossorigin="anonymous"></script>

<!-- GSAP ScrollTrigger CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/ScrollTrigger.min.js" integrity="sha512-QcYm1q7RbnXmwY7HJ0H7938IS0MalTPYqGUF0fIwQgEjMBt2tqjDBt+R5I+ppdwEohjMdHnFU0H+RxmrGQ8qcg==" crossorigin="anonymous"></script>

<!-- GSAP NPM Install -->
npm i gsap

<!-- GSAP ScrollTrigger is included when install node modlues -->
```

With this libraries installed in your project you just have to include the main file **gsap-scrolltrigger-animation.js** and everything is ready to start. This file includes the **gsap.registerPlugin(ScrollTrigger)** that is mandatory in order to run properly the plugin.

> **!IMPORTANT:** this repository is just a faster way to launch simply animations on scroll and it's based on scrollTrigger plugin, but this plugin is not provided with this code and a review of the Green Sock license is required if you want to include it on your project.

## Settings
Due this repository is not a plugin, nor library, the main setting of animations is quite simple and just have to link (from CDN) or install via node modules the required libraries and plugins. Once you have installed the mentioned libraries you can start creating animations directly on your HTML code without a single line of code.

## Trigger
First of all you have to set a **trigger** to initialize your animation on scroll through it. By default, data-gsta-trigger starts when the top of trigger element hits the 75% from viewport top. As gsap defines in their documentation this is written 'top 75%' and in this code is the same for the value start and end of the trigger element. This default value can be overwritted if a value is included into **data-gsta-trigger**. If this option is used, start/end trigger will be the same, so animation will start and end at same moment.

```
<!-- Default Trigger -->
<div id="myAnimation" data-gsta-trigger>
  <!-- Your content here -->
</div>

<!-- Custom Trigger -->
<div id="myAnimation" data-gsta-trigger="top center">
  <!-- Your content here -->
</div>
```
However, there are a few more data-attributes that can be used to get more control over triggers. **data-gsta-trigger-start** and **data-gsta-trigger-end** that defines different start/end points than default for trigger element. Keep in mind that data-gsta-trigger-start or data-gsta-trigger-end overwrite any value included in data-gsta-trigger.

```
<!-- Diferent Start Trigger Point -->
<div id="myAnimation" data-gsta-trigger data-gsta-trigger-start="top center">
  <!-- Your content here -->
</div>

<!-- Diferent End Trigger Point -->
<div id="myAnimation" data-gsta-trigger data-gsta-trigger-end="bottom center">
  <!-- Your content here -->
</div>

<!-- Diferent Start/End Trigger Point -->
<div id="myAnimation" data-gsta-trigger data-gsta-trigger-start="top center" data-gsta-trigger-end="bottom center">
  <!-- Your content here -->
</div>
```

In addition, there is a last option that it can be used if a fully scroll-based animation is needed, **data-gsta-trigger-scrub**. This option allows to create an animation that runs during scroll goes through given trigger start/end points.

```
<!-- Scrub Animation -->
<div id="myAnimation" data-gsta-trigger="top center" data-gsta-trigger-end="top top" data-gsta-trigger-scrub="true">
  <!-- Your content here -->
</div>
```

Feel free to try how far can this code can goes with gsap scrollTrigger and experiment by yourself to improve it. The documentation can be read follow up this link: https://greensock.com/docs/v3/Plugins/ScrollTrigger

## Animations
Then you can include your animation in any HTML tag by using **data-gsta-animation**. The repository includes five default animations:

```
<!-- Fade In -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein"></div>
</div>

<!-- Fade In Up -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein-up"></div>
</div>

<!-- Fade In Right -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein-right"></div>
</div>

<!-- Fade In Down -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein-down"></div>
</div>

<!-- Fade In Left -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein-left"></div>
</div>
```

## Duration
The animation comes with a .5s default duration but that duration can be changed by **data-gsta-duration** attribute. There is no duration limit so you can use any value from 0 to infinite seconds expressed in decimals, but never negative values.

```
<!-- Custom Duration -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein" data-gsta-duration=".7"></div>
</div>
```

## Delay
The animation doesn't comes with delay, so default delay is 0, but if a combination of animations is needed it can be included by **data-gsta-delay** attribute. As duration attribute it can be used from 0 to infinite seconds expressed in decimals.

```
<!-- Custom Delay -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein" data-gsta-delay=".3"></div>
</div>
```

## Stagger
If a banch of animations is needed it can be achieved by using the **data-gsta-stagger** attribute. But it necessary to remember that this attribute changes the behaviour of the code and it's not applied to the element itself but to the indicated target. All the targets for the stagger will share the same animation indicated on the parent element.

```
<!-- Stagger Animation -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein" data-gsta-stagger=".stagger-item">
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
  </div>
</div>
```

In this case an extra attribute can be used to set the delay for each stagger element. It can be done by using **data-gsta-stagger-each** attribute. Default value for this attribute is .3s if any other value is indicated, or data-gsta-stagger-each is no included on stagger parent.

```
<!-- Stagger Animation -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein" data-gsta-stagger=".stagger-item" data-gsta-stagger-each=".5">
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
  </div>
</div>
```
A general delay to set the stagger animation can be added to the parent in order to create the desired global animation effect. This delay will be applied to the entire stagger animation, not to each stagger item.

```
<!-- Stagger Animation -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein" data-gsta-stagger=".stagger-item" data-gsta-stagger-each=".5" data-gsta-delay=".5">
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
    <div class="stagger-item">Stagger Item</div>
  </div>
</div>
```
