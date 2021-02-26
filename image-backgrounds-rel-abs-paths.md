<h1 class="capitalize">COMD2451</h1>
<h2 class="sentence center">Images and their backgrounds in HTML5</h2>
<h3 class="sentence center">Relative vs Absolute Paths</h3>

---

<section class="section">
    <h2 class="sentence">The img element in HTML5</h2>

`Images` can ***improve*** the `design` and `appearance` of a `web page`. They ***make*** the `page` ***more*** `alluring` to the `user`.

</section>

---

<section class="section">
    <h2 class="sentence">The HTML img element</h2>

The `HTML img element` is ***used*** to ***embed*** an `image` in a `web page`.

It ***only*** `contains` ***one*** `tag` and is `self-closing`.

```html
<img>
```

</section>

---

<section class="section">
    <h2 class="sentence">The src and alt img element attributes</h2>

The `src attribute` of the `img element` ***specifies*** the `path` to the `image`.

The `alt attribute` ***specifies*** an `alternate text` for the `image` if an `image` is ***not*** `available`. It is ***also*** `required` for `accessibility` ***purposes***.

```html
<img src="https://source.unsplash.com/user/itookthose" alt="Random daily Photo from Sid Balachandran on unsplash">
```

In ***this*** `case`, ***unless*** the `image` ***no longer*** `exists` at the `URL` ***specified***, there are ***no*** `issues` ***regarding*** `relative` vs `absolute` ***paths*** to the `image`. That's ***because*** the `URL` is ***pointing*** to the `absolute path` of the `image`.

It is ***important*** to ***note*** that the `img element` should ***only*** be `used` to ***embed*** an `image` into an `HTML document`, and ***not*** `intended` for ***embedding*** `HTML text` (***other than*** in the `value` of the `alt attribute`).

</section>

---

<section class="section">
    <h2 class="sentence"> So what is an absolute path anyway?</h2>

An `absolute path` ***points*** to the ***full*** `url` of a `file`.

```html
<img src="https://source.unsplash.com/user/itookthose" alt="Random daily Photo from Sid Balachandran on unsplash">
```

***Here***, the `value` of the `src attribute` is the ***full*** `url` to a `random image` on [unsplash.com](https://source.unsplash.com/user/itookthose) of the ***unsplash user*** `itookthose` (`Sid Balachandran`). That also ***means*** that it ***represents*** the `live` (and `"permanent"`) `path` to the `file` on the `Web`, as is the ***case*** in the `random daily photo API` ***from*** the ***unsplash user*** `Sid Balachandran`.

</section>

---

<section class="section">
    <h2 class="sentence">The relative path in HTML5</h2>

The `relative path` in `HTML5` ***points*** to a `file` ***relative*** to the ***current*** `page` (`file`).

For ***example***, in ***my*** `index.html` ***file*** which ***contains*** an `image` of a `Panda eating bamboo`, and ***which*** is ***located*** in an `images folder` in the ***same*** `root project folder`, the `img element`'s `src attribute` would ***have*** the ***following*** `value`:

```html
<img src="images/sid-balachandran-_9a-3NO5KJE-unsplash.jpg" alt="Random daily Photo from Sid Balachandran on unsplash">
```

***However***, `because` I did ***not*** `specify` a `width` or `height` for the ***image***, the ***full*** `size` is ***displayed*** in the `browser` (which is ***huge***!).

To ***view*** the `image`'s ***full*** `dimensions`, we can ***go*** into the `browser console`, and ***click*** on the `Elements tab`. ***There***, we will ***see*** the `html markup` which is the ***same*** `markup` we ***have*** in our `index.html` ***file***!

if we ***hover over*** the `img element` ***there***, a ***small*** `popup` of the `image` ***appears*** with the ***full*** `dimensions` of the `image`. The ***full*** `dimensions` are `4290w x 2856h`. By ***default***, these ***dimensions*** are ***expressed*** in `px` (`pixels`).

</section>

---

<section class="section">
    <h2 class="sentence">Adding the width and height attributes to an img element</h2>

```html
<img src="https://source.unsplash.com/user/itookthose" width="900" height="600" alt="Random daily Photo from Sid Balachandran on unsplash">
```

After ***adding*** those `attributes`, we can ***go back*** into the `browser` and ***see*** what `effect` ***adding*** a `width` and `height` to the `image` has.

***Already*** it `looks` ***much*** `better`! ***However***, ***because*** we `defined` a ***specific*** `width` and `height` to the `image`, ***those*** `dimensions` will ***not*** `change` if the `web browser's dimensions` ***change***. And ***that*** is ***not*** a good thing!

***Another*** `thing` we `want` to ***address*** is ***where*** the `image` ***should*** be ***placed*** `vertically` and `horizontally` on the `page`.

</section>

---

<section class="section">
    <h2 class="sentence">Centering the image on the HTML page</h2>

I ***add*** the ***following*** to the `style element` in the `head` of the `index.html` ***file*** to ***basically center*** the `image` ***on*** the `HTML document`:

```html
<style>
    img {
        display: block;
        margin: 0 auto;
    }
</style>
```

If I ***want*** to ***lower*** the `position` of the `image` on the ***page***, I would `make` the ***following*** `change` to the `margin property declaration`:

```html
<style>
    img {
        display: block;
        margin: 3rem auto 0;
    }
</style>
```

***Now***, ***when*** we ***go into*** the `browser`, we `can see` ***how*** this `change` ***affected*** the `vertical positioning` of the `image` on the `page`. And ***yes***, it ***has been*** a bit ***lowered***!

But the ***one thing*** to ***note*** is that ***both*** the `display declaration` ***defined*** here and the `margin declaration` ***must*** be `used` ***together*** in ***order*** for the `image` to be ***centered*** on the ***page***.

</section>

---

<section class="section">
    <h2 class="sentence">So why are the display AND the margin property needed to center an image on the HTML page?</h2>

`img elements` are [both inline and block elements](https://stackoverflow.com/questions/2402761/is-img-element-block-level-or-inline-level). What ***does*** that ***mean***? It ***means*** that by ***default*** they ***flow*** `inline` like `text`, but they ***also*** have a `width` and a `height` ***like*** `block elements`. ***Therefore***, the `img element` is ***also referred*** to ***as*** a `replaced element`.

A `replaced element` ***has*** a `display value` of `inline` by ***default***, but its ***default*** `dimensions` are ***defined*** by the ***embedded*** `image`'s ***intrinsic*** `values` (i.e., the ***original*** or ***full*** `dimensions` (`width`  and `height`)).

To ***recap***, `img elements` are *`"block elements"`* in ***that*** they ***have*** a `width` and a `height`, ***but*** by ***default***, they are ***more like*** *`"inline-block elements"`* in ***that respect***. But they ***behave*** like *`"inline elements"`*.

***Explicitly*** `defining` the `display: block` `property declaration` on the `img element` ***separates*** the `img element` ***into*** a `block` of its ***own***, thereby ***making*** it ***behave*** like a `block element` ***instead*** of an `inline element` (it ***no longer*** `floats` to the ***left*** of the ***page***), and then the ***shorthand*** `margin property declaration` is ***actually able*** to ***center*** the `image` on the ***page*** as a ***result***.

The ***longhand*** for `margin: 3rem auto 0` would be the ***following***:

```css
margin-left: auto;
margin-right: auto;
margin-top: 3rem;
margin-bottom: 0;
```

So the ***longhand*** for the `img` `rule set` ***would be***:

```css
img {
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-top: 3rem;
    margin-bottom: 0;
}
```

</section>

---

<section class="section">
    <h2 class="sentence">CSS properties used on the img element</h2>

`CSS properties` such as `border`, `border-radius`, `padding`, `margin`, `width`, `height`, `max-width`, `display`, can ***all*** be ***used*** on the `img element`.

The `img element` ***accepts*** the `background`,  `filter`,`opacity`, `background-image`, `list-style-image`, and `cursor` ***properties***.

It ***accepts*** the `background-size`, `background-position`, `border-image`, `content`, `object-fit`, `image-orientation`, `image-rendering`, `float`, `transform` (***with*** `pseudo-selector:hover`), ***properties***. We'll ***go into*** the `transform property` ***when*** we ***cover*** `pseudo-selectors`.

</section>

---

<section class="section">
    <h2 class="sentence">The border property and the HTML img element</h2>

The `CSS` [border property](https://css-tricks.com/almanac/properties/b/border/) is a `CSS` ***shorthand*** `syntax` that ***accepts*** `multiple values` for ***drawing*** a `line` ***around*** the `element` it is ***applied*** to. When ***applied*** to an `img element`, it ***draws*** a `border` around ***all*** `4` of the `img element`'s ***sides***.

```css
img {
    border: 3px double #9c0b50;
}
```

The ***longhand*** for the `border property` ***is***:

```css
img {
    border-left: 3px double #9c0b50;
    border-right: 3px double #9c0b50;
    border-top: 3px double #9c0b50;
    border-bottom: 3px double #9c0b50;
}

```

</section>

---

<section class="section">
    <h2 class="sentence">The border-radius property and the img element</h2>

The `CSS` [border-radius property](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) ***rounds*** the ***corners*** of an `element`'s `border edge`.

```css
img {
    border-radius: 10px;
}
```

***Here***, the `border-radius property declaration` rounds ***all*** `four corners` of the `image` by `10px`. We can ***go into*** the `browser` and `witness` its ***effect*** on the `panda image`. You `can also` ***try this*** on your ***own*** `images`!

```css
img {
    border-radius: 10% 20%;
}
```

***Here***, the `top-left corner` and `bottom-right corner` are ***rounded*** by `10%`. The `top-right` and `bottom-left corners` are ***rounded*** by `20%`.

```css
mg {
    border-radius: 10% 30% 50%;
}
```

***Here***, the `10% `is ***targeting*** the `top-left corner` of the `img`, the `30%` is ***targeting*** the `top-right corner` and `bottom-left corner` of the `image`, and the `50%` is ***targeting*** the `bottom-right corner` of the `image`.

```css
mg {
    border-radius: 10% 20% 50% 35%;
}
```

***Here***, the `10%` ***targets*** the `top-left corner`, the `20%`  ***targets*** the `top-right corner`, the `50%` ***targets*** the `bottom-right corner`, and the `35%` ***targets*** the `bottom-left corner`.

The `border-radius property` is a ***shorthand*** for:

```css
img {
    border-top-left-radius: 10%;
    border-top-right-radius: 20%;
    border-bottom-right-radius: 50%;
    border-bottom-left-radius: 35%;
}
```

To view ***other*** `renditions` of the `border-radius property`, please ***visit*** the [border-radius property](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) on ***MDN*** or [w3schools](https://www.w3schools.com/cssref/css3_pr_border-radius.asp).

</section>

---

<section class="section">
    <h2 class="sentence">The background property and the img element</h2>

```css
body {
    background: #d4c259	url(images/sid-balachandran-_9a-3NO5KJE-unsplash.jpg) no-repeat fixed center;
}
```

***Here***, the `image` is ***being*** `used` as the `background` for the ***entire*** `body element`, ***covering*** the ***whole*** `viewport`. ***Because*** this `image` is ***so big***, and we have ***nothing*** such as `text` ***on top of*** the `image`, we ***can't*** actually ***take advantage*** of the `fixed property value` we `use`. We can ***go into*** [w3schools](https://www.w3schools.com/cssref/css3_pr_background.asp), for ***example***, to ***see*** what this `code` is ***really doing***.

***However***, if we ***add*** some `text` to the `page`, for ***example***, we can get a ***better*** idea of ***what*** the `background shortcut property` is ***doing*** here.

```html
<h1>An example of the background property and what it can do</h1>
<p>This is some example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
<p>This is some more example text.</p>
```

I ***added enough*** `paragraphs` so that ***there was*** `vertical overflow` and the `scroll bar` ***appeared***. When we ***scroll down*** the `viewport`, we ***see*** that the `image` **remains** *`"fixed"`* in the *`background`*, and the `text` ***scrolls up*** and ***down***. That is ***because*** of the `fixed property value` ***set*** on the `background image` of the `body` ***represented*** by the `CSS background property value` of `url(images/sid-balachandran-_9a-3NO5KJE-unsplash.jpg)`.

I ***also*** wanted to `center` the `h1` and `p text`, so I did the ***following*** within the `style element`:

```css
h1, p {
    text-align: center;
}
```

I ***also wanted*** to `change` the ***default*** `text color` of `black`, so I ***added*** the ***following*** to the `style element` as ***well***:

```css
h1 {
    color: #e0771c;
}
p {
    color: #3fb6b2;
}
```

If I ***wanted*** to get ***fancier***, I could ***add*** a `background `to the `text` so that it `pops out` ***more*** and ***apply*** the `CSS opacity property` to ***this*** `background` as ***well***, ***so that*** it ***doesn't completely*** `cover` the `background image`. That means ***adding*** a `wrapper element` (***usually*** a `div` or ***some sort*** of `sectioning element`) to the `HTML markup` ***too***. We will ***tackle*** that `exercise` ***later***, when we ***touch*** upon `Flexbox` and `CSS Grid`.

</section>

---

<section class="section">
    <h2 class="sentence">The background-image property and the img element</h2>

```css
body {
    background-image: url(images/sid-balachandran-_9a-3NO5KJE-unsplash.jpg);
    background-size: cover;
    background-position: center;
    background-color: #c1cc19;
}
```

The ***above*** is my ***favorite*** `approach` to ***setting*** a `background image` ***against*** the ***entire*** `Web page`. ***No more*** `whitespace` ***below*** a ***tiny*** `image` in ***smaller*** `screens` (`viewports`).

<aside>
    Note: Let's take a look in the browser and see what the image looks like with these three background-image related property declarations.
</aside>

`background-image`: ***this*** `property` sets ***one*** or ***more*** `background images` for an `element`. By ***default***, a [background-image](https://www.w3schools.com/cssref/pr_background-image.asp) is ***placed*** at the `top-left corner` of an `element`, and ***repeated*** both `vertically` and `horizontally`.

`background` of an `element`: the `total size` of the `element`, ***including*** `padding` and `border `(***not*** `margin`).

But to ***set*** the `background-image` ***alone*** is ***not*** enough. ***Just as*** when we `had` to `set` ***both*** the `display property declaration` and the `margin property declaration` ***together*** when ***centering*** an `image` on the ***page***, here we ***have*** to ***set*** at the ***very least*** the `background-size property declaration` as ***well***. ***Otherwise***, we'll ***end up*** with the ***same problem*** when we did ***not set*** an ***explicit*** `width` and `height` to the `Panda image` and ended up ***rendering*** its `original size` to the ***page*** (which is ***huge***!).

***That's where*** the `background-size property declaration` ***comes*** in.

</section>

---

<section class="section">
    <h2 class="sentence">The background-size property and the img element</h2>

`background-size`: ***specifies*** the `size` of the `background image`(s). There are `4` ***different*** `syntaxes` one can ***use*** with the `background-size property`:

1. The `keyword syntax` (`"auto"`, `"cover"`, `"contain"`)

2. The `one-value syntax` (***sets*** the `width` of the `image` and `height` ***becomes*** `auto`)

3. The `two-value syntax` (***first*** `value` is the `width` of the `image` and the ***second*** `value` is the `height`)

4. The `multiple background syntax` (***separated*** by ***commas***)

To ***view*** `examples` and `descriptions` of ***these*** `background-size property` ***values***, we can ***visit*** the [CSS background-size Property](https://www.w3schools.com/cssref/css3_pr_background-size.asp) on `w3schools`.

</section>

---

<section class="section">
    <h2 class="sentence">The background-position property and the img element</h2>

`background-position`: ***sets*** the `starting position` of a `background-image`. By ***default***, the `background-image` is ***placed*** at the `top-left-corner` of the `element`, and ***repeated*** both `vertically` and `horizontally`.

The `background-position property` can ***contain*** the ***following*** `property values`:

```shell
left top
left center
left bottom
right top
right center
right bottom
center top
center center
center bottom

x% y%

xpos ypos

initial

inherit
```

To ***view*** what these `property values` ***mean*** and ***do***, please ***visit*** the [CSS background-position Property](https://www.w3schools.com/cssref/pr_background-position.asp) on `w3schools`. The have `live editors` where you can ***play*** with the `code` and see `real time` ***results*** on the ***page*** (as well as ***everywhere else*** on the `site`).

</section>

---

<section class="section">
    <h2 class="sentence">The background-color property and the img element</h2>

`background-color`: the `background-color property` ***sets*** the `background color` of an `element`.

The `background` of an `element` is the `total size` of the `element`, ***including*** `padding` and `border `(but ***not*** `margin`).

Using a [background-color](https://www.w3schools.com/cssref/pr_background-color.asp) ***behind*** a `text color` can ***make*** the `text` ***easy*** to ***read*** (***depending*** on the `color combination` you ***choose***!). The `background-color property` is ***also*** `used` as a `fallback` for a `background-image property declaration` in ***case*** if an `image` is ***not*** available (***doesn't render*** to the ***page***).

***Other*** `background-related properties` you can ***access*** via the ***above*** `w3schools background-color link` ***are***: `background`, `background-attachment`, `background-blend-mode`, `background-clip`, `background-image`, `background-origin`, `background-position`, `background-repeat`, and `background-size`.

</section>

---

<section class="section">
    <h2 class="sentence">The background-image property can target an element other than body</h2>

The `background-image property` ***does not*** have to ***only*** `target` the `body element`. The `img element` can be ***embedded within*** a `div element`, for ***example***.

`div element`: ***aka*** `content division element`, is a ***generic*** (***non-semantic***) `container` for `flow content`. It has ***no effect*** on the `content` or `layout` ***until*** it is ***styled*** in **some way** with `CSS`. This ***means*** `styling` is ***directly*** `applied` to the `div` or ***some kind*** of `layout model` like `CSS Flexbox` or `CSS Grid`.

The **HTML**:

```html
<body class="Site">
    <main class="main-container">
        <div class="image-wrapper">
            <img src="images/sid-balachandran-_9a-3NO5KJE-unsplash.jpg" alt="Panda eating banana">
        </div>
    </main>
</body>
```

The **CSS**:

```css
body {
    background-color: #c1cc19;
}

div {
    display: block;
    margin: 3rem auto 0;
    background-image: url(images/sid-balachandran-_9a-3NO5KJE-unsplash.jpg);
}

img {
    width: 90%;
    max-width: 900px;
    height: auto;
}
```

***Above***, ***since*** we are ***wrapping*** the `img element` ***inside*** a `div`, we can ***either*** `set` the `display: block;` and `margin: 3rem auto 0` `property declarations` ***on*** the `div CSS element selector` or the `img CSS element selector`. These ***two*** `declarations` are what ***make*** the `image` ***responsive***, and the `width`, `max-width`, and `height property declarations` ***set*** its `size`. We will ***go over*** these ***responsive*** `img property declarations` in the ***next*** `slides`.

***Technically***, for the `purposes` of ***this*** `exercise`, we do ***not need*** to ***have*** a `main element` ***wrapping*** the `img div`, and we ***don't need*** a `.Site class` ***targeting*** the `body element`. It is ***just*** there ***because*** I was ***using*** it for ***another*** `image-related` ***exercise*** which we will cover ***later*** in the course when we ***get into*** `CSS Flexbox` and `CSS Grid`.

</section>

---

<section class="section">
    <h2 class="sentence">Responsive design with the CSS width property and height property with images</h2>

The *`CSS`* `width property` ***sets*** the `width` of an `element`.

***One*** way of ***making*** an `image` ***responsive*** `using` the `width property` is the ***following***:

```css
img {
    width: 90%;
    height: auto;
}
```

***Here***, we ***set*** a `width` of `90%` to the `image` ***instead*** of `100%`. ***Why***? Because we ***need*** a ***bit*** of `margin `to the `left` and `right`  as the `width `of the `viewport` ***diminishes***. We ***don't want*** the `sides` to be ***flush against*** the `edge` of the `viewport` or ***possibly*** even ***beyond*** it!

We ***set*** the `height` to `auto` so that we ***not only*** have `responsiveness` ***width-wise***, but we ***also*** have it ***height-wise***. As the `viewport height` ***changes***, the `height` of the `image` ***automatically*** `adapts` to it.

There is a ***drawback*** to ***setting*** the `height` of an `image` to `height: auto`. The `height` becomes ***very small*** when the `width` of the `viewport` is `small`, and there ***ends up*** being ***a lot*** of `whitespace` ***underneath*** the `image`.

The ***other issue*** is that the `height` of the `image` ***not only*** keeps on ***indefinitely*** `increasing` in `width` as the `viewport` ***increases*** in `width`, but the `height` ***continues*** to ***increase*** at the ***same*** `time`.

</section>

---

<section class="section">
    <h2 class="sentence">Responsive design with the CSS max-width property and height property with images</h2>

```css
img {
    max-width: 90%;
    height: auto;
}
```

Here, the `max-width: 90%; property declaration` is ***used*** so that the `image` ***scales down*** if it ***has to***, but ***never*** `scales up` to be ***larger*** than its ***original size***.

The ***drawback*** about this `max-width: 90%; property declaration` is that if one is ***dealing*** with a ***very large*** `image`, the ***issue*** of `"indefinite"` ***increase*** in `width` and `height` of the `image` with the ***increase*** in the `viewport size` ***still*** exists.

</section>

---

<section class="section">
    <h2 class="sentence">Responsive design with the CSS width, max-width, and height property with images</h2>

```css
img {
    width: 100%;
    max-width: 900px;
    height: auto;
}
```

Of ***all*** the `width` and `height property declaration` ***variations***, I find ***this one*** to be the ***best*** `solution`. ***Here***, there is a ***defined*** `max-width` ***set*** to the `img element`. ***This*** way the `image` ***doesn't*** `outstretch` itself `width-wise`, but ***for me*** the `height: auto property declaration` ***still*** `poses` a ***problem***.

</section>

---

<section class="section">
    <h2 class="sentence">Responsive design using background-related properties</h2>

***Example*** `HTML markup`:

```html
<body class="Site">
    <main class="main-container">
        <div class="image-wrapper">
            <img src="images/sid-balachandran-_9a-3NO5KJE-unsplash.jpg" alt="Panda eating banana">
        </div>
    </main>
</body>  
```

***Example*** `CSS`:

```css
body {
    background-color: #c1cc19;
}

.image-wrapper {
    background-size: cover;
    background-position: center;
}

img {
    display: block;
    margin: 3rem auto;
    width: 90%;
    max-width: 900px;
    height: 100vh;
}
```

The ***key*** `property declaration` ***above***, which `makes` ***all*** the ***difference*** in ***how*** the `image` ***responds*** to a `change` in `size` of the `viewport` is the `height declaration property`.

For ***example***, if you ***don't*** want to ***show*** anything ***other than*** the `image` on the ***page*** (***no*** `citations`, ***no*** `attributions`, ***no*** `titles`, `descriptions`, etc.), you ***might*** want the `image` to ***cover*** as ***much*** of the `viewport` as ***possible*** and have it be `responsive` at the ***same time***.

`height: 100vh` ***means*** that the `height` of the `image` should ***cover*** `100%` of the `viewport height` (`vh`). Chances ***are*** that you ***DO*** want to ***add*** some sort of `image attribution` (i.e., the `photographer`) and ***perhaps*** even ***add*** a `title` (`heading`) and `description` of what is ***going on*** in the `image`. ***Then*** you would ***probably*** want to ***adjust*** the `vh height` of the `image` to ***accommodate*** that ***additional*** `content`.

</section>

---

<section class="section">
    <h2 class="sentence">CSS Units</h2>

`CSS` has ***several*** [different units](https://www.w3schools.com/cssref/css_units.asp) for ***expressing*** `length`.

***Many*** `CSS properties` ***take*** *`"length"`* `values`, ***such as*** `width`, `height`, `margin`, `padding`, `font-size`, etc.

`Length` in `CSS `is a `number` ***followed*** by a `length unit` such as `px`, `em`, `rem`, `%`, ***etc***. Examples ***are***:

```shell
20px
2em
2rem
100%
```

It is `important` to ***note*** that a `whitespace` ***cannot*** appear ***between*** the `number` and the `length unit`. But ***if*** the `value` of the `number` is `0`, the `length unit` can be ***omitted***.

For ***some*** `CSS properties`, `negative` (`-`) `length` is ***permitted***.

There are ***two*** `types` of `length units` in `CSS`: `absolute` and `relative` ***length units***.

To learn ***more*** about `absolute` vs `relative length units`, please ***visit*** [CSS Units](https://www.w3schools.com/cssref/css_units.asp) on `w3schools`.

</section>

---

<section class="section">
    <h2 class="sentence">The vh length unit and the img element height property</h2>

The `CSS vh length unit` is a ***relative*** `length unit`. It is ***relative*** to `1% `of the `viewport height`. This ***means*** that `1vh` is ***equivalent*** to `1%` of the `viewport height`. So `100vh` would ***mean*** `100%` of the `viewport height`, etc.

But as with ***everything else***, if we ***add*** `padding` and/or `margins` to the `element`, `overflow` on the `y axis` ***represented*** by the `overflow-y property declaration` would ***appear***. This would be ***indicated*** by the `appearance` of the `vertical scrollbar` in the `browser window`.

***Relative*** `length units` are ***great*** for `responsive design`. ***Absolute*** `length units` are ***not***. That is because ***absolute*** `length units` are `fixed` (they ***don't*** `adapt` to the ***change*** in the `viewport size`), and will `appear` ***exactly*** as the ***expressed*** `dimension` (i.e., `50px`).

</section>

---

<section class="section">
    <h2 class="sentence">Related Resources</h2>

+ [Centering Things: W3C](https://www.w3.org/Style/Examples/007/center.en.html)

+ [The IMG (Image) Element: W3C](https://www.w3.org/MarkUp/html3/img.html)

+ [Is <img> element block level or inline level?: stackoverflow](https://stackoverflow.com/questions/2402761/is-img-element-block-level-or-inline-level)

+ [<img>: The Image Embed element: MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

+ [CSS Images Module Level 3 W3C Candidate Recommendation Draft, 17 December 2020](https://www.w3.org/TR/css-images-3/)

+ [border-radius: MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)

+ [HTML Images: w3schools](https://www.w3schools.com/html/html_images.asp)

+ [HTML Background Images: w3schools](https://www.w3schools.com/html/html_images_background.asp)

+ [CSS background-size Property: w3schools](https://www.w3schools.com/cssref/css3_pr_background-size.asp)

+ [`<div>`: The Content Division element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)

+ [CSS Units: w3schools](https://www.w3schools.com/cssref/css_units.asp)

</section>
