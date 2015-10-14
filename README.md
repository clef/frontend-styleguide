# Welcome to our nifty frontend styleguide

When contributing _new_ CSS here are some conventions we want to strive for or toward.

## Semantics

Strive for specificity over brevity. The more specific our class selectors _are_, the easier it is to find and debug our CSS.

### Syntax

We use the BEM (block__element--modifier) to name class selectors. We should avoid applying styles to IDs. We should also avoid targeting descendant selectors. We use hypens to separate two words in the same name space, not camelCasing. We should avoid copying or mimic-ing JavaScript syntax for styling.

```
<h1 class="hero__header"></h1>
<img class="hero__header-logo" src=""/>
```

If a style is re-used on more than 3 different views or files in our app, consider making a utility class for it. Utility classes should begin with or be prepended by `u-`. A utility class selector looks like:

```
`u-italic`
```

* A small caveat to the utility class naming convention is that it violates 

### Naming Variables & Global Styles

### Spacing

### Quotes

### Commenting CSS
