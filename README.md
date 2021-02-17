# scrollTriggerHTMLData
Launch gsap scrollTrigger plugin from your HTML DOM via data-attributes

## Requirements
In order to initialize this code you have to include several libraries in your project before start:

- jQuery
- gsap library, includin scrollTrigger plugin

With this libraries installed in your project you just have to include the main file **gsta.js** and everything is ready to start.

**Important:** this repository is just a faster way to launch simply animations on scroll and it's based on scrollTrigger plugin, but this plugin is not provided with this code and a review of the Green Sock license is required if you want to include it on your project.

## Settings
Due this repository is not a plugin, nor library, the main setting of animations is quite simple and just have to link (from CDN) or install via node modules the required libraries and plugins. Once you have installed the mentioned libraries you can start creating animations directly on your HTML code without single line of coding.

### Animations
First of all you have to set a **trigger** to initialize your animation on scroll through it.

```
<div id="myAnimation" data-gsta-trigger>
  <!-- Your content here -->
</div>
```


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

### Duration
The animation comes with a .5s default duration but that duration can be changed by **data-gsta-duration** attribute. There is no duration limit so you can use any value from 0 to infinite seconds expressed in decimals, but never negative values.

```
<!-- Custom Duration -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein" data-gsta-duration=".7"></div>
</div>
```

### Delay
The animation doesn't comes with delay, so default delay is 0, but if a combination of animations is needed it can be included by **data-gsta-delay** attribute. As duration attribute it can be used from 0 to infinite seconds expressed in decimals.

```
<!-- Custom Delay -->
<div id="myAnimation" data-gsta-trigger>
  <div data-gsta-animation="fadein" data-gsta-delay=".3"></div>
</div>
```

### Stagger
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
