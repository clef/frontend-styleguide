# Clef's Front-end Styleguide

Here are some CSS and HTML best practices to consider when writing new CSS at Clef.

## Semantics

Always strive for specificity over brevity. The more specific our class selectors _are_, the easier it is to find and debug our CSS.

### Syntax

We use the SCSS flavor of SASS to preprocess our CSS.

### Naming Conventions

We use the BEM (block__element--modifier) syntax to name class selectors. Avoid applying styles to IDs and targeting descendant selectors. We use hypens to separate two words in the same name space, not camelCasing. We should avoid copying or mimic-ing JavaScript syntax for styling, as it can be confusing.

```html
<div class="dashboard">
  <h1 class="dashboard__header"></h1>
</div>
```

### Spacing

Using proper spacing is important for writing readable code. Something to remember: "Would you write an email without any spacing?" We use two-space indentation and no trailing white-space at the ends of lines.

The right way:

```css
.block__element {
  box-sizing: border-box;
  display: block;
  width: $width;
  height: $height; 
}

.block__element--modifier {
  height: calc($height / 2); 
}

```

The wrong way: 

```css
.block__element{
  box-sizing:border-box;
  display:block;
  width:$width;
  height:$height; 
}
.block__element--modifier{
  height:calc($height / 2); 
}

```
### Listing CSS Properties

Our compiled CSS actually shows re-ordered CSS properties, so we should always order them in our CSS files by grouping them logically and optimizing for what's easiest to search for, read, and debug.

  1. **Display properties** (or things that affect the box model of an element or object)
  2. **Type** (things that affect how fonts are displayed and positioned & their corresponding Visual Styles)
  3. **Decorative properties** (properties that are specific to decoration on structural [non-typographic elements)
  4. **Animations and/or element transitions**

An example:

```css
.block__element {
  box-sizing: border-box;
  display: block;
  width: $width;
  height: $height; 
  margin: 0 auto;
  padding: 0;

  color: $color;
  font-family: $Open-Sans;
  font-size: 16px; /* px preferred */
  line-height: 1.5; /* integers preferred */
  text-align: center;

  background: $bg-color url('images/bg.jpeg');
  background-color: $bg-color;
  background-image: url('images/bg.jpeg');
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  border: 1px solid $border-color;
}
```

Inside of the actual groups, we recommend listing properties alphabetically. And add a space between groups if and when there are more than 12 properties listed. Feel free to make a judgement call here based on how well you can parse the code.

## Style

### Quotes

Although either is technically fine, for consistency's sake let's use double-quotes.

```css
background: url("images/bg.jpeg");
```

### Units of Measure

Use pixels for font-sizes and whole integers for line-height. Instead of using rems or ems, we should scale our type and spacing sizes or variables down or up to be properly viewed and legible on mobile.

```css
font-size: 16px;
line-height: 1.5;
```

### Commenting

Commenting our CSS helps better visually distinguish groups of related blocks. Commeting also allows us to offer additional context to our teammates around styles that may affect one another.

An example:

```css
/* Dashboard Header */
```

### Color

We use variables for color. All of our color variables are in `/common` under `static/scss/settings/colors.scss`. Our colors should be stored as RGB or RGBA values.

```scss
$color-orange: rgb(255,153,63);
$color-blue: rgb(13,157,219);
$color-yellow: rgb(255,199,0);
```

### Images

For non-transparent images use the JPEG format when possible. For non-decorative images, images that a user may depend on for understanding content, etc., use the HTML `<img/>` tag/inline images and _not_ the `background-image` property in your CSS.

### Accessibility

Always include "alt" values in your `<img/>` tags.

## Things to Avoid When Contributing to Our CSS

* Using the !important declarative
* Styling IDs
* Targeting descendant selectors
* Excessive nesting (never ever more than 3 levels deep)


## Additional Resources

* [CSS Best Practices by Sezgi Uluçam](https://github.com/sezgi/CSS-Best-Practices)
* [Desigining for Performance by Lara Hogan](http://larahogan.me/design/)
* [SASS Guidelines](http://sass-guidelin.es/)
