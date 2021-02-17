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

<div id="myAnimation" data-gsta-trigger>
  <!-- Your content here -->
</div>
