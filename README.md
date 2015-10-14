# Clef CSS Styleguide

When contributing _new_ CSS here are some conventions to consider to better write CSS as a team.

## Semantics

Strive for specificity over brevity. The more specific our class selectors _are_, the easier it is to find and debug our CSS.

### Syntax

We use the BEM (block__element--modifier) to name class selectors. We should avoid applying styles to IDs. We should also avoid targeting descendant selectors. We use hypens to separate two words in the same name space, not camelCasing. We should avoid copying or mimic-ing JavaScript syntax for styling.

```
<div class="dashboard">
  <h1 class="dashboard__header"></h1>
</div>
```

If a style is re-used on more than 3 different views or files in our app, consider making a utility class for it. Utility classes should begin with or be prepended by `u-`. A utility class selector looks like:

```
`u-italic`
```

* A small caveat to the utility class naming convention is that it violates 

### Naming Variables

### Spacing

### Quotes

### Commenting

## Style

### Color

We use variables for color. All of our color variables are in `/common` under `static/scss/settings/colors.scss`. 
