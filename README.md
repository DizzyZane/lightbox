# LightBox CSS

This is a CSS only implementation of a LightBox. It works near perfectly on many devices, including mobile phones, low end laptops, modern video game consoles and home PCs. Animation not available if not supported by the users browser (IE).<link rel="stylesheet" href="lightbox.css">

<div id="toc"><h2>Table of Contents</h2><hr><ul><a href="#creating"><li>Creating a lightbox</li></a><a href="#defining"><li>Defining properties</li></a><a href="#innards"><li>Putting things in the lightbox</li></a><a href="#notrightorder"><li>What happ when I don't put things in the right order?</li></a></ul></div>

* [Creating a LightBox](#creating)
* [Defining properties](#defining)
* [Putting things in the LightBox](#innards)
* [What happens when I don't put things in the right order?](#notrightorder)

<h3 id="creating">Creating a LightBox</h3>

Quite simply add `lightbox="lightbox"` (or just `lightbox`) to the `div` or other element you wish to make a LightBox. That's all you require to make a LightBox. Unless you go with the label+input version, where you'll need an input (`<input type="radio" name="lightbox" id="lightbox-1">`) followed by the normal lightbox. (`<input type="radio" name="lightbox" id="lightbox_lbl"><lightbox lightbox></lightbox>`)

    <input type="radio" name="lightbox" id="lightbox_lbl">
    <lightbox lightbox>
     <label for="remove_lightbox"></label>
     <!-- Content -->
    </lightbox>

    <lightbox lightbox id="lightbox">
     <a href="screenarea"></a>
    </lightbox>

<del>Make sure you add an element that doesn't need to be seen with an ID of `screenarea` like so: `<div id=screenarea ></div>` or `<div id="screenarea"></div>`. This is not seen and should only be used once per page, preferably at the start or end of the document.</del> Completely unneccesary, but still somewhat useful. If you're using the label, put a `<input type="radio" name="lightbox" id="remove_lightbox">` at the top of your document.<div id=screenarea ></div><input type="radio" name="lightbox" id="remove_lightbox">

<hr id="defining">

### Defining Properties

Adding extra properties to the LightBox is quite easy. Just add a set of items to the input of the `lightbox`. Not required thanks to defaults (all defaults are shown), but very useful for controlling the UX.

#### Directional

Effects which direction the LightBox enters from.

* Right (`lightbox="right"` or add `-r` to end of ID (`id="lightbox-r"`) {default}). [Demo](#lightbox)<div id="lightbox" lightbox><a href="#screenarea"></a><h1>Default lightbox.</h1></div>
* Left (`lightbox="left"` or add `-l` to end of ID). [Demo](#lightbox-l)<div id="lightbox-l" lightbox><a href="#screenarea"></a><h1>Lightbox from Left.</h1></div>
* Top (`lightbox="top"` or add `-t` to end of ID). [Demo](#lightbox-t)<div id="lightbox-t" lightbox><a href="#screenarea"></a><h1>Lightbox from top.</h1></div>
* Bottom (`lightbox="bottom"` or add `-b` to end of ID). [Demo](#lightbox-b)<div id="lightbox-b" lightbox><a href="#screenarea"></a><h1>Lightbox from bottom.</h1></div>

#### Selectable

Specifies whether the user is able to select it or not.

* Selectable (`lightbox="selectable"` {default}). [Demo](#lightbox)
* Unselectable (`lightbox="nosel"`). [Demo](#lightbox-noselect)<div id="lightbox-noselect" lightbox="nosel"><a href="#screenarea"></a><h1>Unselectable lightbox.</h1></div>

#### Speed

Specifies the speed at which the LightBox appears on screen. Always `inst` if there's no <a href="http://caniuse.com/#feat=css-transitions" target="_blank">support for transition (CSS)</a>.

* Normal (`lightbox="norm"` {default}). [Demo](#lightbox)
* Fast (`lightbox="fast"`). [Demo](#lightbox-fast)<div id="lightbox-fast" lightbox="fast"><a href="#screenarea"></a><h1>Fast lightbox.</h1></div>
* Slow (`lightbox="slow"`). [Demo](#lightbox-slow)<div id="lightbox-slow" lightbox="slow"><a href="#screenarea"></a><h1>Slow lightbox.</h1></div>
* Instant (`lightbox="inst"`). [Demo](#lightbox-inst)<div id="lightbox-inst" lightbox="inst"><a href="#screenarea"></a><h1>Instant lightbox.</h1></div>

Starting time (amount of wind-up)

* None (`lightbox="inst_start"` [default])

Can also be specified by radio inputs with ids of `lightfast`, `lightnorm`, `lightslow`, `lightinst`. Not required and completely optional.

<hr id="innards">

### Putting things in the LightBox

These are the things you put inside the LightBox. These are heavily recommended and, although not required for it to work, will greatly increase the experience the user recieves.

#### Close

This is of utmost importance. If this is not included then it will fail to perform its function properly. Define using `<a href="#screenarea"/>`. It'll automatically add close. You can style it using the below:

##### Styles of Closing banner:

* Normal, changes to look its best (`lb_close=""` or `lb_close` {default, will change to match one of the below based on the direction the lightbox enters from. Doesn't need to be defined.}) [Demo](#lightbox).
* Top-Right (`lb_close="tr"`)
* Top-Left (`lb_close="tl"`)
* Bottom-Left (`lb_close="bl"`)
* Bottom-Right (`lb_close="br"`)

I do plan on adding more soon, such as colours, capitalisation and `:hover` options (`lb_closeh`). If you couldn't guess, this uses the `::before` and `::after` pseudo elements for its main part.

<h3 id="addingcontent">Content</h3>

The utmost important piece. Without this it's literally useless.

Directly supported elements:

* `article`. [Demo](#lightbox-article)<div id="lightbox-article" lightbox><a href="#screenarea"></a><article>This is an <code>Article</code> element. <div id="lipsum"> <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque dapibus, purus ac rutrum hendrerit, nisl est viverra elit, et viverra arcu dolor nec lorem. Vestibulum at mollis lectus. Sed vel pretium ipsum. Vestibulum eu molestie ipsum, a interdum orci. Nulla erat neque, pellentesque eu accumsan maximus, fringilla vitae neque. Vivamus egestas mauris sed lacus rutrum eleifend. Nunc congue aliquet risus, vel condimentum arcu sollicitudin ac. Sed sed neque id felis malesuada tempus. Aenean ac magna consequat, sodales enim sed, molestie lacus. </p> <p> Vivamus efficitur rutrum urna, mattis pharetra dui tincidunt et. Suspendisse eget pellentesque lectus. Suspendisse feugiat leo ac faucibus commodo. In mattis, enim ut iaculis faucibus, sapien felis finibus nisl, eu tempus massa justo id enim. Donec id volutpat ipsum, id luctus dui. Quisque turpis risus, cursus a consectetur a, aliquet ac nisi. Praesent bibendum dui ac arcu molestie, sed lobortis mi facilisis. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et pulvinar eros, in sagittis mauris. </p> <p> Suspendisse rutrum sit amet turpis consequat volutpat. Curabitur pellentesque nisi rhoncus, ultricies magna ac, mattis erat. Vivamus ante ipsum, tincidunt sollicitudin ultricies in, pellentesque imperdiet turpis. Vestibulum lacinia fringilla nisl, ut tincidunt ligula ullamcorper sit amet. Ut vitae lacus non libero aliquam tempus vitae sit amet nisi. Aenean non molestie ante, ac tincidunt urna. Suspendisse imperdiet augue accumsan magna ullamcorper mattis. Curabitur efficitur condimentum nulla et tristique. Quisque egestas vehicula molestie. Suspendisse at enim felis. Nullam vitae lorem ornare, finibus arcu eget, mollis diam. Vivamus eu metus eget neque suscipit cursus et vel augue. Morbi rhoncus congue luctus. Sed non ante pharetra, molestie tortor non, pellentesque ex. Aliquam a nisi neque. Nulla porta pretium massa vel ultrices. </p> <p> Etiam tellus lectus, laoreet quis sem non, vulputate maximus augue. In non volutpat sapien, vel laoreet tortor. Cras id mi at dolor aliquet ultricies non nec enim. Quisque ut commodo ipsum, ac tempus leo. Nam eget purus a urna pellentesque sagittis id sed felis. Sed vulputate eu dui eget ornare. Mauris dictum rutrum interdum. Curabitur fermentum diam at dui pellentesque, vel mattis ipsum venenatis. In ut erat quam. Vestibulum blandit tristique sapien id posuere. Mauris malesuada dapibus est, dignissim cursus purus ullamcorper in. Suspendisse at nunc ex. Donec in ultrices augue. </p> <p> Pellentesque consequat eget risus sit amet vulputate. Etiam efficitur augue eu viverra scelerisque. Sed scelerisque fringilla ullamcorper. Pellentesque sodales odio et purus egestas, ultrices fringilla tellus blandit. Nam ullamcorper sem et nunc elementum, a lacinia felis pellentesque. Aenean quis sapien vitae ligula cursus consectetur non at sapien. Sed viverra vitae tortor id condimentum. Nullam non vulputate massa. </p> <p> Etiam et odio facilisis, lacinia ligula et, tincidunt lectus. In tincidunt tortor accumsan, semper ipsum pulvinar, mattis dolor. Donec non enim eu nisi congue viverra non porttitor ex. Cras mi tellus, lacinia vel ipsum ac, feugiat tempus sapien. Fusce bibendum malesuada libero eget eleifend. Integer elementum est nisi. Donec vel congue dui, vel iaculis ipsum. Duis scelerisque eget tellus ac luctus. Mauris a mi ante. </p> <p> Vestibulum eget justo in nisl dignissim tincidunt a et sem. Sed ullamcorper euismod nisl nec facilisis. Fusce ultricies urna quam, quis aliquet enim facilisis id. Donec ac lorem metus. Quisque blandit ut odio vitae luctus. Suspendisse interdum risus vitae leo iaculis, lacinia tempus erat pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut feugiat pellentesque nibh nec varius. Sed sed imperdiet augue. Donec sagittis facilisis tempor. </p> <p> Nullam id est lacinia, elementum nulla id, varius nisi. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse potenti. Mauris accumsan orci in ipsum condimentum dictum. Phasellus volutpat id quam dapibus lacinia. Suspendisse at vehicula dolor. Nullam pellentesque vitae dui et venenatis. Proin sit amet cursus purus. Nullam quis porta tellus. Morbi vestibulum dui quis nisi lobortis condimentum. </p> <p> Nulla consectetur, eros quis consequat consectetur, purus eros porttitor nunc, at consectetur nisi mi lobortis ante. Etiam a auctor arcu, vitae viverra sapien. Nunc euismod, purus eu faucibus pulvinar, nunc erat egestas metus, in ultrices elit mi sit amet tellus. Sed in interdum arcu. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Ut gravida sed diam quis fermentum. Praesent interdum lectus sodales efficitur semper. Mauris finibus aliquet leo, vitae lacinia dolor porta vitae. </p> <p> Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean tristique erat sed orci convallis, non tincidunt nunc varius. Nunc efficitur eros eu dui auctor, ac scelerisque nibh varius. Fusce quis aliquam orci. Duis aliquam eros lectus, commodo iaculis justo vulputate eu. Aliquam ultrices, risus ac cursus pellentesque, orci justo facilisis mi, ac tincidunt neque est non felis. Nullam dictum purus sed justo viverra efficitur. Proin sollicitudin risus eu condimentum efficitur. Donec malesuada, leo sit amet facilisis dignissim, orci augue efficitur nulla, vel pharetra elit dui sit amet magna. Praesent eget sagittis est. Nunc dapibus auctor ante eget tincidunt. Sed dapibus porttitor ex. </p></div></article><h1>Article lightbox.</h1></div>
* `img`. [Demo](#lightbox-img)<div id="lightbox-img" lightbox><a href="#screenarea"></a><img src="https://upload.wikimedia.org/wikipedia/commons/f/f8/Composite_Image_of_NGC_300.jpg"/><h1>Lightbox with an img.</h1></div>
* `video` (removed due to issues with github) `(Won't be displayed if `autoplay` attribute is found.). [Demo](#lightbox-video)<div id="lightbox-video" lightbox><a href="#screenarea"></a><h1>Lightbox with video.</h1><video preload="auto" width="100%" height="100%" allowfullscreen controls><source src="https://upload.wikimedia.org/wikipedia/commons/c/c5/Artist%E2%80%99s_impression_of_the_black_hole_inside_NGC_300_X-1_%28ESO_1004a%29.webm" type="video/mp4"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Artist%E2%80%99s_impression_of_the_black_hole_inside_NGC_300_X-1_%28ESO_1004a%29.webm/1280px--Artist%E2%80%99s_impression_of_the_black_hole_inside_NGC_300_X-1_%28ESO_1004a%29.webm.jpg"></video></div>`
* `iframe` (issues with github, removed) `(View LightBox\_Rules.md for more). [Demo](#lightbox-iframe)<div id="lightbox-iframe" lightbox><a href="#screenarea"></a><!--<iframe width="100%" height="100%" src="http://simple.wikipedia.org/wiki/Main_Page" srcdoc="<a href='http://simple.wikipedia.org/wiki/Main_Page'>Click to view a Wikipedia</a><meta http-equiv=&quot;refresh&quot; content=&quot;10;URL='http://simple.wikipedia.org/wiki/Main_Page'&quot;/>"></iframe>--><h1>iFrame lightbox - Removed due to github issues.</h1></div>`
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

<hr id="notrightorder">

### What happens when I don't put things in the right order?

Don't worry! I have fallbacks!

The order:

    <div id="lightbox" lightbox>
     <a href="screenarea"></a>
     <article>Content goes here in places of article</article>
     <h1>This is the title</h1>
     <!-- Links to other places are here -->
    </div>

[One like this](#lightbox)

Now, [One that missed the memo](#lightbox-bad)<div id="lightbox-bad" lightbox><h1>Something's different about this lightbox.</h1><a href="#screenarea"></a></div>

As you can see, it's not exactly the end of the world with it.

[Adding content](#addingcontent)
