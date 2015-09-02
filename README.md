# LightBox

This is a CSS only implementation of a LightBox. It works near perfectly on many devices, including mobile phones, low end laptops, modern video game consoles and home PCs. Animation not available if not supported by the users browser (IE)

## Table of Contents

* [Creating a LightBox](#creating)
* [Defining properties](#defining)
* [Putting things in the LightBox](#innards)

<h3 id="creating">Creating a LightBox</h3>

Quite simply add `lightbox="lightbox"` (or just `lightbox`) to the `div` element you wish to make a LightBox. That's all you require to make a LightBox.

Make sure you add an element that doesn't need to be seen with an ID of `screenarea` like so: `<div id=screenarea />` or `<div id="screenarea"/>`. This is not seen and should only be used once per page, preferably at the start or end of the document.

---

<h3 id="defining">Defining Properties</h3>

Adding extra properties to the LightBox is quite easy. Just add a set of items to the input of the `lightbox`. Not required thanks to defaults (all defaults are shown), but very useful for controlling the UX.

#### Directional

Effects which direction the LightBox enters from.

* Right (`lightbox="right"` or add `-r` to end of ID [default])
* Left (`lightbox="left"` or add `-l` to end of ID)
* Top (`lightbox="top"` or add `-t` to end of ID)
* Bottom (`lightbox="bottom"` or add `-b` to end of ID)

#### Selectable

Specifies whether the user is able to select it or not.

* Selectable (`lightbox="selectable"` [default])
* Unselectable (`lightbox="noselect"`)

#### Speed

Specifies the speed at which the LightBox appears on screen. Always `inst` if there's no [support for transition (CSS)](http://caniuse.com/#feat=css-transitions).

* Normal (`lightbox="norm"` [default])
* Fast (`lightbox="fast"`)
* Slow (`lightbox="slow"`)
* Instant (`lightbox="inst"`)

Starting time (amount of wind-up)

* None (`lightbox="inst_start"` [default])

Can also be specified by radio inputs with ids of `lightfast`, `lightnorm`, `lightslow`, `lightinst`. Not required and completely optional.

---

<h3 id="innards">Putting things in the LightBox</h3>

These are the things you put inside the LightBox. These are heavily recommended and, although not required for it to work, will greatly increase the experience the user recieves.

#### Close

This is of utmost importance. If this is not included then it will fail to perform its function properly. Define using `<a href="#screenarea"/>`. It'll automatically add close. You can style it using the below:

##### Styles of Closing banner:

* Normal, changes to look its best (`lb_close=""` or `lb_close` [default, will change to match one of the below based on the direction the lightbox enters from. Doesn't need to be defined.])
* Top-Right (`lb_close="tr"`)
* Top-Left (`lb_close="tl"`)
* Bottom-Left (`lb_close="bl"`)
* Bottom-Right (`lb_close="br"`)

I do plan on adding more soon, such as colours, capitalisation and `:hover` options (`lb_closeh`). If you couldn't guess, this uses the `::before` and `::after` pseudo elements for its main part.

#### Content

The utmost important piece. Without this it's literally useless.

Directly supported elements:

* `article`
* `img`
* `video` (Won't be displayed if `autoplay` or `preload="auto"` attributes are found.)
* `iframe` (View LightBox\_Rules.md for more_)
* `canvas` (Define a width and height. Will be scaled to fit the limits)

Elements supported by wrapping in `article`:

* `audio` (Requires `controls` and no `autoplay`.)

#### Title


#### Gallery

Tools for creating a gallery in the box. Note that these do require you to create your own links to other parts of the gallery.

* Button Right (`lb_right=""` or `lb_right`)
* Button Left (`lb_left=""` or `lb_left`)
* Button Down (`lb_down=""` or `lb_down`)
* Button Up (`lb_up=""` or `lb_up`)
 
