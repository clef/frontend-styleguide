# Clef Frontend Styleguide

When contributing _new_ CSS here are some conventions to consider to better write CSS as a team.

## Semantics

Always strive for specificity over brevity. The more specific our class selectors _are_, the easier it is to find and debug our CSS.

### Syntax

We use the BEM (block__element--modifier) to name class selectors. We should avoid applying styles to IDs. We should also avoid targeting descendant selectors. We use hypens to separate two words in the same name space, not camelCasing. We should avoid copying or mimic-ing JavaScript syntax for styling, as it can be confusing.

```html
<div class="dashboard">
  <h1 class="dashboard__header"></h1>
</div>
```

If a style is re-used on more than 3 different views or files in our app, consider making a utility class for it. Utility classes should begin with or be prepended by `u-`. A utility class selector looks like:

```css
.u-italic,
.u-uppercase,
.u-text-center
```

_*A small caveat to the utility class naming convention is that it somewhat violates the BEM naming convention._

### Naming Variables

### Spacing

### Listing CSS Properties

### Quotes

### Commenting

Commenting our CSS helps better visually distinguish groups of related blocks of CSS. Commeting also allows us to offer additional context to our teammates around styles that affect one another.

```css
/* Dashboard Header */
```

## Style

### Color

We use variables for color. All of our color variables are in `/common` under `static/scss/settings/colors.scss`. 

### Images

For non-transparent images use the JPEG format when possible. For non-decorative images, images that a user may depend on for understanding content, etc., use the HTML image tag and not the `background-image` property in your CSS.
